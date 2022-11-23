# ECR

## 1. ECR 개요

Amazon Elastic Container Registry (Amazon ECR)은 AWS 관리형 컨테이너 이미지 레지스트리 서비스로 쉽게말해 컨테이너 이미지를 저장 및 배포하도록 하는 허브이다.

기본적으로 프라이빗/퍼블릭 기능을 갖추고 있어 공개관리가 가능하다. AWS IAM 을 통해 리소스 기반 권한으로 프라이빗 컨테이너 이미지 레포지토리를 지원합니다.&#x20;

도커 이미지, Open Container Initiative(OCI) 이미지 및 OCI호환 아티팩트를 push, pull, manage가 가능합니다.



## 2. ECR 요금

* 퍼블릭 리포지토리 월 50GB 상시 무료 스토리지 제공
* 매월 퍼블릭 리포지토리에서 (AWS 계정 없이) 500GB 데이터 전송가능
* 매달 무료로 5TB의 데이터를 퍼블릭 리포지토리에서 인터넷으로 전송할 수 있으며, 모든 AWS리전의 퍼블릭 리포지토리에서부터 AWS 컴퓨팅 리소스로 데이터를 전송하는 경우 무제한 대역폭을 무료로 얻음
* 무료 사용량은 모든 리전에서 매월 계산되며, 무료 사용은 누적되지않음.
* [https://aws.amazon.com/ko/ecr/pricing/](https://aws.amazon.com/ko/ecr/pricing/)



## 3. ECR IAM 권한 추가

IAM 사용자 및 특히 EKS 등의 kubernetes 사용자가 직접 레지스트리에 접근해야할 경우 IAM 정책이 필요합니다.

AmazonEC2ContainerRegistryFullAccess

<figure><img src="../.gitbook/assets/스크린샷 2022-11-23 오후 5.37.37.png" alt=""><figcaption></figcaption></figure>



## 4. ECR 레포지토리 생성

ECR > 리포지토리 > 리포지토리 생성

* 표시여부 설정 : 퍼블릭 / 프라이빗



## 5. ECR 접속 및 푸쉬

docker에 대한 기본적인 지식은 모두 안다고 가정하고 진행하겠습니다.



먼저 AWS CLI에 접근할 수 있도록 config를 맞춘 후 aws ecr login을 진행합니다.



간단한 이미지를 빌드합니다.



이미지를 푸쉬합니다.



이미지를 pull해 봅니다.



