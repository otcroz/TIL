## 리팩토링이란?

### 1. 정의

- 외부 동작을 바꾸지 않으면서 코드의 가독성과 유지보수성
    
    ⇒ 내부 소프트웨어의 구조 개선
    
    ⇒ 소프트웨어를 쉽게 이해, 적은 비용으로 수정
    

### 2. 목적

- 코드 중복 제거, 수정 용이성 향상, 가독성 향상
- 겉으로 보이는 소프트웨어의 기능을 변경X
- 프로그램 개발 속도 향상

### 🎩두 개의 모자: Two Hats

![image](https://user-images.githubusercontent.com/79989242/175866316-0969e88a-2c8c-40f8-a16e-c271620959b1.png)

- **Adding Function**: 기존 코드를 건드리지 X, 새로운 기능 추가
- **Refactoring**: 기능 추가X, 코드 구조 변경

## 언제 리팩토링을 해야 하는가?

- **삼진 규칙: The Rule Of Three**
    - ❓**The Rule Of Three**
        
        is a code refactoring rule of thumb to decide when a replicated piece of code should be replaced by a new procedure. It states that you are allowed to copy and paste the code once, but that **when the same code is replicated three times**, it should be extracted into a new procedure. The rule was introduced by Martin Fowler in his text "Refactoring" and attributed to Don Roberts.
        
        => [Rules Of Thumb](https://wou.edu/las/cs/csclasses/cs161/Lectures/rulesofthumb.html)
        
- 기능을 추가할 때
- 버그를 수정할 때
- 코드 리뷰를 진행할 때

[리팩토링이란?](https://ikkison.tistory.com/82)
