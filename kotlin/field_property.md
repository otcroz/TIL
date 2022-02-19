### 필드와 프로퍼티
- 필드(field): 값 자체
- 프로퍼티(property): 필드 + 접근자

### 코틀린의 변수는 "프로퍼티"
- 변수에 세터(setter)와 게터(getter)가 내장되어 있음
- 변수만 사용하더라도 내부적으로 세터와 게터가 호출됨

```java
public class User{
  private String name;
  public String getName(){
    return name;
  }
  
  public void setName(String name){
    this.name = name;
  }
}
```
#### 자바에서 User 클래스 내에 있는 name 변수 접근하기
getName(), setName() 사용하기
```java
user.setName("kkang")
println(user.getName())
```

#### 코틀린에서 User 클래스 내에 있는 name 변수 접근하기
변수만을 사용하여 접근 가능, 실제로는 게터/세터 함수 호출
```kotlin
user.name = "kkang"
println(user.name)
```
