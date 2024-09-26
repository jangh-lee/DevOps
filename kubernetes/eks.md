# eks

EKS 소개 동영상 [https://www.youtube.com/watch?v=E49Q3y9wsUo](https://www.youtube.com/watch?v=E49Q3y9wsUo)

1. eksctl 사용하기
2. [https://eksctl.io/](https://eksctl.io/)

```
eksctl create cluster \
--vpc-public-subentes #워커 노드용 서브넷
--name eks-work-cluster #클러스터 이름
-- region ap-northeast-2 #리전
--version 1.19

--nodegroup-name eks-work-nodegroup
--node-type t2.small
--nodes 2
--nodes-min 2  # 최소 워커노드수 
--nodes-max 5  # 최대 워커노드수



```



2\. yaml로 eksctl 사용하기

```
eksctl create cluster -f cluster.yaml
```



yaml 내용보기

```
apiVersion: eksctl.io/v1alpha5
kind: ClusterConfig

metadata:
  name: basic-cluster
  region: eu-north-1

nodeGroups:
  - name: ng-1
    instanceType: m5.large
    desiredCapacity: 10
  - name: ng-2
    instanceType: m5.xlarge
    desiredCapacity: 2

```



