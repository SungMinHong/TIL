## 추상클래스와 인터페이스
### 추상클래스
추상 클래스는 클래스 내 abstract로 정의된 ‘추상 메소드’가 하나 이상 포함된 경우를 말한다. 상속을 통해 사용한다.
### 인터페이스
인터페이스는 모든 메소드가 추상 메소드인 경우이다. 단 자바 8에서는 default 키워드를 이용해서 일반 메소드의 구현도 가능하다. 인터페이스는 구현을 강제한다. 자바에서는 다중 상속을 지원하지 않기 때문에도 사용하기도 한다.

<br/>
+) 테스트 결과 interface에 동일한 default 메서드를 선언 시에 다이아몬드 상속 문제가 발생한다. 
