# [Swift문법] Dictionary
* [Key : Value]가 함께 저장되는 자료구조이며
정렬되지 않는 컬렉션이다.
* 따라서 Dictionary를 출력하면 저장/삽입 순서와 상관없이 출력된다.
* 값(Value)은 중복되도 되지만, 키(Key)는 중복되면 안된다.
* 모든 키와 값의 타입은 같아야한다.

+ Dictionary는 Array와 같이 구조체로써 Stack에 저장된다. <- 이건 공부해봐야겠다.

Dictionary를 생성할 때 타입추론으론 빈 딕셔너리를 생성불가하니 항상 값을 대입해야한다.
// 1. 타입 추론으로 생성하기
var dict1 = ["height": 165, "age" : 100] -> complete
var dict2 = [:] -> Error

// 2. 타입 Annotation으로 생성하기 (Annotation = 주석)
var dict3: [String: Int] = [:]   -> complete          // 빈 딕셔너리 생성
var dict4: [String: Int] = ["height": 165, "age" : 100]   -> complete

// 3. 생성자로 생성하기
var dict5 = Dictionary<String, Int>()                  // :이 아닌 ,로 명시
var dict6 = [String: Int]()

// 4. 여러 타입을 저장하는 딕셔너리 생성하기
var dict7: [String: Any] = ["name": "Sodeul", "age": 100]
var dict8: NSDictionary = ["name": "Sodeul", "age": 100]
