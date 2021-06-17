# ☕ Starbucks

- ## Open Graph

  어떤 HTML문서의 메타정보를 쉽게 표시하기 위해서 메타정보에 해당하는 제목, 설명, 문저의 타입, 대표 URL 등 다양한 요소들에 대해서 사람들이 통일해서 쓸수 있도록 정의해놓은 프로토콜. <br/>
  `og:title`: 제목
  `og:description`: 설명
  `og:image`: 이미지 정보
  
<br/>

- ## Twitter Cards

  140자의 텍스트만 표현할 수 있는 트위터의 제약을 확장할 수 있는 기능으로 추가적인 이미지나 내용을 미리보기처럼 보여주는 기능이다.

<br/>

- ## Reset CSS

  브라우저마다 기본적으로 제공하는요소에 따른 스타일의 기본값의 차이를 최대한 줄여서 브라우저 요소들의 스타일이 0인 상태에서 다지인을 만들어 나가기 위해 생겨난 것이다. (기본적으로 태그가 가지고 있는 간격이나 색상 등을 통일 시키는 작업.)
  ```html
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css" />
  ```
<br/>

- ##  Google Fonts & Material Icons

  구글이 제공하는 글꼴, 아이콘 디자인 모음.
  ```html
  <link rel="preconnect" href="https://fonts.gstatic.com">
  <link href="https://fonts.googleapis.com/css2?family=Nanum+Gothic:wght@400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
  ```
<br/>

- ## script 속성
  웹브라우저가 외부 자바스크립트를 불러오는 일반 script태그를 만나게되면, 우선 해당 스크립트를 내려받아 해석하고 실행 할때 까지 웹 문서의 HTML코드의 parsing작업을 잠시 뒤로 미루게 되는데, 용량이 큰 스크립트를 문서 해석 초기에 만나게되면 페이지를 불러오는 속도마저 지체되는 현상이 이러나는데 이러한 현상을 막기위한 방법이다. <br/>
  `defer` : `<script defer>`을 만났을 때 다운로드를 시작하시만, HTML의 파싱을 막지 않고 `</html>`을 만났을 때 실행된다.
  <br/>
  `async` : `defer`와 마찬가지로 다운로드 중에 HTML파싱을 막지 않지만 다운로드가 완료되면 즉시 실행하고 실행하는 동안 브라우저는 HTML 파싱을 멈춘다. <br/> (async속성의 스크립트에는 DOM을 조작하지 않으며 앞뒤에 로드되고 실행될 스크립트와 의존성이 없는 코드만 포함하는 것이 좋다.)

  <br/>
