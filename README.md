# JJC 팀 프로젝트

## 프로젝트 개요

- 수업에서 학습한 지식과 퍼블리싱 기술을 응용해 웹사이트를 개발
- JavaScript 애니메이션 라이브러리 중 GSAP 학습

## 기획 의도 & 목표

- 고난도 반응형 웹사이트 개발을 통한 퍼블리싱 실력 향상과 협업 강화
- GSAP 라이브러리 활용을 통한 높은 퀄리티 웹사이트 구현 도전
- 자바스크립트 숙련도 향상 및 다양한 문제 해결에 대한 전략 구축

## 작업 순서

- 사이트의 요구사항 및 디렉토리 구조 분석
- 코드의 가독성, 일관성을 유지하기 위해 퍼블리싱 가이드라인 정의
- 서브 페이지 개별 작업 후 피드백 주고 받기
- 개별 메인 페이지 파트 작업 후 통합
- 완성된 메인 페이지에 서브 페이지 연결

## 사용 기술

- **개발 Tool**
    - Visual Studio Code
- **웹 화면**
    - HTML5 / CSS3 / JavaScript / GSAP
- **프로젝트 관리 Tool**
    - GitHub / Google Drive / Notion

## 담당 업무

- 리더 ****
    - 코드 가이드라인 정의
    - 작업 계획 작성 및 팀원 일정 조율
    - gsap에 대한 학습사이트 제공과 원리를 알기 쉽게 주석으로 표시
    - 작업 시 팀원들의 문제해결을 리더로써 적극적으로 도움

- 작업
    - main - intro 파트 / sub - Inside 페이지
    - header nav toggle 메뉴 구현
    - Javascript를 이용해 다양한 이벤트 구현
    - 파워포인트 템플릿 작성
    - 팀 프로젝트 발표

## 프로젝트 내용

### **페이지 구성**

- **Main**
    
    Intro -
    
     js - 마우스 이벤트, 스크롤 이벤트
    
    css - position : sticky , 위치 값
    

- **Inside**
    
    header - 각 서브 페이지 연결, 토글 메뉴
    
    main- 스크롤 시 이미지의 위치가 변경하는 이벤트
    
    footer - family site 팝업
    

### **문제 및 해결**

- **상황 1**
    
    서브페이지 설계 중 사전에 맞춘 디렉토리 구조에 맞게 경로 작성 했으나 이미지가 누락되는 상황 발생
    
    - **문제 확인 및 해결**
        
        경로가 멀어서 로딩이 오래 걸렸던 것. 
        
        ⇒ 각 서브 폴더 안에 이미지 폴더를 추가해서 경로를 줄임
        
- **상황 2**
    
    메인페이지의 파트를 나눠 각자 작업한 다음 병합 했더니 레이아웃이 무너지고, 동작들이 구현되지 않는 
    
    상황 발생
    
    - **문제 확인 및 해결**
        
        CSS에서 준 속성들에서 충돌이 일어나면서 JavaScript까지 영향
        
        ⇒ 개인 작업을 토대로 한 사람이 HTML, CSS를 다시 설계한 다음 필요한 JavaScript를 넣음
        
- **상황 3**
    
    메인 인트로 부분에 sticky 속성을 이용해서 아래 콘텐츠가 인트로 위로 겹치면서 올라오는 효과를
    
    주려 했으나 실패
    
    - **문제 확인 및 해결**
        
        sticky 대신 JavaScript 스크롤이벤트효과와 transition 값을 줘서 해결
        
- **상황 4**
    
    메인 Contact 부분에서 ‘브로슈어 신청하기’을 누르면 모달창이 열림과 동시에 페이지 최상단으로 이동하는 오류 발생
    
    - **문제 확인 및 해결**
        
        JavaScript에서 <a>태그 기본 성격을 지우지 않아서 발생
        
        ⇒ .preventDefault로 제거하여 해결 
        
- **상황 5**
    
    기존 사이트에서 가져온 svg에 GSAP MotionPath을 적용되지 않는 상황 발생
    
    - **문제 확인 및 해결**
        
        서브페이지 타이틀에 들어가는 모션은 이미지로 대체하고, 메인 about 파트는 제작한 영상으로 대체
        

---

# 코드가이드 라인

## 공통(HTML/CSS)

- 각 구간 안에는 div로 구분하고 클래스명을 부여할 때 해당 구간에
    
    '앞글자(소문자)'를 따고 '_'를 사용해 뒤에 '의미있는 이름'을 붙여줌
    
    (ex: header 안에 menu =>h_menu)
    
    ```jsx
    <section class="main">
        <main>
            <div class="m_content">
                <!-- 메인 콘텐츠 내용 -->
            </div>
        </main>
    </section>
    
    <section class="footer">
        <footer>
            <div class="f_info">
                <!-- 푸터 정보 내용 -->
            </div>
        </footer>
    </section
    ```
    
- 작업 중간 중간 W3C유효성 검사 필수.
- 주석으로 알아보기 쉽게 구간 표시

## **HTML**

1. 구간**:**
- 구간 태그 header는 <header>,<main>,<footer>로 구분
- main을 구분할 때는 해당 페이지의 이름을 Class명으로 부여 (ex: works->works/contact->contact)
- css, js 작업은 외부 링크로만 작성
- 외부링크는 <title> 아래로 태그, og, favicon, font, reset, style 순으로 넣음
1. **들여쓰기:**
- 탭 2칸 (스페이스 사용x)
1. **파비콘 링크 추가하기:** 웹페이지의 **`<head>`** 섹션에 아래 코드를 추가하여 파비콘을 설정합니다. 예시는 파비콘 파일이 "favicon.ico"로 저장되어 있는 경우입니다:

```html
htmlCopy code
<link rel="icon" href="favicon.ico" type="image/x-icon">
<link rel="icon" href="favicon.ico" type="image/vnd.microsoft.icon">
<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">

```

이 코드는 파비콘 파일의 경로를 지정하고, 파비콘이 지원되지 않는 브라우저를 위해 타입을 지정합니다.

## **CSS**

1. **선택자**
- 선택자는 클래스명을 기본으로
- 하위 선택자를 기본으로 작성하고 특수한 경우에 그 외 선택자를 사용함
    
    <header>
    
    <div class= “h_container”>
    
    <a class=”btn”> </a>
    
    </div>
    
    </header>
    
    css = > .btn {스타일}     / 특수한 경우 (btn이 겹칠때) h_container .btn {스타일}
    
1. **스타일** **시트** **구조:**
- 스타일 순서는 일관성 있게 header → main → footer 작업
1. **효율적인 스타일 구조**
- 이미지 단위 : px 고정 필요에따라 %사용
- font-family:  ‘Pretendard’- 먼저 사용 ‘맑은 고딕’ ‘san-serif’ 순으로 사용 모바일과 통일성 유지를 위해 모바일도 동일하게 작성.
1. **미디어 쿼리**
- 모바일 기준으로 작업 후 pc 작업
    
    브레이크 포인트 : 모바일 >= 350px , pc >= 1200px 설정
    

## **JavaScript**

1. 식별자**명:**
- 변수 선언은 지역변수로 작성을 기본
- 변수 이름은 개발자들의 관습적인 이름을 사용

```jsx
javascriptCopy code
// 예: 명확한 변수명과 한글 주석
const btn = document.querySelector('.h-btn'); 
// 버튼 엘리먼트를 선택
const inp = document.querySelector('.h-inp');   
// 입력 엘리먼트를 선택

javascriptCopy code
// 예: 코드가 겹칠때
const mBtn = document.querySelector('.m-btn'); 
main > btn = mbtn = 명확한 표기를 위해 카멜표기법 mBtn
// 버튼 엘리먼트를 선택
const mInp = document.querySelector('.m-inp');   
// 입력 엘리먼트를 선택
```

2. **event 변수**

이벤트리스너안에 콜백함수를 다 쓸것인지. 어조는 간결하게. 통일성있게.

**이벤트 처리 및 addEventListener 사용:**

- 코드에서 이벤트 처리는 **`addEventListener`** 함수를 통해 수행됩니다. 이 방법은 JavaScript 코드와 HTML을 명확하게 분리하여 코드의 구조를 개선하고 관리성을 향상시킵니다.

**이벤트 객체와 event 변수 활용:**

- **`addEventListener`** 함수를 활용할 때, 이벤트 핸들러 함수 내부에서 **`event`** 변수를 사용하여 이벤트 객체에 접근합니다. 이 객체에는 이벤트와 관련된 다양한 정보와 속성이 포함되어 있어 코드 내부에서 이 정보를 활용할 수 있습니다.

**"onclick" 속성 사용의 제한:**

- HTML 요소에 "onclick" 속성을 직접 사용하여 이벤트 핸들러를 할당하는 것은 지양하며, 대신 **`addEventListener`** 함수를 활용하여 이벤트 처리를 구현합니다. 이로써 코드의 유지 보수성을 향상시키고 가독성을 높입니다.

---

# 프로젝트 완료 리뷰

## 아쉬운 부분

- **모션패스 미구현**
    - 모션패스 구현이 어려워 Ae 비디오 및 SVG로 대체

- **포지션 고정의 어려움**
    - 이미지들의 고정 값 (화면의 크기가 달라지면 위치가 변하는 이슈)

- **토글 버튼(메뉴)**
    - 코드펜 사이트를 통해 응용하는 법만 익히고, 원본과 같이 구현하지 못함.

## 잘한 부분

- **팀 소통 및 협력**
    - 서로의 의견을 공유하여 도움 요청, 문제해결, 역할 분담 등을 매우 적극적으로 참여.
- **도전적인 프로젝트 선택**
    - 쉽고 단순한 웹사이트보다 난이도 높은 웹사이트로 선택해 기술의 숙련도 상승 과 디자인 이해력 향상
- **문제해결 및 성장**
    - 어려운 상황에서 문제 해결로 JavaScript 숙련도 상승 및 플러그인 구현 경험

## 배운 점 및 주관적인 의견

- **팀 협업 강화:** 팀 프로젝트를 통해 팀원들과의 효과적인 소통과 협업 능력을 강화
- **기술적 도전과 성장:** JavaScript와 GSAP 플러그인을 활용한 웹사이트 개발은 새로운 기술에 대한 도전이었지만, 이를 통해 디자인과 기술적인 성장을 이룸
    - gsap 플러그인 학습 방법
        - gsap가 들어간 사이트를 참고해 코드에 대한 이해와 플러그인 응용법을 익힘
        - 네이버 블로그를 통해 직접 예제를 만들어 학습함
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/3144f39e-f821-47a0-a5b2-b520c2dcda89/8a579f93-ea1f-4793-b435-04ed119e92cf/Untitled.png)
        
- **창의적 대안 발견:** 어려운 부분에서도 포기하지 않고 창의적인 대안을 찾아내어 높은 완성도의 웹사이트를 구현하는 경험
- **향후 프로젝트에 적용:** 앞으로의 프로젝트에서도 이러한 경험을 토대로 더 나은 결과물 창출

---

## [프로젝트 바로가기](https://jjc0822.github.io/JJC/)**🎈**
