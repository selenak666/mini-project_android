# mini-project (android app)

System Programming, Cloud Computing (2nd Semester 202i0. Integrated Mini Projec#)

개발 환경 : 우분투 리눅스 20.04 , Apache Cordova

사용한 클라우드 서비스 : Amazon AWS (Rekognition)

## 설명
------------------------------------------------------
### A. 프로젝트 명
Celebrity finder - android version

### B. 프로젝트 멤버 이름 및 멤버 별로 담당한 파트에 대한 소개

- 프로젝트 멤버 이름 : 박지원

- 담당한 파트 : 전체

### C. 프로젝트 소개 및 개발 내용 소개

- 프로젝트 목적
: 한 학기 동안 시스템 프로그래밍과 클라우드 컴퓨팅 수업을 들으면서 배웠던 개념들을 이용해서 안드로이드 앱를 만들어 보면서 배운 내용을 활용할 수 있는 능력을 기른다. 리눅스 개발환경에서 cordova와 클라우드 서비스를 활용하여 실제로 현실에서 사용 가능한 안드로이드 애플리케이션을 제작한다.

- 프로젝트 개발 내용

1. 유저가 인물 이미지를 업로드하면 그 인물의 이름과 인물에 대한 imdb 혹은 구글 검색 결과 링크를 반환 해 주는 안드로이드 앱
2. 우분투 20.04 버전과 apache cordova 에서 개발을 진행 하였다. 
3. 사진 속 유명인사를 인지 하는 api 로 아마존 AWS 클라우드 서비스 Rekognition를 사용한다. ; 업로드한 사진 속 인물을 분석하여 유명인사임을 인식하고 관련 정보가 있는 imdb 웹페이지 혹은 구글검색결과 링크를 보여준다. (RecognizeCelebrities 의 Request 에 대하여 반환되는 Response의 포맷을 보면 Urls 가 있는데, 인물에 대한 내용이 있는 Imdb 웹사이트 페이지 링크이다. 이 링크도 웹페이지에 표시된다. 
4. 익명 게스트 사용자 (유저) 가 AWS 서비스에 액세스하기 위한 임시 자격 증명을 얻기 위해서 Amazon Cognito 를 사용한다. ; (Manage Identity Pools 에서 새로운 identity pool 을 생성하고 생성 시 인증되지 않은 ID 에 대한 액세스를 활성화한다. 그런 후, IAM 으로 가서 생성한 identity pool 에 대한 Unauthenticated role 정책을 추가시킨다.)
5. html 파일에 jquery 와 aws sdk javascript 라이브러리를 포함시키고, aws 자격 증명을 얻기 위한 자바스크립트 코드를 추가한다. 사진 확인 버튼 클릭 이벤트에서 선택한 파일을 가져온 후, 로컬 파일 리더 개체를 만들고 선택한 이미지를 읽는다. 완료되면 rekognized celebrity API 에 대한 매개 변수 개체를 만들어서 선택한 이미지의 이진 표현을 가져온다. API 를 호출하고 반환된 결과에서 감지된 각 유명인의 얼굴에 대해 이름과 첫번째 url 링크를 가져온다. url ㅇ이 비어 있으면 유명인 이름을 검색 매개 변수로 사용하여 맞춤 google 검색 url 을 만든다. 유명인 이름과 url 이 포함 된 html snippet 을 만들고 album-list div 에 추가시킨다. 
6. cordova 개발 환경 생성 ; cordova cli 설치, app 폴더 생성, cordova platform add 명령으로 android ploatform 추가. 빌드를 위한 필수 구성요소 설치
7. 배포를 위해 cordova build android 명령으로 앱을 빌드한다.
8. 생성된 apk 파일을 안드로이드 장치에서 실행시킨다.


### D. 개발 결과물을 사용하는 방법 소개 (+ 프로그램 구동 화면 스크린 샷 첨부)

**앱 빌드**

![alt text](https://i.ibb.co/LxPkRGb/6-1.png)

**안드로이드 에뮬레이터에서 실행**

![alt text](https://i.ibb.co/T0vyTVm/6-2.jpg)

### E. 개발 결과물의 필요성 및 활용방안
사진 속의 인물을 보고 그 사람이 유명인사인지 아닌지, 만약 유명인사라면 누구인지 알고 싶은 경우가 있다. 그럴 때, 이 앱을 사용하면 궁금증을 해소 할 수 있다.
