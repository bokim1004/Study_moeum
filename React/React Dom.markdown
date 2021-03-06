## React Dom은 컴포넌트 혹은 JSX요소를 DOM에 렌더한다.

### DOM(문서객체모델)

문서 객체란`<html>`이나`<body>`같은 html문서의 태그들을 javascript가 이용할 수 있는 객체(object)로 만들면 문서 객체라고 한다.
왜 모델이 뒤에 붙여졌을까? 문서 객체를 '인식하는 방식'이라고 해석할 수 있다.

자바스크립트와 HTML은 직접적으로 소통할 수 없다. DOM은 이러한 문제를 해결하기
위해 개발되었다. 웹페이지를 열었을 때, 브라우저 엔진은 모든 컨텐츠를
자바스크립트가 이해할 수 있는 포맷으로 변형시킨다. 이것이 `DOM tree` 다.

브라우저에서는 HTML코드를 DOM이라는 객체 형태의 모델로 저장. 그렇게 저장된 정보를 DOM Tree라고 하며 결국 HTML element는 tree형태로 저장된다.

DOM은 tree형식의 자료구조를 가지고 있다.
DOM tree구조는 해당 HTML의 구조와 같다. DOM은 사용자의 브라우저에 의해 생성되고
저장된 웹페이지의 논리적인 표현법. 브라우저가 사이트의 HTML을 가져와 DOM으로
변형한 후 사용자들이 볼 수 있도록 사용자의 화면에 DOM을 그린다.

브라우저에서 DOM의 변화를 감지할 때마다, 브라우저는 전체페이지를 다시 그린다.
가상돔은 리액트가 자신을 대표하는 DOM을 자바스크립트 객체 형태로 생성한
것이다. DOM에 변화가 있을 때마다 리액트는 이 자바스크립트 객체의 복사본을
만들고, 해당 복사본에 변화를 준 뒤, 어떤 곳이 수정되었는지 알기 위해 원본과
복사본의 자바스크립트 객체를 비교한다. 그 후에 이 변화를 브라우저에 알리고
DOM에 수정된 부분들만 다시 그려진다.

참고로 리액트 컴포넌트는 기본적으로 부모 컴포넌트가 리렌더링되면
자식컴포넌트또한 리렌더링된다.(바뀐 내용이 없어도) 실제 DOM에 변화가 반영된
것은 바뀐 내용이 있는 컴포넌트에만 해당한다. 하지만 virtual DOM에는 모든 걸
다 렌더링하고 있다는 것이다.
