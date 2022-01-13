## 자바 교재: <명품 자바 프로그래밍> 실습문제 4장
#### 12번 문제) 콘서트 예매 시스템 구현하기



##### ConcertReserveSystem: 콘서트 좌석 예약 시스템의 전체적인 기능
- S_seat, A_seat, B_seat: 각 등급(타입)에 따른 좌석
- seat: 각 등급의 따른 좌석들을 seat 배열에 모아둠.
- ConcertReserveSystem: 생성자 메서드, main 메서드에서 생성자를 호출한다. 전체적인 영화 시스템의 기능을 담당.


```
public class ConcertReserveSystem {
	Scanner s = new Scanner(System.in);
	String[] S_seat = { "---", "---", "---", "---", "---", "---", "---", "---", "---", "---" };
	String[] A_seat = { "---", "---", "---", "---", "---", "---", "---", "---", "---", "---" };
	String[] B_seat = { "---", "---", "---", "---", "---", "---", "---", "---", "---", "---" };
	String[][] seat = { S_seat, A_seat, B_seat };
	String[] class_name = { "S", "A", "B" };

	ConcertReserveSystem() { // 생성자
		System.out.println("명품콘서트홀 예약 시스템입니다.");

		while (true) {
			int select = inputNum(); // 입력받기

			// select에 따른 함수 실행
			if (select == 1)
				reserve();
			else if (select == 2)
				inquire();
			else if (select == 3)
				cancel();
			else
				break;

			System.out.println();
		}
	}

	private int inputNum() { // 숫자 선택
		System.out.print("예약:1, 조회:2, 취소:3, 끝내기:4 >> ");
		int select = s.nextInt();

		return select;
	}
```
##### reserve 메서드: 콘서트 좌석 예약 기능
- class_seat() 메서드를 통해 특정 등급의 좌석을 선택
- 이름과 좌석 번호를 입력받아서 좌석 예약

```
	private void reserve() { // 예약
		int seat_sel = class_seat(); // 특정 좌석 선택 및 출력 함수

		System.out.print("이름 >> ");
		String name = s.next();
		System.out.print("번호 >> ");
		int seat_num = s.nextInt();

		// 예약하기
		seat[seat_sel -1][seat_num - 1] = name;

		System.out.println("예약이 완료되었습니다.");
	}
```
##### inquire 메서드: 콘서트 조회 기능
- for 이중 반복문을 사용하여 전체 콘서트 좌석을 조회한다.

```
	private void inquire() { // 조회
		for (int i = 0; i < 3; i++) {
			for (int j = 0; j < 10; j++) {
				System.out.print(seat[i][j] + " ");
			}
			System.out.println();
		}

		System.out.println("조회를 완료하였습니다.");
	}
```
##### cancel 메서드: 콘서트 좌석 취소 기능
- class_seat() 함수를 사용하여 특정 좌석을 선택
- 이름을 입력한 후 해당하는 이름의 좌석 취소 작업
- 해당 이름으로 예약한 좌석이 없는 경우 이에 대한 출력

```
	private void cancel() { // 취소
		int seat_sel = class_seat(); // 특정 좌석 선택 및 출력 함수
		System.out.print("이름 >> ");
		String name = s.next();

		// 취소하기
		for (int i = 0; i < seat[seat_sel -1].length; i++) {
			if (name.equals(seat[seat_sel -1][i])) {
				seat[seat_sel -1][i] = "---";
				System.out.println("예약 취소가 완료되었습니다.");
				return;
			}
		}

		System.out.println(name + "으로 예약된 좌석이 없습니다.");

	}
```
##### class_seat 메서드: 좌석 등급 선택
- S, A, B 중 좌석 등급을 선택
- 해당하는 좌석을 조회 후 출력(디스플레이)

```
	private int class_seat() {
		// 좌석 등급 선택
		System.out.print("좌석구분 S(1), A(2), B(3) >> ");
		int seat_sel = s.nextInt();

		// 특정 좌석 출력
		System.out.print(class_name[seat_sel - 1] + ">> ");
		for (int i = 0; i < seat[seat_sel -1].length; i++) {
			System.out.print(seat[seat_sel -1][i] + " ");
		}
		System.out.println();

		return seat_sel;
	}
}
```

#### 보완점
- reserve 메서드에서 좌석을 예약할 때, 이미 자리가 있으면 이에 대한 예외 처리 추가 구현
- 사용자에게 공연 목록을 보여준 후, 공연에 따라 좌석 예약이 가능하도록 구현
- 특정 좌석을 골랐을 때, 좌석이 찬 경우 이에 대한 출력 필요
- 클래스를 더 나누어서 구현(객체지향적)
