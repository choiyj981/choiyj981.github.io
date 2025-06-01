---
IDX: "6"
tags:
  - 
update: "2025-06-01T08:07:00.000Z"
date: "2025-06-01"
상태: "Ready"
title: "tests"
---
### 1. Rest Parameters (나머지 매개변수)

#### 1.1 개념

- **Rest Parameters**는 함수의 매개변수 목록에서 전달된 여러 인자를 하나의 배열로 모아줍니다.



- 이를 통해 전달되는 인자의 수가 가변적인 함수들을 쉽게 작성할 수 있습니다.

#### 1.2 사용 예시

#### 예시: 합계 구하기

```javascript
javascript
복사
const sum = (...numbers) => {
  // numbers는 전달된 인자들을 배열로 받음
  return numbers.reduce((acc, curr) => acc + curr, 0);
};

console.log(sum(1, 2, 3, 4)); // 출력: 10


```

#### 예시: 문자열 결합하기

```javascript
javascript
복사
const concatenateStrings = (separator, ...strings) => {
  // separator를 사용하여 나머지 인자들을 결합
  return strings.join(separator);
};

console.log(concatenateStrings(', ', "Apple", "Banana", "Cherry"));
// 출력: "Apple, Banana, Cherry"


```

<hr style="border: none; height: 1px; background-color: #e0e0e0; margin: 16px 0;" />
### 2. Spread Operator (전개 연산자)

#### 2.1 개념

- **Spread Operator**는 배열이나 객체와 같이 반복 가능한(iterable) 데이터를 개별 요소로 "펼쳐" 사용할 수 있도록 해줍니다.

- 이를 통해 배열 복사, 배열 결합, 객체 복사 및 병합, 함수 인자 전개 등 다양한 작업을 간결하게 처리할 수 있습니다.

#### 2.2 배열에서의 활용

#### 예시: 배열 복사

```javascript
javascript
복사
const originalArray = [1, 2, 3];
const copiedArray = [...originalArray];  // 원본 배열 복사
console.log(copiedArray); // 출력: [1, 2, 3]


```

#### 예시: 배열 결합

```javascript
javascript
복사
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const combinedArray = [...array1, ...array2]; // 두 배열 결합
console.log(combinedArray); // 출력: [1, 2, 3, 4, 5, 6]


```

#### 2.3 객체에서의 활용

#### 예시: 객체 복사

```javascript
javascript
복사
const obj1 = { a: 1, b: 2 };
const copiedObj = { ...obj1 };  // 객체 복사
console.log(copiedObj); // 출력: { a: 1, b: 2 }


```

#### 예시: 객체 병합

```javascript
javascript
복사
const obj1 = { a: 1, b: 2 };
const obj2 = { c: 3, d: 4 };
const mergedObj = { ...obj1, ...obj2 }; // 객체 병합 (동일 키는 나중 값이 덮어씀)
console.log(mergedObj); // 출력: { a: 1, b: 2, c: 3, d: 4 }


```

#### 2.4 함수 인자에 배열 전개하기

#### 예시: Math.max 사용

```javascript
javascript
복사
const numbers = [1, 2, 3, 4];
// 배열의 요소들을 개별 인자로 전달
console.log(Math.max(...numbers)); // 출력: 4


```

<hr style="border: none; height: 1px; background-color: #e0e0e0; margin: 16px 0;" />
### 3. 실무 활용 예시

- **배열 복사 및 결합:**

    데이터 리스트를 다룰 때 원본 배열을 보호하거나 여러 리스트를 하나로 합칠 때 사용합니다.

- **객체 복사 및 병합:**

    불변성을 유지하며 상태 객체나 설정 객체를 업데이트할 때 유용합니다.

    ```javascript
    javascript
    복사
    const newState = { ...prevState, updatedProperty: newValue };
    
    
    ```

- **함수 호출 시 배열 전개:**

    배열의 요소들을 함수의 개별 인자로 전달할 때 사용합니다.

- **API 응답 데이터 처리:**

    예를 들어, API에서 받은 배열 데이터를 spread operator를 사용하여 다른 배열과 결합하거나, 복사하여 가공하는 작업에 활용됩니다.

    예시 (불변성 유지하며 업데이트):

    ```javascript
    javascript
    복사
    const prevState = { theme: "dark", fontSize: 14 };
    const newState = { ...prevState, fontSize: 16 };
    console.log(newState); // 출력: { theme: "dark", fontSize: 16 }
    
    ```

<hr style="border: none; height: 1px; background-color: #e0e0e0; margin: 16px 0;" />
### 요약

- **Rest Parameters**

    - 함수 매개변수로 전달된 인자들을 하나의 배열로 모아서 처리합니다.

    - 예제: `const sum = (...numbers) => numbers.reduce((acc, curr) => acc + curr, 0);`

- **Spread Operator**

    - 배열이나 객체를 개별 요소로 "펼쳐"서 복사, 결합, 병합, 함수 인자 전개 등에 사용합니다.

    - 배열 예제: `[...arr1, ...arr2]`

    - 객체 예제: `{ ...obj1, ...obj2 }`

    - 함수 인자 예제: `Math.max(...numbers)`

이 정리는 Notion에 복사하여 붙여넣을 수 있도록 깔끔하게 구성되어 있으므로, 실무에서 자주 쓰이는 Spread Operator의 활용 방법을 쉽게 참고할 수 있습니다.

