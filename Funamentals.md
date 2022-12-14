## Fundamentals

- 사용하는 쪽에서 명확하다고 느끼게 하는 것이 가중 중요한 목표입니다. (at the point of use)
- 설계를 평가할 때, 선언한 쪽만 보고 평가하는 경우는 거의 없다. (사용자가 어떻게 사용하는 가로 판단할 수 있다.) 
- 명확한 것이 간결한 것보다 중요하다. (코드를 짧게 작성하는 것이 목표가 아니다.)

> API를 간단히 설명하는게 어렵다면, 설계를 잘 못 했을수도 있다. 

1. 요약으로 주석을 시작해라. API 선언과 요약만으로 완전히 이해되는 경우가 존재한다.
```swift 
/// Returns a "view" of `self` containing the same elements in
/// reverse order.
func reversed() -> ReverseCollection
```

2. 필요한 경우, 문단이나 bullet items(- 으로 구분되는 문장)을 추가해라. 문단은 빈줄로 구분하고 완전한 문장을 사용한다.
```swift 
/// Writes the textual representation of each    ← Summary (요약 정보)
/// element of `items` to the standard output.
///                                              ← Blank line (빈줄)
/// The textual representation for each item `x` ← Additional discussion
/// is generated by the expression `String(x)`.
///
/// - Parameter separator: text to be printed    ⎫
///   between items.                             ⎟
/// - Parameter terminator: text to be printed   ⎬ Parameters section
///   at the end.                                ⎟
///                                              ⎭
/// - Note: To print without a trailing          ⎫
///   newline, pass `terminator: ""`             ⎟
///                                              ⎬ Symbol commands
/// - SeeAlso: `CustomDebugStringConvertible`,   ⎟
///   `CustomStringConvertible`, `debugPrint`.   ⎭
public func print(
  _ items: Any..., separator: String = " ", terminator: String = "\n")
  ```
