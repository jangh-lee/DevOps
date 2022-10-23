---
description: 테라폼을 이용해 AWS 상에서 EC2 인스턴스를 배포해봅시다.
---

# EC2 배포

작업 디렉토리 생성 및 이동

```
// Some code
mkdir terraform-ec2
cd terraform-ec2
```



main.tf 생성 - EC2 1대 배포



```
cat <<EOT > main.tf
provider "aws" {
  region = "ap-northeast-2"
}

resource "aws_instance" "example" {
  ami           = "ami-0c76973fbe0ee100c"
  instance_type = "t2.micro"
}
EOT
```



terraform init

```
```

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

코드 파일 수정하여, EC2에 이름 부여하기

{% hint style="info" %}
AWS에서는 인스턴스의 이름을 주로 tag에서 key:values를 통해서 지정합니다. 테라폼도 해당 로직을 그대로 따릅니다.
{% endhint %}





보안그룹 수정

```
cat <<EOT > main.tf
provider "aws" {
  region = "ap-northeast-2"
}

resource "aws_instance" "example" {
  ami                    = "ami-0e9bfdb247cc8de84"
  instance_type          = "t2.micro"
  vpc_security_group_ids = [aws_security_group.instance.id]

  user_data = <<-EOF
              #!/bin/bash
              echo "Hello, T101 Study" > index.html
              nohup busybox httpd -f -p 8080 &
              EOF

  tags = {
    Name = "Single-WebSrv"
  }
}

resource "aws_security_group" "instance" {
  name = var.security_group_name

  ingress {
    from_port   = 8080
    to_port     = 8080
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

variable "security_group_name" {
  description = "The name of the security group"
  type        = string
  default     = "terraform-example-instance"
}

output "public_ip" {
  value       = aws_instance.example.public_ip
  description = "The public IP of the Instance"
}
EOT
```





