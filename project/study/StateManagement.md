## State

React에서 State는 컴포넌트 안에서 관리

## 컴포넌트 간 정보 공유

- 자식 컴포넌트 간 **다이렉트로 데이터 전달이 불가능**
- **부모 컴포넌트**를 통해 주고받음
- 자식이 많아지면 state management가 복잡해짐
- 상태를 관리하는 상위 컴포넌트에서 계속 내려받음 ⇒ **Props Drilling 이슈**

**#Props Drilling**: 하위 컴포넌트로 전달하는 용도로만 쓰이는 컴포넌트를 거치면서 다른 컴포넌트로 데이터를 전달하는 과정

## State Management

- react에서는 전역적으로 상태를 관리할 수 없기 때문에 props를 통해 필요한 컴포넌트까지 전달이 필요
- 프로젝트 규모가 커지고 요구사항이 늘어남 ⇒ 상태 교환이 증가하면서 개발과 유지보수가 어려움

## State Management Library

- 전역 상태 저장소 제공
- Props Drilling 이슈 해결
    - 전역 상태 저장소를 통해 어디서든 접근할 수 있기 때문에 이슈 해결
- 라이브러리: **React Context, Redux, MobX**
