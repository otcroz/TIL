### SetBackground 색상 코드 적용하기
객체.setBackground("색상코드") 오류가 나서 색상 코드를 적용하는 방법을 찾아봄

Color.parseColor("색상코드")를 적용하면 된다.

``` kotlin

객체.setBackground(Color.parseColor("색상코드"))

```
