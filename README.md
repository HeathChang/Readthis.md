# Good Articles to read


## SWIFT

#### 1. [Choosing Between Structures and Classes]<br/> https://developer.apple.com/documentation/swift/choosing-between-structures-and-classes


## JS
### 1. 고차 함수(Higher-Order Function):
고차 함수란, 다른 함수를 인자로 받거나 함수를 반환하는 함수를 말합니다. 자바스크립트에서 함수는 일급 객체이므로 함수를 변수로 다루거나 인자로 전달하는 것이 가능합니다. 고차 함수를 사용하면 함수의 재사용성을 높이고 추상화를 통해 코드를 간결하고 유연하게 작성할 수 있습니다.
예시:

```
// 고차 함수 예시 1: 함수를 인자로 받는 고차 함수
function applyOperation(x, y, operation) {
  return operation(x, y);
}

function add(a, b) {
  return a + b;
}

function multiply(a, b) {
  return a * b;
}

console.log(applyOperation(2, 3, add)); // Output: 5
console.log(applyOperation(2, 3, multiply)); // Output: 6

// 고차 함수 예시 2: 함수를 반환하는 고차 함수
function makeMultiplier(multiplier) {
  return function (x) {
    return x * multiplier;
  };
}

const double = makeMultiplier(2);
console.log(double(5)); // Output: 10
```


### 2. 자바스크립트 반복 실행 방법:

자바스크립트에서 반복 실행을 위해 다양한 방법이 있습니다. 주요한 방법으로는 다음과 같습니다.
  1) for문: 가장 기본적인 반복문으로, 특정 조건이 참인 동안 코드 블록을 반복 실행합니다.
  2) while문: 조건이 참인 동안 코드 블록을 반복 실행합니다.
  3) do-while문: 코드 블록을 실행한 후 조건을 검사하여 조건이 참이면 반복 실행합니다.
  4) forEach 메서드: 배열의 각 요소에 대해 콜백 함수를 호출합니다.
  5) map 메서드: 배열의 각 요소에 대해 콜백 함수를 호출하고, 새로운 배열을 반환합니다.
  6) for...of 문: 배열이나 이터러블 객체를 순회합니다.

특징:
for문: 초기값, 조건식, 증감식 등을 잘 설정하여 사용하면 좋습니다.
forEach와 map 메서드: 콜백 함수를 사용하므로 간결하며 가독성이 높습니다.
for...of 문: 배열 또는 이터러블 객체의 요소를 직접 사용하기 용이합니다.
Promise의 순차 실행:
Promise를 사용하여 비동기 작업을 순차적으로 실행하려면 then 메서드를 이용합니다. then 메서드는 이전 Promise가 fulfilled(이행)되면 다음 작업을 처리합니다.

```
function asyncTask1() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Async Task 1 Done");
      resolve();
    }, 1000);
  });
}

function asyncTask2() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Async Task 2 Done");
      resolve();
    }, 500);
  });
}

function asyncTask3() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Async Task 3 Done");
      resolve();
    }, 800);
  });
}

// 순차 실행
asyncTask1()
  .then(() => asyncTask2())
  .then(() => asyncTask3());

```

### 3. 자바스크립트에서 함수의 평가:
함수의 평가란 함수가 호출되어 실행되는 것을 의미합니다. 함수 호출은 함수 이름 뒤에 괄호 ()를 붙여서 수행합니다. 함수를 호출하면 함수 내부의 코드가 실행되고, 필요에 따라 인자(argument)를 전달할 수 있습니다.

예시:
```
function greet(name) {
  console.log("Hello, " + name + "!");
}

// 함수 호출
greet("John"); // Output: Hello, John!
greet("Alice"); // Output: Hello, Alice!
```



### 4. OOP의 특징 및 예시:
객체 지향 프로그래밍(OOP)의 주요 특징은 다음과 같습니다:
  1) 캡슐화(Encapsulation): 관련 있는 데이터와 메서드를 하나의 단위로 묶고, 외부에서 직접 접근을 제한하는 것을 말합니다.
  
  2) 상속(Inheritance): 클래스가 다른 클래스의 속성과 메서드를 상속받을 수 있게 해주는 개념입니다.
  
  3) 다형성(Polymorphism): 한 요소(메서드 또는 클래스)가 여러 다른 방식으로 동작할 수 있는 능력을 의미합니다.
  
  4) 추상화(Abstraction): 객체들의 공통적인 특징을 추출하여 모델을 만드는 과정을 말합니다.

예시:

```
// 클래스 정의
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(this.name + " makes a sound");
  }
}

class Dog extends Animal {
  speak() {
    console.log(this.name + " barks");
  }
}

class Cat extends Animal {
  speak() {
    console.log(this.name + " meows");
  }
}

// 다형성 예시
const animals = [new Dog("Buddy"), new Cat("Misty")];
animals.forEach(animal => animal.speak());
// Output:
// Buddy barks
// Misty meows

``` 

### 4. 버추얼 돔(Virtual DOM) 사용을 피해야 하는 경우:
버추얼 돔은 리액트와 같은 프론트엔드 라이브러리/프레임워크에서 사용되는 기술로, 변경된 부분만 실제 DOM에 반영하여 성능을 향상시킵니다. 그러나 아래와 같은 경우에는 버추얼 돔을 사용하는 것이 적절하지 않을 수 있습니다:
간단한 정적인 페이지: 변경이 거의 없고 정적인 페이지의 경우, 버추얼 돔을 사용하는 것은 비효율적일 수 있습니다.

강력한 하드웨어 요구: 버추얼 돔은 추가적인 계산이 필요하므로, 강력한 하드웨어가 없는 환경에서는 성능 향상보다는 더 큰 부하를 주는 결과가 발생할 수 있습니다.

적은 양의 데이터: 데이터 양이 적고 단순한 경우에는 버추얼 돔을 사용할 필요가 없을 수 있습니다.

다른 렌더링 기술 사용: 이미 다른 렌더링 기술을 사용 중이거나 특정 프레임워크가 제공하는 렌더링 기능을 활용하고 있다면, 버추얼 돔을 사용하지 않아도 됩니다.




### 5. 훅 규칙 위반 에러:
React의 훅 규칙 위반 에러는 다음과 같은 경우에 발생합니다:
훅을 조건문, 반복문, 중첩 함수 안에서 호출한 경우
React 함수 컴포넌트 또는 커스텀 훅의 최상위 수준이 아닌 곳에서 훅을 호출한 경우
이러한 규칙을 위반하면 React는 컴포넌트의 상태를 올바르게 추적할 수 없으며, 예기치 않은 동작을 유발할 수 있습니다.

해결 방법:

훅을 컴포넌트의 최상위 레벨에서만 호출하세요.

조건문이나 반복문 안에서 훅을 사용해야 한다면, 조건문/반복문의 바깥쪽에서 조건에 따라 훅을 호출하는 방식으로 수정해야 합니다.

필요한 경우 커스텀 훅을 만들어서 로직을 추상화하여 사용하세요.




### 6. SOP와 CORS:

SOP (Same-Origin Policy): 웹 보안 정책 중 하나로, 웹 페이지에서 온 리소스가 동일한 출처(프로토콜, 도메인, 포트)에서 온 것인지 검사하는 보안 메커니즘입니다. 다른 출처에서 오는 리소스에 접근하려고 할 때 보안 상의 이유로 브라우저가 요청을 차단합니다.

CORS (Cross-Origin Resource Sharing): SOP를 우회하기 위한 메커니즘으로, 서로 다른 출처 간에 리소스를 공유할 수 있게 해줍니다. 서버가 올바른 CORS 헤더를 응답으로 보내면 브라우저가 해당 리소스에 접근하는 것을 허용합니다.


### 7. Class 컴포넌트와 Functional 컴포넌트의 차이점과 사용 형태:
Class 컴포넌트: React의 기존 컴포넌트 작성 방식으로, ES6 클래스를 사용하여 컴포넌트를 정의합니다. state를 사용하거나 라이프사이클 메서드를 활용할 수 있습니다.

```
class MyClassComponent extends React.Component {
  render() {
    return <div>Hello, Class Component!</div>;
  }
}

```

Functional 컴포넌트: 함수 형태로 컴포넌트를 작성하는 방식으로, React Hooks의 등장으로 주로 사용됩니다. 단순히 props를 받아와서 뷰를 렌더링하는 역할을 수행합니다.

```
function MyFunctionalComponent(props) {
  return <div>Hello, Functional Component!</div>;
}
```

Class 컴포넌트는 더 많은 기능과 라이프사이클 메서드를 활용할 수 있지만 코드가 복잡해질 수 있습니다. Functional 컴포넌트는 간결하고 읽기 쉬운 장점이 있으며, 훅(Hooks)을 통해 Class 컴포넌트와 비슷한 기능을 활용할 수 있어서 최근에는 주로 Functional 컴포넌트가 사용되고 있습니다.

### 8. 2의 보수(Two's Complement):
2의 보수는 컴퓨터에서 음수를 표현하기 위한 방법 중 하나입니다. 양수와 음수를 모두 표현할 수 있으며 덧셈과 뺄셈을 동일한 방식으로 처리할 수 있도록 합니다.
2의 보수 방법은 다음과 같습니다:

양수를 이진수로 나타냅니다. (부호 비트를 제외한 나머지 비트)
모든 비트를 반전시킵니다. (0은 1로, 1은 0으로 변경)
1을 더합니다.
예시:
10을 8비트 2의 보수로 표현하는 과정:

10을 이진수로 변환: 00001010
모든 비트 반전: 11110101
1을 더함: 11110110
따라서 10의 8비트 2의 보수는 11110110입니다.

### 9. 메뉴 구현시 호버 이벤트 문제 극복 방법:
메뉴를 구현할 때 호버 이벤트로 인해 예기치 않은 동작이 발생하는 경우가 있습니다. 이를 극복하기 위해 여러 가지 방법이 있습니다.
디바운스(Debounce) 또는 스로틀(Throttle): 호버 이벤트를 처리할 때 디바운스 또는 스로틀을 사용하여 이벤트 핸들러를 지정된 시간 동안 한 번만 호출하도록 제어합니다. 이를 통해 이벤트 핸들러의 호출 횟수를 줄여서 의도하지 않은 동작을 방지할 수 있습니다.

CSS Transition/Animation: CSS의 transition 또는 animation을 사용하여 메뉴가 부드럽게 열리고 닫히도록 만들 수 있습니다. 이를 통해 마우스 호버가 불안정하더라도 사용자에게 자연스러운 효과를 제공할 수 있습니다.

Click 이벤트 사용: 호버 대신 클릭 이벤트를 사용하여 메뉴를 열고 닫을 수 있습니다. 사용자의 의도에 따라 명확하게 메뉴를 조작하게 되므로 호버로 인한 문제를 해결할 수 있습니다.

이러한 방법들을 조합하여 메뉴를 구현하면 사용자 경험을 향상시키고 호버로 인한 문제를 극복할 수 있습니다.
