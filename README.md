# linux-command

● 환경변수 세팅
sudo vi ~/.bashrc
source ~/.bashrc   << 적용

● 자바힙메모리 확인
java -XX:+PrintFlagsFinal -version 2>&1 | grep -i -E 'heapsize|metaspacesize|version'

● 특정 웹사이트의 HTTP 리턴 코드 보기
curl -L -k -s -o /dev/null -w "%{http_code}\n" https://주소

● 외부아이피 확인
curl ifconfig.me

● java jar 파일 백그라운드에서 실행 시키기
nohup java -jar 파일이름.jar &

● 특정포트 연결확인
curl -v telnet://100.1.1.1:8080

● tar 압축풀기
tar -xvf test.tar

● tar.gz 압축풀기
tar -xzvf test.tar.gz

● gz 압축풀기
sudo gzip -d 파일.gz 

● 파일 이름 검색
find . -name "STR*"

● 현재 부터 하위 모두를 검색하되, 갯수 세기는 -c 추가
grep -ri '내용' ./*

● 시간설정(AWS)
타임존 확인 timedatectl
타임존리스트 확인 timedatectl list-timezones | grep Seoul
타임존 설정 sudo timedatectl set-timezone Asia/Seoul
시간확인 date

● top 보는법
https://sabarada.tistory.com/146

● 레디스 접속
redis-cli --raw -h 주소 -p 6379

● crontab 실행로그
sudo tail -f /var/log/syslog

● crontab 등록
sudo vi /etc/crontab
*/5 * * * * root sudo 경로/파일이름.sh

● 윈도우 환경변수 바로 적용
taskkill /f /im explorer.exe
다시 exeplorer.exe

● 로그계속보기
sudo tail -f ./logname.log

● 서버 nginx 로그
sudo tail -f /var/log/nginx/access.log

● tomcat 정지 실행 재실행
sudo /경로/shutdown.sh
sudo /경로/startup.sh
sudo /경로/checkstart.sh

● nginx재시작
sudo service nginx reload - 재부팅
sudo service nginx stop - 중지
sudo service nginx start - 시작

● 프로세스 실행여부
ps -ef | grep tomcat

● 전체적인 CPU사용률, 메모리 사용률, 점유율 확인 가능
top

● 리눅스 vi 대소문자 구별없이 검색
대소문자 구분 없이 검색하려면 검색어 뒤에 \c 옵션을 붙여주면 됩니다. (사실 아무데나 붙여도 됩니다.)
/Hello\c

● 열려있는 모든 포트 표시
netstat -tnlp

● 윈도우 열려있는 포트 확인
netstat -ano | findstr \[::]\:

● 윈도우 프로세스 킬
taskkill /f /pid 5880


● 프론트 웹 서버 설정하는곳
tomcat - /etc/nginx/conf.d/tomcat.conf
nginx - /etc/nginx/sites-available/reverse-proxy.conf

● 로그경로들
/var/log/nginx


● 디스크 용량 찍기
df   << 전체용량
sudo du -ckx | sort -n > ~/list
# du -sh * | sort -hr
# sudo du -h --max-depth=1 | sort -hr


● 우분투 버전
lsb_release -d

● 좀비프로세스 찾기
sudo lsof | grep deleted

● 코드디플로이 시작
sudo service codedeploy-agent status

● git 캐시파일 지우기
git rm -r --cached .

● codedeploy 실행확인
sudo service codedeploy-agent status
sudo service codedeploy-agent start

