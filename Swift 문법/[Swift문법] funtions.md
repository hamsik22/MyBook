# [Swift문법] functions
## 정의와 호출 (Defining and Calling Functions)<br>
함수를 선언할 때는 앞에 func 키워드를 붙이고 (person: String)처럼 매개변수와 형태 그리고 -> String 처럼 반환형을 정의한다.<br>
ex) func 함수명(매개변수: 타입) -> 반환형 타입 { }
타
예시 1
```swift
 func greet(person: String) -> String {
    let greeting = "Hello," + person + "!"
    return greeting 
 }
    print(gree(person: "Anna"))
    // prints "Hello, Anna!"
```
예시 2
```swift
func greetAgain(person: String) -> String {
    return "Hello again," + person + "!"
}
    print(greetAgain(person: "Anna"))
    // prints "Hello again, Anna!"
```

## 함수 매개변수와 반환 값(Function Parameters and Return Values)
* 매개변수가 없는 함수(Functions without Parameters)<br>
예시
```swift
func sayHelloWorld() -> String {
    return "hello, world"
}
print(sayHelloWorld())
// prints "hello, world"
```

* 복수의 매개변수를 사용하는 함수 (Functions with Multiple Parameters)
```swift
func greet(person: String, alreadyGreeted: Bool) -> String {
    if alreadyGreeted {
        return greetAgain(persin: person)
    } else {
        return greet(person: person)
    }
}
print(greet(person: "Tim", alreadyGreeted: true))
// prints "Hello again, Tim!"
```
* 반환 값이 없는 함수 (Functions without Return Values)
```swift
func greet(person: String) {
    print("Hello, \(person)!")
}
    greet(person: "Dave")
    //prints "Hello, Dave!" 
```

* 복수의 값을 반환하는 함수 (Functions with Multiple Return Values)
튜플을 함수의 반환 값으로 사용할 수 있다.<br>
튜플이란 셀 수 있는 수량의 순서 있는 열거이다.
```swift
func minMax(array: [Int]) -> (min: Int, max: Int) {
    var currentMin = array[0]
    var currentMax = array[0]
    for value in array[1..< array.count] {
        if value < currentMin {
            currentMin = value
        } else if value > currentMax {
            currentMax = value
        }
    }
    return (currentMin, currentMax)
}
```
반환 값의 인자를 반환 값을 접근하는 접근자로 사용할 수 있다.
```swift
let bounds = minMax(array: [8, -6, 2, 109, 3, 71])
print("min is \(bounds.min) and max is \(bounds.max))
// Prints "min is -6 and max is 109"
```

* 옵셔널 튜플 반환형 (Optinal Tuple Return Types)
우의 반환 값과 달리 반환 값에 ? 물음표가 붙어있다.<br>
ex) (min: Int, Max: int)?
```swift
func minMax(array: [Int]) -> (min: Int, max: Int)? {
    if array.isEmpty { return nil}
    var currentMin = array[0]
    var currentMax = array[0]
    for value in array[1..<array.count] {
        if value < currentMin {
            currentMin = value
        } else if value > currentMax {
            currentMax = value
        }
    }
    return (currentMin, currentMax)
}
```
실제 반환 값에 접근하기 위해서는 if let과 같은 옵셔널 체인을 사용하거나 강제 언랩핑을 해야 한다.
예시.
```swift
if let bounds = minMax(array: [8, -6, 2, 109, 3, 71]) {
    print("min is \(bounds.min) and max is \(bounds.max)")
}
// Prints "min is -6 and max is 109"
```