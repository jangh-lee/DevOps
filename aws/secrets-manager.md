# Secrets Manager

시크릿 매니저를 통한 키관리

시크릿 매니저를 통한 DB 비밀번호 등 접속관리



서비스 -> 보안, 자격증명 및 규정 준수 -> secret Manager를 선택

시크릿 매니저 항목에 가서 \[보안 암호 값 검색]을 통해 검색한다.



데이터 베이스 사용자 자체는 생성되지 않고 비밀번호만 생성한 것이므로 이후 사용자를 생성할 때 SM의 비밀번호를 등록하도록 하면 관리가 더 편하다.



Postgre SQL을 사용해보자

```
createuser -d -U eksdbadmin -P -h <RDS 엔드포인트 주소> mywork    
```

\-d : 생성한 사용자에게 데이터베이스 생성 권한 부여

\-P : 비밀번호 설정



여기서 등장하는 프롬프트는 총 세번으로&#x20;

첫 두번의 프롬프트는 다음과 같이 신규로 생성할 사용자 mywork의 비밀번호를 입력한다.

앞에서 AWS Secret Manager의 보안 암호로 확인한 데이터베이스 사용자의 비밀번호 값을 사용한다.



세 번째 프롬 프트는 다음 과 같이 표시된다/ 여기에는 데이터베이스 관리자인 eksdbadmin의 비밀번호를 입력한다.





애플리케이션용 데이터 베이스 생성

애플리케이션용 데이터베이스 생성은 create를 활용한다.

```
createdb -U mywork -h <RDSendpoint> -E UTF8 myworkdb
```

\-U : 유저

\-h : 접속하는 dB 호스트

\-E : 엔드포인트 지정옵션



DB 접속

postgresql client를 활용하기 위해 psql 명령어를 활용한다.

psql -U mywork -h \<RDS 엔드포인트 주소> myworkdb



DDL 실행과 예제 데이터 불러오기
