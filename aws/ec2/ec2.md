# EC2에 추가 패키지 설치



**which** 명령을 사용하여 **amazon-linux-extras** 패키지가 설치되었는지 확인합니다.

```
$ which amazon-linux-extras/usr/bin/amazon-linux-extras
```

**amazon-linux-extra** 패키지가 설치되지 않은 경우, **yum**을 사용하여 설치합니다.

```
$ sudo yum install -y amazon-linux-extras
```



보통 eprl을 통해서 패키지를 설치 / 업데이트 할 수 있습니다.



[https://repost.aws/ko/knowledge-center/ec2-install-extras-library-software](https://repost.aws/ko/knowledge-center/ec2-install-extras-library-software)
