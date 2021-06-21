# ☕ Starbucks

- ## 홈페이지 주소  <br/>
  [STARBUCKS](https://pedantic-jennings-0c99aa.netlify.app/)

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

- ## youtube iframe api 사용
  유투브 영상이 출력될 위치 설정
  ```html
  <div id="player"></div>
  ```
  js 코드설정
  ```js
  new YT.Player('player', {
    videoId: 'An6LvWQuj_8', //재생할 유투브 영상의 id
    playerVars:{ 
      autoplay : true, //자동재생 여부 결정
      loop: true, // 반복 재생 유무
      playlist : 'An6LvWQuj_8' // 반복 재생할 유투브 영상 ID 목록
    },
    events : {
      onReady: function (event) {
        event.target.mute() //음소거
      }
    }  
  });
  ```
  <br/>
  
- ## gsap사용 (javascript를 통해 애니메이션 효과 추가하기)
  - fade-in 효과
  ```js
  const fadeEls = document.querySelectorAll('.visual .fade-in');
    fadeEls.forEach(function (fadeEl,index){
      gsap.to(fadeEl, 1, {
      delay: (index +1) * .7,  //0.7, 1.4 2.1 2.7
      opacity : 1,
    });
  });
  ```
  
- ## lodash사용 <br/> (자바스크립트 유틸리티 라이브러리-배열과 객체 데이터를 핸들링할때 사용하기 좋다.)
  - badge scroll 효과
  ```js
    window.addEventListener('scroll', _.throttle(function (){
    console.log(window.scrollY);
    if (window.scrollY > 500){
      // gsap.to(요소,지속시간,옵션);
      gsap.to(badgeEl, .6, {
        opacity: 0,
        display: 'none'
      });
      // badgeEl.style.display = 'none';
      //버튼 보이기
      gsap.to(toTopEl,.2 ,{
        x: 0
      });
    }else{
      gsap.to(badgeEl, .6, {
        opacity: 1,
        display: 'block'
      });
      // badgeEl.style.display = 'block';
      //버튼 숨기기
      gsap.to(toTopEl,.2 ,{
        x: 100
      });
    }
  } ,300 ));
  // _.throttle(함수, 시간)
  ```
