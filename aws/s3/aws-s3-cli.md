# aws s3 cli

## S3 버킷 -> 로컬 다운로드

```
aws s3 cp s3://<bucket_name> . --recursive
```



S3 버킷에 있는 내용을 로컬로 복사한다.&#x20;

\--recursive 명령어를 사용하면 대상의 모든 경로 하위 객체까지 포함해서 가져오게 된다.



## 로컬 -> S3 버킷 업로드

```
aws s3 cp ./ s3://<bucket_name> --recursive
```



## 특정 파일만 조건으로 복사하기

```
aws s3 cp <source> <destination> --recursive --exclude="*" --include="*.jpg"


```

