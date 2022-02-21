### get() set() 함수

```java
public class User{
  private String getName(){
    return name;
  }
  
  public void setName(String name){
    this.name = name;
  }
}

```
#### java
```java
user.setName("YooSoo");
println(user.getName())
```
#### kotlin
```kotlin
user.name = "YooSoo"
println(user.name)
```

- kotlin의 변수는 프로퍼티(필드 + 접근지정자) 단위를 가짐
- kotlin은 변수에 게터와 세터가 포함되어 있음
- 자바에서 private로 선언된 변수에 접근할 수 있음, 이때 변수에는 get, set 함수가 호출


### 코틀린의 프로퍼티와 get(), set() 함수

- 변수
  - val로 선언한 변수(불변): getter만 생성
  - var로 선언한 변수(가변): setter/getter 생성
  - private로 선언한 변수: getter/setter가 생성되지 않는다. 
