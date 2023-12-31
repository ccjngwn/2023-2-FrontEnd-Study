# 투두리스트 만들기

# 1. Vanilla JS의 필요성

Vanilla JS란 외부 라이브러리나 프레임워크를 사용하지 않는 순수 자바스크립트이다. 빠르고 가벼운 크로스 플랫폼 프레임워크이다. 하지만 프레임워크를 쓰면 간단하게 구현할 것을 복잡하게 구현해야한다는 단점이 있다. 요즘은 너무 프레임워크에 의존하기 때문에 Vanilla JS의 중요도가 높아지고 있다.

# 2. DOM

DOM은 문서의 프로그래밍 인터페이스이다. 문서의 구조화된 표현을 제공하며 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공하여 그들이 문서 구조, 스타일, 내용 등을 변경할 수 있게 만든다.

페이지 콘텐츠는 DOM에 저장되고 자바스크립트와 같은 스트립팅 언어를 통해 접근하고 조작할 수 있다.

# 3. To-do-list 화면 분석

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b9ba95b-fe7d-4e0d-bd6f-e95f92a3be44/33ca0c7a-ab0a-4b87-84f9-840b5544b45b/Untitled.png)

모서리가 둥근 네모 안에 세 부분으로 구성

1. “Things to do” 제목과 할 일 입력 창
2. 할 일 목록
3. 이미 완료된 일 목록

# 4. html, css에서 공부한 내용

### 1. css의 단위

css에는 여러 단위가 있다. 그 중 rem과 vh, vw를 공부했다.

rem: root em

r은 최상위를 뜻하며 최상위 태그에 지정된 것을 기준으로 하는 상대 단위이다. 최상위 태그의 font-size가 16px이라면, 2rem이라 지정한 font-size는 16px의 두 배인 32px이 된다.

vh: vertical height

vw: vertical width

뷰포트의 높이값과 너비값에 맞춰서 너비와 높이가 변한다. 1vh나 1vw는 뷰포트의 높이값과 너비값의 1/100이다. 예를 들어 브라우저의 높이값이 900px이라면 1vh의 값은 9px이 된다.

뷰포트란 현재 보고 있는 컴퓨터 화면의 영역을 나타낸다.

### 2. css box-shadow

box-shadow 프로퍼티의 값을 공부했다.

x-position: 가로 위치로, 값이 양수면 오른쪽에, 음수면 왼쪽에 그림자가 만들어진다.

y-position: 세로 위치로, 값이 양수면 아래쪽에, 음수면 위쪽에 그림자가 만들어진다.

blur: 그림자를 흐릿하게 만든다. 값이 클수록 더욱 흐려진다.

spread: 양수면 그림자를 확장하고, 음수면 축소한다.

color: 그림자 색을 정한다.

### 3. <form> 태그

html에서 form은 사이트의 방문자들에게 정보를 수집할 수 있는 태그들이다.

form의 동작 방식

1. 사용자가 폼을 입력한 후 submit하면 정보가 웹서버에 전송된다.
2. 웹서버는 정보를 처리하고 대부분 정보는 데이터베이스에 저장된다.
3. DB에서 CRUD작업이 일어나고 작업 결과를 app, web으로 보낸다.
4. 서버는 수신한 정보를 브라우저로 보내 새로운 페이지를 만든다.

action 속성과 method 속성, id 속성을 쓸 수 있다.

action=”url”의 형태로 쓰이며 폼에 있는 정보를 수신할 서버 페이지의 url을 입력한다.

method에는 정보를 전달하는 방식을 입력해준다. get방식과 post 방식이 있고 default 값은 get이다.

get - 주로 간단한 폼에 사용. url 정보가 보이고 보내야할 데이터의 양이 정해져있다.

post - 전송할 데이터가 길 때 사용. url 정보가 보이지 않고 민감한 데이터가 포함된 경우에 사용. 데이터베이스에 정보를 추가하거나 삭제할 경우 사용된다.

### 4. <input> 태그

다양한 type 값과 속성들을 입력하여 여러 종류의 입력 폼을 만들 수 있다.

type: “text” - 텍스트 입력 폼이 만들어진다.

placeholder - 입력한 값에 대한 힌트를 설정해 줄 수 있는 속성 값이다.

### 5. <section> 일반 구획 요소

html의 요소. 문서의 독립적인 구획을 나타낸다. 더 적합한 의미를 가진 요소가 없을 때 사용한다.

### 6. <span> 태그

html의 태그이다. <div> 태그처럼 특별한 기능을 갖고 있지는 않고, css와 함께 쓰인다.

<div> 태그와의 차이점은 <div> 태그는 display 속성이 block이고, <span> 태그는 display 속성이 inline이다. 쉽게 말하면 <div> 태그는 줄바꿈이 되고, <span> 태그는 줄바꿈이 되지 않는다는 점이다.

### 7. list-style property

css의 프로퍼티이다. List-style은 리스트의 앞 부분 모양을 지정해줄 수 있다.

list-style: squre; 이라 하면 앞 모양이 네모가 되고,

list-style: inside; 이라 하면 한 줄 들어간 동그란 모양,

list-style: none; 이라 하면 리스트지만 앞에 모양이 없어진다.

### 8. overflow property

css의 프로퍼티이다. 요소의 콘텐츠가 너무 커서 요소의 블록 서식 맥락에 맞출 수 없을 때의 처리법을 지정한다.

overflow: visible; 이라 하면 보이는 만큼만 보여주고

overlow: scroll; 이라 하면 보이지 않는 부분은 스크롤 하면 볼 수 있게 한다.

# 5. 자바스크립트 구현하기

구현해야하는 기능은 할 일을 입력하고 + 버튼을 누르면 todo칸에 들어가고, 개수가 카운팅되며, 할 일을 누르면 done으로 가고, 빗자루 버튼을 누르면 삭제되는 기능을 만들어야 한다. 그런데 자바스크립트 공부는 했지만 구현은 너무 어려워 그냥 코드를 따라 치며 이해하는 수준에 그쳤다.

JSON 파트를 다시 공부해야겠다는 생각을 하였고, 자바스크립트 대부분이 함수로 이루어져 있다고 생각하게 되었다.
