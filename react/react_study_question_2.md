### ❓Question 1
> "this.setState를 사용한다고 해서 state 값이 바로 바뀌지는 않기 때문입니다." 무슨 소리일까?

- this.setState()에서 setState가 객체의 값을 설정할 때, 객체 내부의 키 값이 동일한 경우가 있을 수 있음.
- 키값이 동일한 경우 setState()는 일괄적으로 모아서 처리하는 경향이 있어,  마지막에 setState() 처리한 것만 업데이트된다.


### ❓Question 2
> 클래스의 임의 메서드가 특정 HTML요소의 이벤트로 등로되는 과정에서 바인딩을 하는 이유?

- 메서드와 this의 관계가 끊어져서 this가 undefined를 가리킨다.
- 컴포넌트 자신을 가리키기 위해 바인딩 작업 실행

### ❓Question 3
> 클래스 컴포넌트에서 바인딩을 적용하지 않으면 this에서 undefind를 반환하는 이유는?

- class 내부는 암묵적으로 strict mode가 적용
- this는 undifind로 반환되는 것이 원칙이다.
