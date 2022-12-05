# git ssh 접근

## 공통 (ssh-key 발급)

해당 내용은 openssh 가 설치되었다는 가정하에 작성되었습니다.



먼저 ssh-keygen을 통해서 서버의 public/private key pair를 생성합니다.

마지막에 id\_rsa가 저장되는 경로를 지정하는데 기본은 /{user}/.ssh/id\_rsa입니다.

```
# ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa): 

# ls ~/root/.ssh/
id_rsa   id_rsa.pub   known_hosts
```

`id_rsa` : private key

`id_rsa.pub` : public key. -> 우리가 등록하게 될&#x20;

`known_hosts` : 최초 ssh 접속시 기존 연결된 접속정보를 기록하는 곳입니다.



## gitlab

해당 리포지토리에 접속하여 우측 상단에 profile 아이콘을 클릭 > Edit profile을 클릭

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

다시 왼쪽에 User Settings 에서 \[SSH Keys] 탭을 누릅니다.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>



key 부분에 ssh pub 키를 등록고 \[Add key] 버튼을 클릭

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

##

## bitbucket

해당 리포지토리에 접속하여 \[Repository Setting] 을 클릭

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>



Security > Access Keys로 접

<figure><img src="../.gitbook/assets/스크린샷 2022-11-28 오후 2.48.16.png" alt=""><figcaption></figcaption></figure>

\[Add Key] 클릭

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

접속할 서버의 ssh pub키를 복사하여 넣습니다.

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

clone할 소스로 들어가서 \[clone]을 클릭

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>



SSH로 선택한 후 주소를 복사

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

이상없이 clone 됨을 확인했습니다.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
