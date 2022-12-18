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
* 복수의 매개변수를 사용하는 함수 (Functions With Multiple Parameters)
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
* 반환 값이 없는 함수 (Functions Without Return Values)
```swift
func greet(person: String) {
    print("Hello, \(person)!")
}
    greet(person: "Dave")
    //prints "Hello, Dave!" 
```