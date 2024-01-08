# JJCproject

# JJC 완료 보고서

## Overview (프로젝트 개요)

- 수업에서 학습한 지식과 퍼블리싱 기술을 응용해 웹사이트를 개발
- JavaScript 애니메이션 라이브러리 중 GSAP 학습

## 기획의도 & 목표

- 고난도 반응형 웹사이트 개발을 통한 퍼블리싱 실력 향상과 협업 강화
- GSAP 라이브러리 활용을 통한 높은 퀄리티 웹사이트 구현 도전
- 자바스크립트 숙련도 향상 및 다양한 문제 해결에 대한 전략 구축

## 작업 순서

- 사이트의 요구사항 및 디렉토리 구조 분석
- 코드의 가독성, 일관성을 유지하기 위해 퍼블리싱 가이드라인 정의
- 서브페이지 개별 작업 후 피드백 주고 받기
- 개별 메인페이지 파트 작업 후 통합
- 완성된 메인페이지에 서브페이지 연결

## 사용기술

- **개발 Tool**
    - Visual Studio Code
- **웹 화면**
    - HTML5 / CSS3 / JavaScript / GSAP
- **프로젝트 관리 Tool**
    - GitHub / Google Drive / Notion

## 각 담당 업무

- **장원준**
    - 리더 / main - intro 파트 / sub - Inside 페이지
    - header nav toggle 메뉴 구현
- **정하솔**
    - GitHub 관리 / main - about, contact 파트 /  sub - Contact 페이지
    - header PC 메뉴 GSAP ScrollTrigger 구현
- **최수민**
    - 보고서 및 회의록 작성 / main - works 파트 / sub - Works 페이지
    - Adobe After Effects로 메인 about 궤도 모션 영상 제작

## 프로젝트 내용

### **페이지 구성**

- **Main**
    
    Intro -
    
     js - 마우스 이벤트, 스크롤 이벤트
    
    About - 
    
    Works, Contact - 서브페이지와 동일 
    
- **Works**

- **Contact**

- **Inside**
    
    header - 각 서브페이지 연결, 토글메뉴


    # JJC 퍼블리싱 가이드라인

## 공통(HTML/CSS)

- 각 구간 안에는 <div>로 구분
- <class>명: 해당 구간에 '앞글자(소문자)_의미 있는 명'을 붙임
    
    **ex:** header 안에 menu => h_menu
    

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

- 작업 중간 중간 W3C 유효성 검사 필수
- 주석으로 알아보기 쉽게 구간 표시

## **HTML**

1. **구간**
- 구간 태그는 <header>, <secticon>, <footer> 사용
- <section>의 <class>명은 해당 페이지의 제목으로 작성
    
    **ex:** works->works / contact->contact
    
- css, js는 외부 링크로 작성
- 외부 링크 순서: <title> 하단에 og → favicon → font → reset → css
- <script>의 외부 링크는 끝나는 </body> 위에 넣음
- <meta>는 <title> 상단에 작성
1. **들여쓰기**
- space bar 2칸 기본 작성

## **CSS**

1. **선택자**
- <class>명을 기본으로 작성
- 작성법: 하위 선택자 기본
    
    **ex: .**h_container .btn{} (o) / **.**h_container > .btn{} or .btn{} or a{} (x)
    

```jsx
<header>
	<div class=“h_container”>
		<a class=”btn”></a>
		<a class=”btn”></a>
	</div>
</header>
```

- 특수한 경우에 그 외 선택자를 사용
    
    **ex:** a에 스타일이 공통적으로 들어가는 경우 **→** a{} (o)
    
1. **스타일** **시트 순서**
- header → main → footer 작업
1. **font**
- font-family: ‘Pretendard’, *apple-system, BlinkMacSystemFont, "Malgun Gothic", "맑은 고딕",  "Apple SD Gothic Neo", sans-serif;*
- 모바일과 PC는 동일하게 사용
1. **미디어 쿼리**
- 모바일 기준으로 작업 후 PC 작업
- 브레이크 포인트: 모바일 ( width >= 200px ) / PC ( width>= 1200px ) 설정

## **JavaScript**

1. **식별자명**
- 카멜표기법
- 변수 선언: 지역변수 기본 작성
- 변수명: 개발자들의 관습적인 명 사용

```jsx

// 예: 관습적인 명과 한글 주석은 상단 위치

// 버튼 엘리먼트를 선택
const btn = document.querySelector('.h_btn'); 
// 입력 엘리먼트를 선택
const inp = document.querySelector('.h_inp');   

---------------------------------------------------

// 틀린 예 : 자기만의 코드명 사용

const mybtn123 = document.querySelector('.m_btn');
// 버튼 엘리먼트를 선택 
const hellobtn = document.querySelector('.m_inp');   
// 입력 엘리먼트를 선택
```

1. **이벤트 처리**
- 이벤트는 .addEventListener 를 사용
- .onclick 사용은 지양

## **JavaScript GSAP Plugins**

- GSAP 플러그인 링크는 <script> 최상단에 넣음

```jsx
//플러그인은 항상 상단에 위치시킨다.
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.3/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.3/ScrollTrigger.min.js"></script>

<script>
	...~~
</script>
```

- 사용 플러그인: ScrollTrigger v*3.12.2*, ScrollSmoother *v3.10.0*

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

# 7. 프로젝트 완료 리뷰

## 아쉬운 부분

- **모션패스 미구현**
    - 모션패스 구현이 어려워 Ae 비디오 및 svg로 대체

- **포지션 고정의 어려움**
    - 이미지들의 고정 값 (화면의 크기가 달라지면 위치가 변하는 이슈)

- **레이아웃의 무너짐**
    - 레이아웃이 무너진 부분을 백그라운드 컬러로 대체.(레이아웃의 문제를 제대로 해결하지 못함)

- **토글 버튼(메뉴)**
    - 코드펜 사이트를 통해 응용하는 법만 익히고, 원본과 같이 구현하지 못함.

## 잘한 부분

- **팀 소통 및 협력**
    - 서로의 의견을 공유하여 도움요청, 문제해결, 역할분담 등을 매우 적극적으로 참여.
- **도전적인 프로젝트 선택**
    - 쉽고 단순한 웹사이트 보다 난이도 높은 웹사이트로 선택해 기술의 숙련도 상승 과 디자인 이해력 향상
- **문제해결 및 성장**
    - 어려운 상황에서의 문제 해결로 JavaScript 숙련도 상승 및 플러그인 구현 경험

## 배운 점 및 주관적인 의견

- **팀 협업 강화:** 팀 프로젝트를 통해 팀원들과의 효과적인 소통과 협업 능력을 강화
- **기술적 도전과 성장:** JavaScript와 GSAP 플러그인을 활용한 웹사이트 개발은 새로운 기술에 대한 도전이었지만, 이를 통해 디자인과 기술적인 성장을 이룸
- **창의적 대안 발견:** 어려운 부분에서도 포기하지 않고 창의적인 대안을 찾아내어 높은 완성도의 웹사이트를 구현하는 경험
- **향후 프로젝트에 적용:** 앞으로의 프로젝트에서도 이러한 경험을 토대로 더 나은 결과물 창출

---

피드백

1. 반응형 기술ㅈ덕인 면 중간에 보여주는게 좋을 것 같다
2. gsap 어떤 방법으로 학습했는지 보고서에 써주기
gsap의 어느 코드, 어느 방법을 통해 각자 공부했는지 등등
서치를 통해 비슷한 예제를 찾고 코드 파악
유튜브 영상 시청
