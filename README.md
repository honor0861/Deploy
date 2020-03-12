# Deploy
Deploy

# 세팅 절차
- git에 새로운 저장소 생성 https://github.com/아이디/Deploy
- 로컬 PC에서 aws 폴더를 vs code에 오픈
- terminal 오픈
- $ git clone https://github.com/아이디/Deploy.git
- cd Deploy

# 파일 세팅(~/aws/deploy)
- fabfile.py, deploy.json 파일을 위치
- 서버파일 생성
- wsgi.py(엔트리 포인트), run.py 생성
- 코드 작성
- 배포 관련 환경변수 파일 수정(deploy.json)
- git 주소, 서버의 IP, 도메인은 향후 IP와 연결(호스팅 쪽), 리눅스 접속 계정 ID 등 설정
- requirements.txt : 본 서비스를 구동하기 위해 사용된 모든 파이썬 패키지를 기술함

# 구동
- python3 버전 기반으로 수행
- 운영체계 및 서버 세팅 및 배포, 업데이트 관리 등등을 자동화하는 모듈 => fabric3
- $ pip3 install fabric3
- git에 최종소스 반영
- $ fab new_server
- 중간에 y, git로그인 등등이 나올 수 있다.
- 브라우저 가동
- 13.125.9.250 접속
- 접속로그 확인(리눅스에서 진행)
- $ tail -f /var/apache2/access.log

# 이후작업
- 코드수정
- git 최신반영
- 서버 업데이트
    $ fab deploy