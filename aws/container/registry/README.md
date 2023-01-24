# Registry





1. ECR 서비스로 접속합니다. \[시작하기] 버튼을 통해서 리포지토리를 생성합니다.

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

2\. 표시 여부에서 프라이빗 혹은 퍼블릭을 설정합니다.

* 프라이빗 : IAM 등 정책 권한에 의해서 접근 가능한 사용자만 접근하도록 하는 저장소
* 퍼블릭 : 누구에게나 접근 가능하도록 공개하는 저장소

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

3\. ecr 로그인

```
aws ecr get-login-password --region ap-northeast-2 

docker login --username AWS --password-stdin
```



4\. ecr 푸쉬

이미지를 푸쉬할 때는 docker tag 명령어로 컨테이너 이미지에 태그를 설정한다. 해당 태그에 대해서 docker push 를 이용해 푸쉬한다.

```
docker tag k8sbook/backend ~~
이미지 레지스트리 주소/레지스트리 이름/컨테이너이름:버전
```
