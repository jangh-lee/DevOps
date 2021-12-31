Region( 리전) - 세계 각 지역에
Availability Zone - 리전 안에 존재하는 데이터 센터의 논리적인 그룹. 실제 가용영역은 물리적으로 나누어 있지만 리전들보다 빠르게 통신하고 서비스 결합도를 높일 수 있다. 같은 리전에 다른 가용역을 설정해 재난에 안정성읖 높인다.

Local Zones 로컬 영역 - 로컬 영역은 리전 안에 존재하고 특정 지역에 보다 빠르게 통신하기위해 등장했다. 
Edge Location - AWS CDN을 제공하기 위해 만든 CloudFront 캐시 서버이다.


AWS IAM
IAM (AWS Identity and Access Management) - AWS 권한을 관리하는 서비스
계정별 권한을 부여하고 통제한다. 

MFA(Multi Factor Authentication)
- 팩터(Factor) : 사용자의 신원을 확인하는 방법에 따라서 지식 기반, 소유기반, 속성 기반의 인증으로 총 3가지 방법이있다.

지식 기반 - ID/PW를 이용한 방법
소유 기반 - 휴대폰 SMS 인증 
속성 기반 - 고유 속성 이용 지문인식, 홍채인식

IAM User - 사용자
IAM Group - 사용자 그룹
IAM Role - 권한
IAM Policy - 정책
