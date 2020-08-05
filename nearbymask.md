마스크 알리미
============



1강
---------------
브랜치 : 한 개발마다 용도에 따라 브랜치를 나누는 것 - 공간을 나눔

어디에 적용할 것인가 : base]


fork : collaborator가 아닌 경우에 사용 가능

octocat spoon knife



http : 인터넷을 통해서 정보를 주고받을 때 지켜야하는 규칙
  - 요청과 응답으로 이루어짐  Request에 대해 집중적으로 봄



api   JSON을 갖고오기위한 방법(함수, 메서드)



CRUD  Create, Read, update delete

요청
GET : URL에 표시된 리소스 가져오기  READ

POST : body 에 정보를 담아 서버에 입력   CREATE

PUT : URL에 표시된 리소스와 바꿔 치기  UPDATE

PATCH : PUT과 다르게 일부만 수정  UPDATE

DELETE : URL에 표시된 특정 리소스를 삭제 DELETE

왼쪽에 all in one
markdown allinone


JSON Key : Value 형식
"이름" : "심우빈"
"몇 강?" : 2


JSON의 특징
기존 XML보다 가벼움 - 같은 내용물을 포장을 했을 때 내용물이 무게에 따라서 배송비가 달라진다고 생각
	- JSON 이 훨씬 이득
많은 프로그래밍 언어 지원

전송 : 직렬화
수신 : 역직렬화

크롬에서 F11을 누르면 코드를 볼 수 있어요.

super_hero.members
super_hero[members]


API : 서비스들이 제공해주는 데이터들에 접근하고 사용할 수 있도록 도와주는 도구

REST : 하나의 아키텍쳐
소프트웨어 아키텍쳐 : 소프트웨어를 설계하는 지침과 원칙
REST 구성 요소

자원 : GET /likelion/..././..
        PATCH /likelion/..././..

행위 : GET
        PATCH

표현 { "members" : [1,2,3] }



2강
--------------------------------

JSONPlaceholder

Fake online REST API

REST API를 테스트, 프로토타이핑 가능

URL의 구성
프로토콜 http, https, file 등
호스트주소 www.naver.com 등
파일 경로 /aaaa
Query parameter ?id=1&postID=1 등등



3강
----------------------------------------
ofcourse : https://ofcourse.kr/ -> 공부하기 좋아요.
W3C School
MDN Document
생활코딩 WEB2 - Javascript


_Javascript_

웹페이지를 동적으로 만들 때 사용하는 언어
객체 기반의 스크립트 언어

할 수 있는 일이 굉장히 많음
  * Browser API - DOM, 위치정보, audio, 화면공유 등 Browser 에서 제공하는 API 들
  * 2D, 3D 그래픽 작업 - NullSchool
  * 클라이언트 뿐만 아니라 서버도 JS로 가능 - Node.js

스크립트 언어 + 인터프리터 방식 (파이썬과 동일)
  * 입력 후 바로 결과 확인이 가능
  * 브라우저에 내장된 엔진으로 즉시 해적
  
사용법 1: HTML 내부에서 <script> 태그 내에 사용

사용법 2 : .js파일로 만들고 <script src="파일경로">를 사용해서 불러오기


_변수_

1. 사용가능한 데이터 타입 : Boolean, Null, Undefined, Number, String, Symbol, Object

2. var : 권장하지 않는 변수 선언 방식
  * Hoisting
  * Function scope 변수 (타 언어와 다른 점)
  * 중복 선언 가능
  * 예측하기 어려운 코드를 만들 수 있음

3. let : block scope 변수 (타 언어와 비슷하게 동작)

4. const : 변하지 않는 데이터를 저장 (ex. 파이, 객체)


_DOM_

1. DOM : Document OBject Model -> 웹페이지에 접근할 수 있게 해주는 일종의 인터페이스

2. Javascript와는 별개

3. JAvascript에 DOM을 조작할 수 있는 API 존재

<pre><code>

// ID 로 DOM 객체 선택
let idObj = document.getElementById("name");

// Class 로 DOM 객체 선택
let classPbj = document.getElementsByClassName("");

// CSS 선택자로 DOM 객체 선택
let selectorObj = document.querySelector("#kp-wp-tab-overview > div.cLjAic.")

</code></pre>

_DOM 속성 변경하기

<pre><code>

// 사용할 수 있는 속성들
// style, innerText, innerHtml
selectorObj.style = "color:yellow";
selectorPbj.innerTect - "안녕";
selectorObj.innerHTML = '<a href = "https://www.naver.com"> 네이버로 가기 </a>';

// a Tag의 href 속성같은 각종 태그들의 속성들
aTag.href = "https://www.naver.com";

</code></pre>

_함수 - 기본적인 형태_

<pre><code>

// 새로운 노드를 추가해주는 함수
function ver1_appendNewNode(targer, tag = "p", text = "기본값") {
  let newTag = document.createElement(tag);
   newTag.innerText = text;
   
   target.appendChild(newTag);
}

appendNewNode(target);
appendNewNode(target, "a");
appendNewNode(target, "a", "A태그!");

</code></pre>

_함수 - 익명함수_

<pre><code>

// 익명함수의 형태
let ver2_appendNewNode = function(target, tag = "p", text = "기본값") {
  let newTag = document.createElement(tag);
  newTag.innerTect = text;
  
  target.appendChild(newTag);
}

</code></pre>

_함수 - 화살표 함수_

<pre><code>

// 화살표 함수의 형태
let ver3_appendNewNode = (target, tag ="p", text="기본값") => {
  let newTag = document.createElement(tag);
  newTag.innerText = text;
  
  target.appendChild(newTag);
}

</code></pre>



4강
--------------------------------------------

비동기처리

들어온 요청들을 순차적으로 실행
-> 앞에 들어온 작업이 시간이 오래 걸리는 작업일 시 뒤에 작업 밀림

-> 이런 작업들을 그대로 실행시키면서 뒤에 있는 코드를
실행하는것이 비동기 처리

promise 객체 사용
대기, 이행, 거부의 상태

비동기 호출 - keyword

async, await 키워드 활용
-> 


async, await

비동기 하는 방법
async function asyncFunction() { await promise } 객체

fetch api 
네트워크 통신을 위해 제공되는 api
promise 객체 반환
request, response 두 객체 사



z index : 실습 1
컨트롤 / : 주석



5,6,7강
-----------------------------------------------------------

개발 순서

1. HTML 구조 만들기
 - Navbar, Main
 
2. 기본으로 들어있는 스타일 제거
 - 기본적으로 html, body에 margin이 들어있음
 - 그대로 놔두면 꽉찬 화면 만들 수 없기에 body, html이 전체화면을 채우도록 크기 지정

3. Navbar 만들기
 - 적당한 색, 투명도로 뒤에 지도 보이게 하기
 
4. Fontawesome CDN 추가
 - Fontawesome은 아이콘 폰트를 제공해주는 사이트
 - Black button과 유사한 아이콘 찾아서 넣어주기
 
5. Navbar에 Black button 추가
 - 위치는 왼쪽에 고정
 - 색은 흰색
 - 사이즈 조절해서 적당한 크기로 만들어주기
 
6. kakao 지도 추가
 - API 키 발급
 - 지도 추가
 - 지도 크기, 위치 조정
 
7. 검색 창 만들기
 - 검색창 구조
   * 검색창 전체 위치를 조정해줄 컨테이너
   * 검색창을 감싸고 있는 배경
   * 검색창의 input
   * 검색 버튼
 - 검색창 폰트를 나눔고딕으로 바꾸기위해 웹폰트 가져오기
 - 웹폰트 적용
 <pre><code>
     <!-- fontawesome cdn 아이콘 폰트 사용하기 위해 필요 -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.1/css/all.min.css" rel = "stylesheet">
 
 </pre></code>
 
 기능 : 검색기능, 마스크 데이터 불러오기, 표시하기, 마스크의 개수에 따라 다른 표시 띄우기, 클릭 시 수량 나오게
 
 시작화면 만들기 - UI, 목록
 
 _잘 안됐던 점_
 
 1.
 <pre><code>
 
  <script type="text/javascript" src="//dapi.kakao.com/v2/maps/sdk.js?appkey=834bfe4a6f51105398363d3e023a1f2b"></script>
 
 </pre></code>
 
 -> appkey 넣어주는 부분 Java로 했을 때 안되고, RestApi 넣어주니깐 됐음
 
 2. 마스크 수량 API 만료돼서 실습은 따로 안함
 
 _중간 중간 필기한 거!_
 ### 보자
 이동할 때 a태그


a href -> 이동경로


header.html에 유지되는 부분을 따로 빼서 모든 웹사이트에 동일하게 적용되도록 함


사진이나 폰트 크기 모든 거에 알맞게 하고싶으면 픽셀이나, 퍼센트 사용 XX

알맞게 하고 싶을 때
rem -> 폰트할 때 추천
vw, vh -> 추천


모바일 -> Bootstrap : CSS에서 모바일만 따로 잡아줄 수 있음


<p> -> br필요  : XXX
 
div -> OOO  

<li> 순서없는
<ol> 순서 붙어요

숫자, 로마자 저알 수 잇어
