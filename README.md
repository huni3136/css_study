# CSS(Cascading Style Sheet)
## CSS 작성 전 준비사항
* html 문서 준비(태그 작성 완료 상태)
* html, css 파일 별도 폴더 관리
* 최상위 폴더 html 파일 배치
* 하위 폴더명 css, styles 으로 css파일 배치 
* ex) index.html, index.css
## CSS 외부스타일시트와 내부스타일시트
* name.css 외부파일로 분리해서 html에 link로 연결하는 **외부스타일시트**
* html파일 내에서 head태그 안에 style태그로 구분해서 작성하는 **내부 스타일시트**
* 외부스타일시트 장단점 :
- 장점 : 1개의 css 파일로 여러개의 html을 관리할 수 있다.
- 단점 : 파일명 또는 파일 위치를 정확히 관리하지 않으면 파일 관리가 어려울 수 있다. 
* 내부스타일시트 장단점 :
- 장점 : html파일 내에 작성하여 태그와 한꺼번에 보기편하다.
- 단점 : 2개이상의 html파일을 동시에 디자인관리하는것이 불가능하다.
## CSS 선택자
1. 태그선택자 : `<h1></h1>` -> `h1 {속성:값;}`
2. 클래스선택자 : `<h1 class="a"></h1>` -> `.a {속성:값;}`
3. 아이디선택자 : `<h1 id="b"></h1>` -> `#b {속성:값;}`
4. 자손선택자 : `<h1><em><span></span></em></h1>` -> `h1 em span {속성:값;}`
5. 자식선택자 : `<h1><em><em></em></em></h1>` -> `h1 > em {속성:값;}`
## CSS 디자인하기
* CSS 작성 전 HTML이 미리 디자인이 되어있으면 안된다.
* **HTML을 디자인 초기화하는 작업이 CSS 디자인 전 반드시 선행되어야한다!!!**
* 초기화 CSS `reset.css` 공통파일(날짜나 프로젝트명 표기금지!)
# CSS 글자 표현 속성
## font-family
* 로컬글꼴(설치글꼴제공) 또는 웹 글꼴을 연결할 수 있다.
* "메인대표글꼴", "후보글꼴" (후보제한없음)
* 후보글꼴은 메인글꼴과 모양이 비슷한 글꼴로 연결해야 한다.
* 글꼴에 띄어쓰기가 있으면 따음표가 필요하다. 
## font-size
* 웹 글꼴 평균 16px
* 사용 단위 px, %, em, rem
* 절대값 : px, 상대값: %, em, rem(권장)
# 선택자 우선 순위
* #아이디(3) > .클래스(2) > 태그(1)
1. 다음 중 우선 순위가 가장 높고 낮은 선택지는?
* `#box .a .b p {}` > 3+2+2+1 = 8
* `#box #a .b p {}` > 3+3+2+1 = 9
* `#wrap #box .a {}` > 3+3+2 = 8
* `#wrap .a .b p {}` > 3+2+2+1 = 8
2. 다음 중 우선 순위가 가장 높고 낮은 선택지는?
* `#box a b p {}` 
* `#box #a .b {}` 
* `#box #wrap .a .b {}`> 
* `#wrap #box a {}` 
## color 
* 영문명 직접 입력 ex) 테스트용으로 주로 밝은색을 사용한다.
* aqua, lime, yellow, coral, ...
* 헥사코드 입력 최소값0 ~ 최대값F RFB 코드 기준
* RGB 웹 색상 기준으로 색상을 섞을 수록 밝아진다.
* #Hex #000000 == #000, #FF00CC => #F0C 
* rgba(red, green, blue,alpha) *최대색상 255
## box css
### display
* `block, inline, inline-block`
* 특정 태그가 화면에 어떻게 표시될지 지정하는 속성
* `block` : 새로운 행, 크기, 여백 인식
* `inline` : 내용만큼 크기 인식(그 외 크기인식불가능)
* `inline-block` : 내용만큼 크기인식(크기 추가설정가능), 옆으로 정렬
### box-sizing
* `box-sizing:border-box`
* 요소의 너비와 높이를 계산할 때 테두리, 여백(padding)까지 포함해서 계산하는 속성
* 속성 미적용 시 : w100+h100+padding-top20 = 100x120
* 속성 적용 시 : w100+h100+padding-top20 = 100x100
### width, height
* 요소의 너비와 높이
* 절대값px, 상대값%, 화면 상대값 vw, vh
* 상대값 처리는 0~100% 사이 값만 사용한다.
### border-radius
* 사각형을 원으로 만들어준다  50%로 사용 
### 테이블 열 수평/수직 방향 합치기
* rowspan : 세로 합치기
* colspan : 가로 합치기
* required = *필수
## form
* 속성선택자(form관련 주로 사용)
* 태그[속성] 태그에 속성이 있을 때
* 태그[속성=값] 속성의 값이 이것일 때
* 태그[속성^=값] 속성값이 이것으로 시작할 때
* 태그[속성$=값] 속성값이 이것으로 끝날 때
* 태그[속성*=값] 속성값이 이것을 포함할 때 (최소 2글자 이상)
## form요소와 속성
### `<form action="#" method=""></form>
* action :
* method :
### `<input type="" name"">`
* type : 
* name : 서버(action)전송 시 입력한 데이터 구분 명칭
* readonly : 입력불가능 읽기만 가능 
* disabled : 비활성화
* autofocus : 커서 깜빡거림, 딱 하나만 사용가능
* autocomplete="on" : 자동완성 on
* autocomplete="off" : 자동완성 off
* value : 미리 제시된 텍스트(활성화 시 제거안됨) 
* placeholder : 미리 제시된 텍스트(활성화 시 제거됨)
* value 와 placeholder의 차이점 :
* maxlength : 최대 글자 수 
### `<textarea></textara>`
* rows,cols :
* 사용용도 및 주의사항
### input의 입력양식과 선택양식
* text, url 등의 사용자가 직접입력가능한 입력양식
* radio 등의 사용자의 입력이 아닌 선택으로 들어가는 선택양식
* `name` : 입력양식(데이터 구분용), 선택양식(데이터구분 (개별데이터X, 그룹데이터구분용))
* `value : 입력양식(초기값), 선택양식(개별데이터구분용)
### background이미지
* background-repeat: no-repeat; - 이미지 반복 없애기
### select 
* 예) <select name="email"> <option value="naver.com">naver.com</option>
## CSS Layout
### float, flex
* `float` : 형제 관계에 해당하는 block or inline tag 왼쪽, 오른쪽 정렬할 때 사용
* 예 : ul-li*3ro 정렬 `ul li {float:left;}`
* `flex` : 정렬하고자 하는 아이템의 부모한테 flex를 먼저 설정한다.
* 예 : ul-li*3개 정렬 `ul {display;flex;}`
* flex 설정 시 **기본갑** : 메인축(수평) 교차축(수직)
* `display:flex` : 정렬대상의 부모 설정 속성값, 설정 시 해당 부모 기준 자식까지(자손X) flexible box layout으로 처리하겠다!
### flex
* `flex-direction`  : 아이템 정렬 방향, 컨테이너안의 메인축
* `row` : 왼쪽-> 오른쪽 (기본값)
* `column` : 위 -> (아래 수직축 변경) 
* `flex-wrap` : 컨테이너 내부 아이템 줄바꿈 처리 설정
* `wrap` : 자동 줄바꿈
* `wrap-reverse` : 역방향으로 자동 줄바꿈 
* `nowrap` : 줄바꿈 x 
* `flex-flow` : 컨테이너 안의 flex-direction과 flex-wrap을 묶음으로 처리
* `flex-direction:column + flex-wrap:nowrap 일 경우 -> flex-flow:column nowrap 이라고 작성 가능`
* `justify-content ` : 메인축의 정렬 방법 설정
* `flex-start` : 시작점으로 정렬
* `flex-end` : 끝점으로 정렬
* `center` : 가운데 정렬
* `space-between` : items을 container의 start, end 양끝 items을 배치하고 나머지는 고르게 정렬
* `space-around` :items을 container안에서 균등한 여백을 포함하여 정렬
* `align-content ` :container에 적용 교차축의 아이템이 2줄 이상일 경우 정렬방법, * flex-wrap:wrap 적용한 상태로 확인하세요.
* `stretch` :기본값(교차축 기준 아이템 늘리기)
* `flex-start` : container의 start지점 기준 item 정렬
* `flex-end` : container의 end 지점 기준 item 정렬
* `center` : container의 가운데 위치 기준 item 정렬
* `space-between` : container의 start, end 에 양쪽 끝 맞추고 나머지 item 균등하게 정렬
* `space-around` : container에서 모든 item 균등하게 정렬
* `align-self` : item에 적용하는 속성 flex box의 교차축을 정렬
* `flex-start` : 교차축 기준 container의 start 시작 위치(top or left)
* `flex-end` : container의 end 종료 위치(bottom or right)
* `align-self:center` : align-self:center
* `order` : item에 적용하는 속성, 정렬 순서 설정
* ` order:-1` : 가장 작은 수로 첫번째 정렬
* ` order:0` : 가장 작은 수로 두번째 정렬
* ` order:1` : 가장 작은 수로 세번째 정렬
* `input, button label {cursor: pointer;}` : 버튼 클릭시 모양 변경
## font-awesome
* `font-awesome 전용속성값`
* .fa {
    font-weight: 600;
    font-family: 
    'Font Awesome 5 Free',
    'Font Awesome 5 Brands',
    'Font Awesome 5 Solid';}
## z-index
* absolute 이용해서 요소 배치시 중첩위치가 생기면 태그 작성 순서에 따라 기본 배치가 결정된다 
* z-index 수동으로 설정하는 중첩순서 속성, 단위사용안함, 0~999 
* 사이트 접속 시 함께 실행되는 기간성 이벤트 및 주요 공지사항은 z-index가 999으로 최대값으로 사용된다. 
* z-index속성은 position의 추가속성이기 때문에 position속성 없이 사용할 수 없다. 
* `sticky` : 달라붙다
## animaiton
* background-attachment: fixed; : 배경 이미지 고정 