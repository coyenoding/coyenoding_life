## 원격에서 jenkins job 정보 조회하기

[wiki.jenkins.io](https://wiki.jenkins.io/display/JENKINS/Jenkins+Script+Console#JenkinsScriptConsole-Remoteaccess)

```
# curl example via bash

curl -d "script=<your_script_here>" https://jenkins/script
# or to get output as a plain text result (no HTML)
curl -d "script=<your_script_here>" https://jenkins/scriptText
```

```
# curl submitting groovy file via bash
curl --data-urlencode "script=$(< ./somescript.groovy)" https://jenkins/scriptText

# curl submitting groovy file providing username and password via bash
curl --user 'username:password' --data-urlencode "script=$(< ./somescript.groovy)" https://jenkins/scriptText
```

ex) curl --user 'username:password' --data-urlencode "script=$(< ./scriptfile.groovy)" http://myjenkins/scriptText

---
## 오류 발생
org.eclipse.jetty.util.Utf8Appendable$NotUtf8Exception: Not valid UTF8! byte D6 in state 2

## Solution
Groovy Script 파일을 UTF8 -> EUC-KR 로 변경

