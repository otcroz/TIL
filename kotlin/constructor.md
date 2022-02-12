
### 주 생성자
#### 주 생성자의 선언
```
class User{
}
```
개발자가 클래스의 주 생성자 선언을 하지 않으면 컴파일러가 매개변수가 없는 주 생성자를 자동으로 추가.
```
class User(){
}
```

```
class User constructor(){
}
```

```
class User(name: String, count: Int){
}
```

#### 주 생성자의 본문
```
class User(name: String, count: Int){
  init{
    println("I am init....")
  }
}
```
- 객체를 선언할 때 자동으로 실행
- 클래스 선언부에 있는 주 생성자의 본문을 작성할 때 사용

#### 생성자의 매개변수를 클래스의 매개변수로 사용
```
class User(val name: String, var count: Int)
```
- 클래스 선언부에 var 또는 val 키워드로 변수를 선언
- 주 생성자에서 유일하게 매개변수를 var, val 키워드로 선언할 수 있음

### 보조 생성자
```
class User(name: String) { // 주 생성자를 선언부에
    constructor(name: String, count: Int): this(name){
        println("Constructor(name: String) call...")
    }
    constructor(name: String, count: Int, email: String): this(name, count){
        println("Constructor(name: String, email: String) call...")
    }

}
fun main(){
    val user1 = User("kkang")
    val user2 = User("kkang", 10)
}
```
- ```constructor``` 을 사용하여 선언
- 주 생성자와 보조 생성자를 모두 생성 → 보조 생성자에서 주 생성자 호출
- this()를 사용하여 주 생성자 호출
