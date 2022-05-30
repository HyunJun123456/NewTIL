FONT-FAMILY
글꼴

	Family-name과 generic-family로 구성
	Family-name은 지정순서로 폰트의 우선순위 결정(한글 지원 여부)
	Generic-family는 family-name으로 지정한 폰트가 사용자의 컴퓨터에 없을 시 적절한 폰트를 선택할 수 있도록 함

sans 삐침이 없음
serif 삐침이 있음

LINE-HEIGHT
줄 간격
행간격이 아니라는 것을 주의하기 바람
알파벳이 더 위에 존재하는 게 있고 더 밑에 있는 게 있어서
2하고 200%는 차이가 없을 수 있지만 상속에서는 차이를 보임

FONT-SIZE
글꼴 크기
기본 값 미지정 시 글꼴의 기본크기는 16px(1em)

FONT-WEIGHT
글꼴 굵기
normal과 bold만 지원하는 폰트일 경우, 100-500은 normal, 600-900은 bold임.
자식에게 영향을 주는 것은 사용을 지양

FONT-STYLE
글꼴 스타일 지정
italic: 이탤릭체, oblique: 기울임

FONT-VARIANT
글꼴 변환(소문자를 작은 대문자 형태로 표현)

FONT-
글꼴 속성의 축약형
	font-size와 font-family는 반드시 선언해야 하는 필수 속성
	각 속성마다 선언 순서를 지켜야 함
실무에서 사용을 지양

웹 폰트(@FONT-FACE)
사용자의 로컬환경(컴퓨터)에 글꼴을 다운로드 받아 적용
font-family, src 지정

VERTICAL-ALIGN
수직 정렬
	인라인요소 또는 테이블 세 상자의 수직 정렬을 지정함
	대부분 부모요소에 상대적으로 정렬됨
baseline, sub, super, top …
div에는 적용이 되지 않음
middle을 선언한다고 중간에 위치하는 게 아님


TEXT-ALIGN
텍스트 정렬
left, right, center, justify
justify는 양끝 정렬

TEXT-ALIGN과 DISPLAY의 관계
	text-align은 inline-level에 적용됨
	block-level을 text-align으로 정렬할 수 없음
div에 자식인 텍스트가 정렬되는 거임
div 자체는 center로 움직이는 게 아니라 안에 있는 텍스트만 가운데 정렬
div를 움직이고 싶으면 margin, padding 값을 주면 됨

TEXT_INDENT
텍스트 들여쓰기
부모요소 값으로 결정이 됨 

TEXT-DECORATION
텍스트 장식
overline, line-through, underline
텍스트에 의존적임







단어 관련 속성
	white-space : 연속된 공백과 줄 바꿈은 메꾸어져서 하나의 공백으로 표시
	letter-spacing
	word-spacing
	word-break
	word-wrap
white-space => nowrap 공백을 무시하고 쭈욱 작성함
letter-spacing => 상속이 되니 주의해야 함, 각 글자 사이의 간격이 조정됨(압축이 가능)
word-spacing => 단어 간격 조절
word-break => 문자열을 어떻게 자를 것인지
word-wrap => word-break와 비슷하지만 영역 밖으로 넘어가는 것을 어디서 자를지 결정


	추가 공부 내용들
line-height의 값으로 number를 선언할 때와 %로 선언할 때의 차이가 존재함
두 값 모두 font-size를 기준으로 동작하기 때문에 1이나 100%를 같은 것으로 오해할 수 있음
하지만 두 값은 큰 차이가 존재함
바로 line-height의 값이 자식 요소로 상속되었을 때의 계산 방식이 달라짐
- number 부모 요소의 숫자 값이 그대로 상속됩니다. 즉, 자식 요소에서도 또 한 번 자식 요소의 font-size를 기준으로 계산된 값을 가짐
- % 부모 요소에서 %값이 그대로 상속되는 것이 아니고, %에 의해 이미 계산된 px 값이 상속됨
number를 선언할 때 계산된 값이 아닌 숫자값을 상속하기 때문에 숫자값을 사용하면 부모 엘리먼트에 계산된 값 대신 비율을 그대로 상속 받을 수 있으므로 가능하면 단위가 없는 값을 사용하는 것이 더 좋음
{부모요소에 number로 선언된 경우} -> 동일한 값을 부여 받아 자식 font-size로 적용하면 됨
{부모요소에 %로 선언된 경우} -> 부모 font-size의 값으로 계산됨
