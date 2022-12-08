# aws profile 및 vault 구성

aws cli를 활용할 때 가장 기본적인 것은 credentials을 사용합니다.

현 사용자의 credental은 \~/.aws/credentials 에서 확인가능하며

여러개의 등록을 위해서 대괄호로 구분하고 있습니다.

```
[credential명]
aws_access_key_id = accesskeyidaccesskeyid
aws_secret_access_key = secretaccesskeysecretaccesskey
[credential명]
aws_access_key_id = accesskeyidaccesskeyid
aws_secret_access_key = secretaccesskeysecretaccesskey
```



credential을&#x20;







[https://github.com/99designs/aws-vault](https://github.com/99designs/aws-vault)



최신버전의 vault 다운로드

```
# always get latest version
sudo curl -L -o /usr/local/bin/aws-vault https://github.com/99designs/aws-vault/releases/latest/download/aws-vault-linux-amd64  
sudo chmod 755 /usr/local/bin/aws-vault
```



aws-vault 버전확인

```
aws-vault --version
```



profile 설정

만약 profile을 설정했다면 \~/.aws/credentials를 대체하기 때문에 삭제하는 것을 권장합니다.

```
# 설정
#aws-vault add <PROFILE_NAME>
aws-vault add tutorial
Enter Access Key Id: (YOUR_ACCESS_KEY_ID)
Enter Secret Key: (YOUR_SECRET_ACCESS_KEY)

# 확인
aws-vault ls
Profile                  Credentials              Sessions
=======                  ===========              ========
default                  -                        -
t101                     t101                     -


```

aws-vault를 통해서 작업을 시작하려면 aws-vault exec명령어를 사용합니다.

```
# 사용
#aws-vault exec <PROFILE> -- <COMMAND>
aws-vault exec t101 -- aws s3 ls
aws-vault exec --debug t101 -- aws s3 ls

aws-vault exec t101 -- terraform plan
aws-vault exec t101 -- terraform apply
```

[https://www.44bits.io/ko/post/securing-aws-credentials-with-aws-vault](https://www.44bits.io/ko/post/securing-aws-credentials-with-aws-vault)

