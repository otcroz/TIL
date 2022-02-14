## 리액트 스터디 궁금한 점

### ❓Question1
> 렌더링 과정에서 이전의 virtual DOM 이랑 새로운 virtual DOM이랑 비교 후 실제 DOM에 적용하는 것인가?

- 데이터를 업데이트하면 전체 UI를 virtual DOM에 업데이트
- ***현재 virtual DOM***과 ***이전의 virtual DOM에 있던 내용***을 비교. 즉 **실제 DOM의 데이터**와 비교.
- 다른 부분만 실제 DOM에 적용


### ❓Question2
> ReactDOM.render와 render의 차이?

- ReactDOM.render은 **index.js**에서 사용, 리액트 코드를 DOM에 붙이는 역할을 수행
- render은 UI 렌더링 역할
- 즉, 컴포넌트들은 render 함수를 통해 렌더링을 실행하고, 최종적으로 **index.js**에서 **렌더링 + DOM**에 코드를 붙이는 역할을 수행


### ❓Question3
> var, const, let의 사용법?

```
function myFunction(){
  var a = "hello";
  if(true){
    var a = "bye";
    console.log(a) //bye
  }
  console.log(a) //bye
}

```
```
function myFunction(){
  let a = "hello";
  if(true){
    let a = "bye";
    console.log(a) //bye
  }
  console.log(a) //hello
}

```

- ES6 이전에는 var을 사용: var은 scope가 **함수 단위**
- ES6 이후에 나온 const, let의 scope는 **블록 단위** 
  - const: 한 번 선언하면 값을 재설정 할 수 없음
  - let: 값 재설정 가능, var가 사용법이 같다.


### ❓Question4
> 클래스 컴포넌트에서는 defaultProps와 propTypes를 사용할 때 앞에 static을 붙이는 이유?

- static을 붙이지 않으면 오류가 발생한다. 이 부분은 직관적으로 이해해야 하는 부분인 듯.


