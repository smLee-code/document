# 241224

> - git에 대한 전반적인 이해
> - 스프링 입문 시작

## git 입문

### git을 사용하는 이유

- 소스코드 및 개발 과정을 기록, 저장, 관리
- 협업 (형상 관리, 버전 관리)
- 거의 모든 회사에서 사용
- 오픈소스 
- 개발자 커뮤니티 기능



## git과 github

### 버전 관리 / 형상 관리?

- 파일을 하나로 유지하면서 언제든지 이전 작업 포인트로 돌아가서 수정할 수 있는 것

### 로컬 & 리모트

- 로컬 : 내가 보고 있는 PC
- 리모트 : 다른 사람의 PC
- git : 로컬에서 돌아가는 버전 관리 프로그램
- github : 다른 사람 컴퓨터에 버전들을 저장해놓는 원격 저장소
- 다른 여러가지 버전관리 프로그램이 있으나 git, github가 가장 대중적임

## git 명령어

### git 설치 

- cmd 창 'git --version' 입력으로 설치 여부 확인 가능
- git 홈페이지에서 다운로드 가능

### 유저 네임 / 이메일 세팅

- 'git config --global user.name 이름' : 유저 네임 세팅
- 'git config --global user.email 이메일' : 유저 이메일 세팅
- 'git config -list' : 확인
- 'global' : 앞으로 git에서 진행하는 모든 내용은 해당 유저 네임으로 진행

### 로컬 형상관리 명령어

- 'git init' : '.git' 폴더 생성. 해당 폴더가 생성된 폴더는 git이 관리되기 시작함
- 'git status' : 현재 git 상태를 보여줌
- 'git add .' : 모든 파일 스테이징
- 'git commit -m "message" ' : message 라는 이름으로 현재 add 되어 있는 코드들을 저장 
- 'git log' : commit 로그를 확인
- 'git reset --hard 커밋해쉬코드' : 해당 해쉬코드에 해당하는 커밋으로 코드를 롤백

### github 연동

- github == remote (회원가입 필요)
- git과 github의 이메일과 유저네임이 서로 일치해야 잔디가 심어진다.

1. 로컬에서 add, commit 진행
2. github에서 리포지토리 생성 
3. 'remote add origin https://github.com/유저네임/프로젝트명.git' 명령어 실행 
   - 해당 원격 리포지토리를 내 로컬 리포지토리와 연결
4. 'git push origin main' : 리모트 (리포지토리)의 main 이라는 브랜치에 로컬의 커밋 내용을 저장

- 'git clone 리포지토리_주소' : github 리포지토리에서 모든 커밋들을 내 로컬로 가져옴
- 'git fetch' : 서버에서 변경사항이 일어났는지 확인 (?)
- 'git pull origin main' : 서버에서 변경사항이 일어난 것을 로컬로 동기화한다.

### 개인 프로젝트

- 두 개의 PC로 작업을 이어서 하는 경우
- 회사의 작업을 집에서 이어서 하는 경우