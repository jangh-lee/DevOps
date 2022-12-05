# SSH 로그인 noti

```
#!/bin/sh

url="https://hooks.slack.com/services/XXX/YYY/ZZZ" # 슬랙 WebHook으로 설정한 URI
channel="#ssh" # 알림을 받을 SLACK CHANNEL
icon=":dark_sunglasses:" # 알림을 보내는 아이콘 설정
host="`hostname`"

if [ "$PAM_TYPE" != "close_session" ]; then
content="\"attachments\": [ { \"mrkdwn_in\": [\"text\", \"fallback\"], \"fallback\": \"SSH LOGIN: $PAM_USER connected to \`$host\`\", \"text\": \"SSH LOGIN TO \`$host\` \", \"fields\": [ { \"title\": \"USER ID\", \"value\": \"$PAM_USER\", \"short\": true }, { \"title\": \"USER IP\", \"value\": \"$PAM_RHOST\", \"short\": true } ], \"color\": \"#F35A00\" } ]"
curl -X POST --data-urlencode \
      "payload={
        \"channel\": \"$channel\",
        \"mrkdwn\": true,
        \"username\": \"SSH_MONITOR\",
        $content,
        \"icon_emoji\": \"$icon\"
    }" $url &
fi

if [ "$PAM_TYPE" == "close_session" ]; then
content="\"attachments\": [ { \"mrkdwn_in\": [\"text\", \"fallback\"], \"fallback\": \"SSH LOGOUT: $PAM_USER connected to \`$host\`\", \"text\": \"SSH LOGOUT TO \`$host\` \", \"fields\": [ { \"title\": \"USER ID\", \"value\": \"$PAM_USER\", \"short\": true }, { \"title\": \"USER IP\", \"value\": \"$PAM_RHOST\", \"short\": true } ], \"color\": \"#F35A00\" } ]"
curl -X POST --data-urlencode \
      "payload={
        \"channel\": \"$channel\",
        \"mrkdwn\": true,
        \"username\": \"SSH_MONITOR\",
        $content,
        \"icon_emoji\": \"$icon\"
    }" $url &
fi
```





참조

[http://www.coolio.so/slack으로-ssh-로그인-알림-확인/](http://www.coolio.so/slack%EC%9C%BC%EB%A1%9C-ssh-%EB%A1%9C%EA%B7%B8%EC%9D%B8-%EC%95%8C%EB%A6%BC-%ED%99%95%EC%9D%B8/)
