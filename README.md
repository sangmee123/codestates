# codestates
SW Career Up 패키지 2023 참여 - 유어클래스 | 코드스테이츠 학습 정리

# <Day 0> - Linux 

**ls -l**

옵션 a와 함께, 자주 사용하는 옵션 l은 **폴더나 파일의 포맷을 전부** 표현하라는 의미. 

다음 예시로, 하나의 파일 또는 하나의 폴더는 한 줄에 출력

'#' 기호는 설명을 위해 사용.

drwxr-xr-x   # 생략

-rw-r--r--   # 생략
___

**ls -a**: 
명령어 ls의 옵션 a는 **all** 이라는 의미. 숨어있는 폴더나 파일을 포함한 모든 항목을 터미널에 출력합니다.

**ls -al 또는 ls -la**

**explorer.exe .**:
WSL에서 **현재 위치**를 GUI로 실행하는 명령어 

**touch**:
파일 생성하기

**cat**:
파일의 내용을 터미널에 출력하기

**rm**:
단일 파일을 삭제

명령어 rm으로 삭제한 폴더나 파일은, 휴지통을 거치지 않고 삭제됨. 

---

**rm -rf**:
대시(-)를 사용하여 옵션을 입력(대시는 파일을 의미). 사용할 수 있는 옵션은 r과 f

+ 옵션 r은 "recursive"를 뜻하고, 옵션 f는 "force"를 뜻한다.

+ 옵션 **r은 폴더를 지울 때** 사용하고, 옵션 **f는 질문을 받지 않고 지울 때** 사용합니다.
---
**cp**: 폴더나 파일을 복사하기

cp helloWorld.txt hiComputer.txt

ls //helloWorld.txt hiComputer.txt 가 출력됩니다


<img width="560" alt="스크린샷 2023-06-24 092223" src="https://github.com/sangmee123/codestates/assets/69633033/b822d959-c486-49f4-85e7-8952bfecd5d7">
<img width="425" alt="스크린샷 2023-06-24 092707" src="https://github.com/sangmee123/codestates/assets/69633033/d047245d-ab02-4039-8071-2cac08acf016">
<img width="569" alt="스크린샷 2023-06-24 093955" src="https://github.com/sangmee123/codestates/assets/69633033/a027f96e-af1a-4855-aacb-8092198ab6c1">

___

**mv**: 폴더나 파일의 이름을 변경, 또는 폴더나 파일의 위치 옮기기

<img width="421" alt="스크린샷 2023-06-24 091811" src="https://github.com/sangmee123/codestates/assets/69633033/d0509653-aa57-4b74-ab43-4a075e7a57fd">
<img width="507" alt="스크린샷 2023-06-24 091424" src="https://github.com/sangmee123/codestates/assets/69633033/a9fd797a-c977-439e-8651-d5fca3798933">

___

**whoami**: 현재 로그인 된 사용자를 확인하는 명령어

---
## 관리자(root) 권한

**sudo**: 관리자 권한을 획득하는 명령어

<img width="498" alt="스크린샷 2023-06-24 100127" src="https://github.com/sangmee123/codestates/assets/69633033/19ec7634-f02b-4a7a-8877-9a39e39c84e8">

## nano 에디터 
CLI에서 환경에서 유명한 에디터는 vim(vi), emacs 등이 있다. 그러나 가장 사용하기 쉬운 에디터는 다름 아닌 nano 에디터이다.

Q. 왜 터미널에서 에디터를 사용 하나? 이미 Visual Studio Code와 같은 멋진 GUI 에디터가 있지 않나?

A. AWS(Amazon Web Service)와 같은 원격 서버 환경에서 원격으로 텍스트 파일을 편집해야 하는 경우가 있어서. 

---

**Ctrl + X**: 파일 편집 후 종료

<img width="583" alt="스크린샷 2023-06-24 101428" src="https://github.com/sangmee123/codestates/assets/69633033/f38506fb-8ac2-4f55-838b-95cfb0db7858">

화면에 표시된 ^X와 같은 내용은 Ctrl + X 키 조합을 의미

---

**^O WriteOut**: nano를 종료하지 않고, 파일을 저장할 수도 있습니다.

___

## 패키지와 패키지 매니저 개요
윈도우 운영체제에서 '알집'이나 '반디집'이란 프로그램으로, 여러 파일을 모아 하나의 파일로 만들 수 있다. 

이렇게 여러 파일을 담고 있는 하나의 파일을 '압축 파일'이라 하고, 리눅스의 **패키지**는 여러 파일을 모아 하나의 파일로 저장하고 있는 **압축파일**이다.

우분투는 기본적으로 apt라는 패키지 매니저가 내장되어 있다.

### <apt 패키지 매니저의 주요 명령어>

**apt update(관리자 권한 필요)**: 패키지 목록 갱신

패키지를 다운로드할 수 있는 여러 저장소의 최신 정보를 업데이트. 새로운 저장소를 추가하거나, 패키지를 설치하기 전, 최신 정보를 갱신.

**apt list -—upgradable**: 업그레이드 가능한 패키지 목록을 출력

**apt upgrade (관리자 권한 필요)**: 전체 패키지 업그레이드(버전 업)

**apt --only-upgrade install 패키지 이름 (관리자 권한 필요)**: 특정 패키지만 업그레이드(버전 업) 

**apt install 패키지 이름 (관리자 권한 필요)**: 패키지 설치 

**apt list --installed**: 설치된 패키지 보기

**apt search 검색어**: 패키지 검색

**apt show 패키지 이름**: 패키지 정보 확인

**apt remove 패키지 이름(관리자 권한 필요)**: 패키지 삭제

---
**sudo apt install 패키지 이름**: 관리자 권한으로 패키지 설치

Q. 너무 시간이 오래 걸리거나, 뭔가 과정 중에 예상치 못하게 멈춰있는 경우에는 어떻게 해야하나?

A. Unix 기반 운영체제에서는 Ctrl + C 키는 작업을 취소하고, 터미널의 사용자 입력을 다시 되찾아오는 역할을 한다. 

기본적으로 강제 종료의 방법이지만, 해당 키를 공식적인 종료 방법으로 안내하고 있는 경우도 많이 있으므로, 두려워하지 말고 뭔가 잘못된 것 같으면 Ctrl + C 키를 눌러 종료한다.

## Node.js 개요

JavaScript 런타임(runtime)중 하나인 **Node.js**

어떤 프로그램이 동작할 때, 프로그램이 동작하는 곳이 바로 **런타임**

크롬, 사파리와 같은 웹 브라우저가 대표적인 **JavaScript 런타임**이다. 그래서 JavaScript의 주된 용도는 웹 페이지를 구성

정리하면 런타임이란, 프로그래밍 언어가 실행되는 환경, 그리고 Node.js는 JavaScript 런타임

---

 **node helloWorld.js**: Node.js 환경에서 JavaScript 파일을 실행할 때에는 명령어 node에 실행할 파일의 이름을 입력
 
