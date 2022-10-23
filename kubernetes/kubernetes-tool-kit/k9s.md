# K9S

K9S는 CLI환경에서도 쿠버네티스 클러스터를 UI처럼 관리할 수 있도록 도움 주는 도구 중 하나이다.



## 주요 특징

* 네임스페이스별 리소 현황 파악 가능
* metrics-server 기능인 클러스터 리소스 사용량 파악 가능
* pod에서 발생하는 log분석 가



<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>



## 설치

* release 페이지에서 최선버전 정보를 확인한다. &#x20;

[https://github.com/derailed/k9s/releases](https://github.com/derailed/k9s/releases)



* K9S\_VERSION에 해당 버전을 저장하고 파일을 다운받으면서 /usr/local/bin에 압축해제한다.

```
K9S_VERSION=v0.24.15
curl -sL https://github.com/derailed/k9s/releases/download/${K9S_VERSION}/k9s_Linux_x86_64.tar.gz | sudo tar xfz - -C /usr/local/bin k9s
```



## 실행

* k9s



