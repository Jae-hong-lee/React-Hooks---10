# useconfirm


## 수정

- confirm 오류
`confirm(message)`-> `window.confirm(message)`
앞에 window를 붙여주기

> 현재 크롬으로 코드샌드박스를 쓰신다면 confirm 창이 막힌 것 뿐이니 당황하지 마세요. 요게 막혀서 confirm 코드가 항상 false만 뿜어, 코드가 돌지 않는 것 뿐이에요. 해결책은 다른 브라우저(예:파이어폭스)는 아직은 안 막혀 있어서 테스트 가능해요.

2021년 8월 1일, 현재 크로스오리진 다이얼로그창이 막혀있어요. 지금의 UX, UI상황에선 javascript dialogs가 URL에서 오냐 embedded된 페이지에서 오냐 구분하지 못하기 때문에 혼란스러워 도용할 수 있고, cross-origin iframe 에서의 js dialogs의 낮은 사용 빈도(전체사용량의 0.003%)를 볼 때 사이트에서 일반적으로 요구되는 주된 기능이 아니어서 기능을 중지한다고 크롬 측이 설명하고 있음.


### 다른사람 코드
```js
const confirmAction = () => {
if (window.confirm(message)) {
onConfirm();
} else {
onCancel();
}
};
는
const confirmAction = () => {
if (window.confirm(message)) {
onConfirm();
} else {
// try, catch를 통해 프로그램이 터지는 걸 방지
try {
onCancel();
} catch (error) {
return;
}

}
};
```

로 수정해 봤습니다. onCancel() 실행 부분은 onCancel이 필수가 아니라 onCancel이 없는 경우에도 Cancel 누르면 실행 될건데 예외 발생으로 프로그램 터질 겁니다. 그래서 예외처리 넣어서 프로그램 터지는걸 방지했습니다.