

### 웹페이지가 느려지는 원인 분석
#### 리렌더링이 발생하는 경우
- 자신이 전달받은 props가 변경
- 자신의 state가 바뀔 때
- 부모 컴포넌트가 리렌더링
- forceUpdate 함수가 실행

> App.js에서 리렌더링 발생, TodoList 컴포넌트가 리렌더링 되고 TodoList 안에 있는 컴포넌트들도 리렌더링 됨

리렌더링이 발생할 때, 부모 컴포넌트가 리렌더링 되면 자식 컴포넌트도 모두 렌더링, <br>
자식 > 자식 > ... => 무수한 컴포넌트들이 리렌더링된다. <br>
이는 컴포넌트의 개수가 많아지면 웹페이지의 속도가 느려지면서 성능이 저하됨. <br>
<hr>

### 컴포넌트 성능을 최적화하는 방법
클래스 컴포넌트에서 리렌더링 방지하는 방법: shouldComponentUpdate 라이프사이클 사용, <br>
하지만 함수 컴포넌트에서는 라이프사이클 메서드를 사용할 수 없다.
- React.memo
- react-virtualized

#### React.memo
컴포넌트를 만들고 리렌더링하지 않을 컴포넌트에 React.Memo로 감싸주면 됨
```
import React from 'react';
.
.
.
export default React.memo(TodoList);
```

#### react-virtualized
컴포넌트에서 스크롤되기 전에 보이지 않는 컴포넌트는 렌더링하지 않음
해당 스크롤 위치에서 보여 주어야 할 컴포넌트를 자연스럽게 렌더링함.

