
## [NEXTSTEP] FINPC 2021년 U-Space 고급 프로그래밍

| Week | 세미나 | 과제 |커리큘럼 내용 |
| ------ | -- | -- |----------- |
| 1주차 | ☑️ | ☑️ | 숫자 야구 - 프리코스 |
| 2주차 | ☑️ | ☑️ | 자동차 경주 - 단위 테스트 |
| 3주차 |  |  | 로또 - TDD |
| 4주차 |  |  | 블랙잭 - 상속, 인터페이스 |
| 5주차 |  |  | 체스 - FP, OOP |

## 🧮 문자열 계산기
- [기능 구현 목록](https://github.com/LEE-Yerim/java-racingcar/blob/step2/src/StringCalculator.md)
- [main](https://github.com/LEE-Yerim/java-racingcar/tree/step2/src/main/java/stringcalculator)
- [test](https://github.com/LEE-Yerim/java-racingcar/tree/step2/src/test/java/stringcalculator)

기능 요구 사항
사용자가 입력한 문자열 값에 따라 사칙 연산을 수행할 수 있는 계산기를 구현해야 한다.
문자열 계산기는 사칙 연산의 계산 우선순위가 아닌 입력 값에 따라 계산 순서가 결정된다. 즉, 수학에서는 곱셈, 나눗셈이 덧셈, 뺄셈 보다 먼저 계산해야 하지만 이를 무시한다.
예를 들어 "2 + 3 * 4 / 2"와 같은 문자열을 입력할 경우 2 + 3 * 4 / 2 실행 결과인 10을 출력해야 한다.

프로그래밍 요구 사항
자바 코드 컨벤션을 지키면서 프로그래밍한다.
기본적으로 Google Java Style Guide을 원칙으로 한다.
단, 들여쓰기는 '2 spaces'가 아닌 '4 spaces'로 한다.
indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메소드)를 분리하면 된다.
3항 연산자를 쓰지 않는다.
함수(또는 메소드)가 한 가지 일만 하도록 최대한 작게 만들어라.

힌트
테스트할 수 있는 단위로 나누어 구현 목록을 만든다.

덧셈
뺄셈
곱셈
나눗셈
입력값이 null이거나 빈 공백 문자일 경우 IllegalArgumentException throw
사칙연산 기호가 아닌 경우 IllegalArgumentException throw
사칙 연산을 모두 포함하는 기능 구현
공백 문자열을 빈 공백 문자로 분리하려면 String 클래스의 split(" ") 메소드를 활용한다. 반복적인 패턴을 찾아 반복문으로 구현한다.

AssertJ Exception Assertions를 참고한다.
```
assertThatThrownBy(() -> {
    List<String> list = Arrays.asList("String one", "String two"));
    list(2);
}).isInstanceOf(IndexOutOfBoundsException.class)
  .hasMessageContaining("Index: 2, Size: 2");

```
```
assertThatExceptionOfType(IndexOutOfBoundsException.class)
  .isThrownBy(() -> {
      // ...
}).hasMessageMatching("Index: \\d+, Size: \\d+");

```
```
assertThatIOException().isThrownBy(() -> {
    // ...
});

```
AssertJ의 Assertions
```
import static org.assertj.core.api.Assertions.assertThat;

```
테스트 데이터 전달
Guide to JUnit 5 Parameterized Tests
```
@ParameterizedTest
@ValueSource(strings = {"", "  "})
void isBlank_ShouldReturnTrueForNullOrBlankStrings(String input) {
    assertTrue(Strings.isBlank(input));
}

```

## 🚗 자동차 경주 게임
- [기능 구현 목록](https://github.com/LEE-Yerim/java-racingcar/blob/step2/src/RacingCarGame.md)
- [main](https://github.com/LEE-Yerim/java-racingcar/tree/step2/src/main/java/racingcargame)
- [test](https://github.com/LEE-Yerim/java-racingcar/tree/step2/src/test/java/racingcargame)
