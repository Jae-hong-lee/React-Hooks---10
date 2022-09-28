# use-title

문서 제목을 업데이트

## 사용법

```js
import React from "react";
import useTitle from "useTitle";

function App() {
  useTitle("Welcome");
  return <h1>Welcome</h1>;
}
```

### Arguments

| Argument | Type   | Description                                | Required |
| -------- | ------ | ------------------------------------------ | -------- |
| title    | string |  문서 제목을 업데이트 | yes      |