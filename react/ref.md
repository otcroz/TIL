### ref : DOM에 이름을 다는 방법

#### ref는 *"DOM을 직접적으로 건드려야 할 때"* 사용한다. 
- 클래스형 컴포넌트: ref 
- 함수형 컴포넌트: ref를 사용하기 위해 Hooks를 사용해아함



#### 클래스형 컴포넌트에서 ref
- **콜백 함수**를 통한 ref 설정
```
<input ref={(ref)=>{this.input=ref}} />
```
- **createRef**를 통한 ref 설정
```
input = React.createRef();
```

#### 컴포넌트에 ref 달기
- 컴포넌트 내부에 있는 DOM을 컴포넌트 외부에서 사용할 때 사용한다.
- DOM에 ref를 다는 방법과 같다.
```
<MyComponent 
  ref={(ref)=>{this.MyComponent=ref}}
/>
```
컴포넌트 내부의 메서드 및 멤버 변수에 접근 가능
내부의 ref에 접근 가능
ex) MyComponent.handleClick, MyComponent.input
