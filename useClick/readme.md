# useClick

reference는 component의 어떤 부분을 선택할 수 있는 방법이다.
모든 component는 reference prop을 가지고 있다.
`useRef()`는 `document.getElementById()` 와 같은 기능을 한다.
htmlTag에 `ref={이름}` 와 같이 사용한다.
reference는 `{current: HTMLHeadingElement}` 의 형식으로 값을 반환한다.
`useEffect`에서 return한 함수는 componentWillUnmount 때 호출된다.
참고로 `useEffect`에서 return한 함수를 cleanup function(클린업 함수)라고 부른다.

