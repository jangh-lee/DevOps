# crontab

1. crontab 백업

crontab -l > my\_cron\_backup.txt

크론텝 비우기

crontab -r



crontab 복원하기

crontab my\_cron\_backup.txt

crontab -l



시간설정

분 시 일 월 요일

0 5 \* \* \* - 매 정각 5분에 실행

0 \*/5 \* \* \* - 5분만다 진행

0은 일요일, 6을 토요일이다.

쉼표

0 5,11 \* \* \* 새벽 5시, 밤 11시에 실행

0 5,11 \* \* 0,3 일요일, 수요 새벽 5시와 밤 11시





위치

/etc/crontab



or crontab -e (실행 사용자는 작성자 자신)



실행로그

/var/log/syslog에 나온다. (실결과의 출력값이 기록되는 것은 아니다)

서버에 메일 발송 시스템이 없다면 이메일 내용은 /var/mail/사용자명 파일에 기록된다.







