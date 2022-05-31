# JS
웹 브라우저에서 동작하는 유일한 프로그래밍 언어 JS 파헤치기


## 클로저 사용 이유
변수값은 누군가에 의해 언제든지 변경 될 수 있다.
오류 발생의 근본적인 원인이 될 수 있다.

함수형 프로그래밍은 외부에 의해 상태나, 데이터가 변경되는 부수 효과를 최대한 억제하는 것을 목표로 한다.
때문에, 프로그래밍의 안전성을 높이기 위해 클로저를 적극 활용한다.



## live 객체 의도와 다른 코드 작성  피하기
HTML Collection과 NodeList의 ChildNodes는 의도와 live 객체임으로 동적으로 객체가 변경된다.
특히 for 문을 돌 때, 중간에 객체의 변경이 있을 수 있다. 
때문에 배열로 변환 시켜 사용하는 것이 좋다.



## 유사 배열 온전한 배열의 역할을 못하는 대, 왜 필요할까?
인덱스와 length 프로퍼티를 가지고 있어 배열처럼 보이는 객체이다. 
하지만 배열처럼 순화가 불가능하다.
객체이기 때문에 메서드를 가질 수 있고, window에서 변경 불가능한 객체인 유사 배열을 제공한다.
제공되는 것이기 때문에 직접적으로 사용되지는 않는다.



## 개념이 다양하고 유기적으로 묶여있을 때의 대처 방법
### 존재 이유가 없는 존재는 없다.
차이점에 대해서 고민하려고 노력한다.
차이점을 알면 존재 이유가 궁금해 진다.
존재 이유를 알면 필요한 기능에 대한 적절한 메서드를 활용해서 사용할 수 있다.

## nodeVlaue, textContent 프로퍼티 보다 복잡하는데 돼 존재할까?
파싱된 텍스트 노드에 따로 접근할 수 있다.
textContent는 모든 텍스트의 값을 텍스트로 모두 반환한다.
접근은 textContent가 쉽다.
textContent 프로퍼티에 문자열을 할달하면 요소 노드의 모든 자식 노드가 제거되고 할당한 문자열이 텍스트로 추가된다.

## 악성 코드 피하기 innerHTML
innerHTML은 script 요소 없이도 크로스 사이트 스크립팅 공격이 가능하다. 

## 얼핏보면 그런거 같지만 자바스크립트 엔진은 더 복잡하게 굴러간다.
innerHTML에서 노드를 추가할 때, 기존에 생성된 노드에 추가 되어 얼핏 보기에 기존 생성 노드는 새롭게 생성되지 않는 것처럼 보인다.
하지만, 유지 되어도 좋은 기존 코드까지 제거하고 다시 처음부터 새롭게 자식 노드를 생성하여 반영하여 효율적이지 않다.
얼핏 보기에는 매우 효율적인 것 처럼 보이지만, 사실 자바스크립트 엔진은 그렇게 구동되지 않는다.
효율적 코드를 짠다는 것은 언어 엔진 작동 원리를 이해하고, 적용하는 것이라고 생각한다.
