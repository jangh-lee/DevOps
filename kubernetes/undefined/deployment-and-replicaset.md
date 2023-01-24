# Deployment & replicaSet

Replicaset은 가장 처음 등장한 것으로 파드의 갯수를 의도된 상태에 맞춰 유지하는 역할을 했다.



이에 배포 기능을 추가한 것이 Deployment이다.

* 배포에 대한 이력 관리가 가능하다.
* replica 조절이 가능하다.
* 이미지 업데이트배포를 자동으로 해준다 (rolling update가 기본)/ 롤백가능
* 비정상 종료된 파드를 자동으로 재생한다.
*
