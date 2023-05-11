
https://practice1-e23e2.web.app/


*압축파일 다운로드 후 
npm install후에 사용 (vue 설치 되어있다는 가정하에)


* 프로젝트 구성방법 *
           참고사이트 : https://simplevue.gitbook.io/intro/
        1. node.js 설치 
           https://nodejs.org/ko/ 에서 LTS 버젼 설치
           브라우저에서만 실행했던 자바스크립트를 서버를 비롯한 다양한 환경에서 실행할 수 있는 환경을 제공
           노드는 자바스크립트 프로그램을 컴퓨터(터미널)에서 실행할 수 있게 하는 자바스크립트 실행기
           서버사이트 스크립트 언어가 아니라, 프로그램을 실행할 수 있는 환경(런타임)
           node 환경에서 자바스크립트로 서버까지 만들 수 있게 됨. 한 가지 언어로 프론트엔드, 
           백엔드 프로그램이 가능해짐
           설치확인 node -v  
        2. Vue CLI 설치(기본 vue 개발 환경을 설정해주는 도구)
           
           윈도우 사용자
           npm install -g @vue/cli  
           
           맥사용자
           sudo npm install -g @vue/cli  - Password는 본인 맥 비밀번호 

           npm(Node Package Manager)은 Node.js에서 사용할 수 있는 모듈(자바스크립트 라이브러리)들을 
           패키지화하여 관리함
           
        3. 설치확인
           vue --version
           만약 오류가 뜨면 윈도우 PowerShell 창에서 경로에 상관없이 아래 코드 입력
           PowerShell 창을 열려면 화면 왼쪽 아래 윈도우 아이콘 옆에 검색창에 PowerShell 입력하여 찾음
           PS C:\\WINDOWS\system32> Get-ExecutionPolicy
           Restricted
           PS C:\\WINDOWS\system32> Set-ExecutionPolicy RemoteSigned
           Y 선택 
           PS C:\\WINDOWS\system32> Get-ExecutionPolicy

        4. Vue 프로젝트 생성하기
           vue create 프로젝트명(Default Vue2 선택)
           cd 프로젝트명
           npm run serve 
           localhost 8080을 컨트롤키 누르고 클릭하면 브라우저에서 열림
           실행중인 vue를 종료하려면 터미널에서 Ctrl + C 클릭

        5. VSC에서 확장프로그램 설치 : Vue VSCode Snippets, ESLint
           ESLint 설치 후 생기는 오류 해결
           설정아이콘 클릭 - 설정 클릭 - 오른쪽 위에 설정열기(JSON) 클릭하면 settings.json 파일이 열림
           { 
               맨 아래에 아래 코드 추가
               "eslint.workingDirectories": [
                  {"mode": "auto"}
               ],
           }
        6. SFC(Single File Components) : HTML, CSS, JS를 단일 파일에서 캡슐화
           단축키로 SFC 구성하기 : vbase

        7. 웹폰트 아이콘 적용하기
           npm install --save @fortawesome/fontawesome-free
           main.js 파일에  import '@fortawesome/fontawesome-free/js/all.js'
           혹은 index.html 파일에 <link rel="stylesheet"      href="https.fontawesome.com/releases/v6.0.0/css/all.css">

        8. scss 사용하기
           npm install sass-loader sass webpack --save-dev
           <style lang="scss" scoped>

         9. vuex 사용하기
           npm install --save vuex@2.6.2
          
=================================================================================================


 파이어베이스 프로젝트 만들기
 
        0. vsc 터미널에서 npm install -g firebase-tools 설치(컴퓨터에 한번만 설치)
        1. npm i firebase vuefire@2.2.0-alpha.0 (프로젝트마다 설치)
        2. firebase.google.com 로그인
        3. 오른쪽 위에 "콘솔로 이동" 클릭
        4. "프로젝트 추가" 클릭(무료는 10개, 기존 프로젝트를 제거해도 새로 생성되지는 않음ㅞㅡ )
        5. 프로젝트 이름 입력 -> "Firebase를 거래, 사업, 기술, 직업과 관련된 목적으로만 사용할 것을 확인합니다." 체크
        6. "계속" 클릭
        7. "이 프로젝트에서 Google 애널리틱스 사용 설정" 안함
        8. "프로젝트 만들기" 클릭
        9. "새 프로젝트가 준비되었습니다."
        10. 프로젝트명 선택하고 앱에 Firebase를 추가하여 시작하기 아래 "</>(웹)" 클릭
        11. 앱 닉네임 입력, 또한 이 앱의 Firebase 호스팅 설정 "체크(선택)" 앱등록 클릭
        12. Firebase SDK 추가에서 npm 선택
        13. 마지막 콘솔로 이동 단계까지 확인하고 클릭
        14. firebase에서 "빌드" RealTime Database 클릭하여 "데이터베이스 만들기"
            위치설정 : 미국
            테스트모드에서 시작 "사용설정"
        15. firebase에서 "빌드" Storage "시작하기" 클릭
            테스트모드에서 시작 "선택"
            위치설정 "완료" 클릭
        16. firebase에서 "빌드" Hoting "시작하기" 클릭
        17. vsc에서 firebase login(긍정적 답) 후에 firebase init
            "Are you ready to proceed?" Y
            스페이스바 눌러 선택 (*) "Hosting: Configure files for Firebase Hosting and (optionally) set up GitHub Action deploys"
            "What do you want to use as your public directory?"(public) dist 입력하고 엔터
            "Configure as a single-page app (rewrite all urls to /index.html)?" N
            "Set up automatic builds and deploys with GitHub?" N
            "File dist/index.html already exists. Overwrite?" N
        18. firebase.com에 가서 프로젝트 개요 옆에 "설정아이콘"에서 "프로젝트 설정" 클릭
            내 앱에서 databaseURL(생성되는데 시간이 걸림)과 storageBucket 복사 
        19. vsc화면 firebase.js에 databaseURL과 storageBucke에 각각 붙여넣기
            databaseURL은 https:// 추가할 것
        20. vsc화면 main.js에서 다음 코드 입력(뷰파이어는 파이어베이스의 RTDB와 파이어스토어 DB형식을 뷰 애플리케이션과 연결할 수 있도록 도와주는 플러그인을 제공함)
            import { rtdbPlugin } from 'vuefire' 
            Vue.use(rtdbPlugin)
        21. 프로그램 작성하면서 npm run serve로 확인
        22. npm run build 후 firebase deploy
        23. 내용이 수정될때마다 npm run build 후 firebase deploy 함
        24. ctrl 누른채 Hosting URL에 표시된 주소 클릭하여 확인
     
           
           
           
           
