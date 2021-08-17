## 구구단
### 구구단을 출력하는 문제

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
N을 입력받은 뒤, 구구단 N단을 출력하는 프로그램을 작성하시오.</br> 출력 형식에 맞춰서 출력하면 된다. | 첫째 줄에 N이 주어진다. N은 1보다 크거나 같고, 9보다 작거나 같다.| 출력형식과 같게 N*1부터 N*9까지 출력한다.

<br/>


> 예제 입력 예시

```
2
```

> 예제 출력 예시

```
2 * 1 = 2
2 * 2 = 4
2 * 3 = 6
2 * 4 = 8
2 * 5 = 10
2 * 6 = 12
2 * 7 = 14
2 * 8 = 16
2 * 9 = 18
```

<br/>

> 내가 푼 방식

```javascript
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let input = [];

rl.on('line', function (line) {

    input.push(line)

    rl.close();
}).on('close', function () {

    for (var i = 1; i < 10; i++) {
        console.log(input + " * " + i + " = " + input * i);
    }

    process.exit();
});
```
<br/>

#### 📔 파이썬이 아닌 자바스크립트로 언어를 바꿔서 구현을 하였는데 처음 값을 받는 부분에서 많이 쩔쩔맸습니다. 😂 혹시 오답이 나온다면 출력형식을 다시 확인 후 풀면 될거 같습니다

<br/>

---

<br/>





## 	A+B - 3
### A+B를 여러 번 출력하는 문제

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오. | 첫째 줄에 테스트 케이스의 개수 T가 주어진다. </br> 각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10) | 각 테스트 케이스마다 A+B를 출력한다.

<br/>

> 예제 입력 예시

```
5
1 1
2 3
3 4
9 8
5 2
```

> 예제 출력 예시

```
2
5
7
17
7
```

<br/>

> 내가 푼 방식

```javascript
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
});

let T = null;
let countT = 0;
let data = [];

rl.on('line', function (line) {

    if (!T) {
        T = +line;
    } else {
        data = line.split(' ').map((el) => parseInt(el));
        console.log(data[0] + data[1]);

        countT += 1; // data를 입력받으면 countN을 증가시켜주고
    }
    if (countT === T) {
        // 입력받은 T 만큼 테스트 케이스를 통과하게되면
        rl.close(); // rl.close()를 호출하고
    }
}).on('close', function () {
    process.exit(); // 종료한다.
});
```
<br/>

#### 📔 테스트 개수가 주어질 때는 위와 같은 방식으로 개발하면 된다.

<br/>

---

<br/>





## 	합
### 1부터 N까지의 합을 구하는 문제. 물론 반복문 없이 풀 수도 있습니다.

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
n이 주어졌을 때, 1부터 n까지 합을 구하는 프로그램을 작성하시오. | 첫째 줄에 n (1 ≤ n ≤ 10,000)이 주어진다. | 1부터 n까지 합을 출력한다.

<br/>

> 예제 입력 예시

```
3
```

> 예제 출력 예시

```
6
```

<br/>

> 내가 푼 방식

```javascript
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let input = [];

rl.on('line', function (line) {
    input.push(line)
    rl.close();
}).on('close', function () {

    let sum = 0;
    for (var i = 1; i < Number(input) + 1; i++) {
        sum = sum + i;
    }
    console.log(sum);
    process.exit();
});
```
<br/>

#### 📔 수학적인 연산을 할 때는 값을 숫자로 인식하고 있는지 문자로 인식하고 있는지 확인하자!

<br/>

---

<br/>

## 빠른 A+B
### 빠르게 입력받고 출력하는 문제

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
본격적으로 for문 문제를 풀기 전에 주의해야 할 점이 있다. <br> 입출력 방식이 느리면 여러 줄을 입력받거나 출력할 때 시간초과가 날 수 있다는 점이다. ...(생략) | 첫 줄에 테스트케이스의 개수 T가 주어진다.<br> T는 최대 1,000,000이다. 다음 T줄에는 각각 두 정수 A와 B가 주어진다. A와 B는 1 이상, 1,000 이하이다. | 각 테스트케이스마다 A+B를 한 줄에 하나씩 순서대로 출력한다.

<br/>


> 예제 입력 예시

```
5
1 1
12 34
5 500
40 60
1000 1000
```

> 예제 출력 예시

```
2
46
505
100
2000
```

<br/>

> 내가 푼 방식

```javascript
let input = require('fs').readFileSync('/dev/stdin').toString().split('\n');

let max = Number(input[0]);
let answer = '';

for (let i = 1; i <= max; i++) {
    let num = input[i].split(' ');
    answer += Number(num[0]) + Number(num[1]) + '\n';
}

console.log(answer);
```
<br/>

#### 📔 for 문을 사용해 1부터 시작해 split 메서드로 나눈 후 결과값을 얻고 하나의 문자열에 넣어 출력을 해주면 됩니다

<br/>

---

<br/>

## N 찍기
### 1부터 N까지 출력하는 문제

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
자연수 N이 주어졌을 때, 1부터 N까지 한 줄에 하나씩 출력하는 프로그램을 작성하시오. | 첫째 줄에 100,000보다 작거나 같은 자연수 N이 주어진다.| 첫째 줄부터 N번째 줄 까지 차례대로 출력한다.

<br/>


> 예제 입력 예시

```
5
```

> 예제 출력 예시

```
1
2
3
4
5
```

<br/>

> 내가 푼 방식

```javascript
let input = require("fs").readFileSync("/dev/stdin").toString();

let answer = "";

for (let a = 1; a <= input; a++) {
    answer += a + "\n";
}
console.log(answer);
```
<br/>

#### 📔 시간초과가 난다면 require 방법을 이용하고 console.log를 줄여야한다.

<br/>

---

<br/>





## 	기찍 N
### 제문 는하력출 지까N 터부1

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
자연수 N이 주어졌을 때, N부터 1까지 한 줄에 하나씩 출력하는 프로그램을 작성하시오. | 첫째 줄에 100,000보다 작거나 같은 자연수 N이 주어진다. | 첫째 줄부터 N번째 줄 까지 차례대로 출력한다.

<br/>

> 예제 입력 예시

```
5
```

> 예제 출력 예시

```
5
4
3
2
1
```

<br/>

> 내가 푼 방식

```javascript
let input = Number(require('fs').readFileSync('/dev/stdin').toString());

let answer = '';

for (let i = input; i > 0; i--) {
    answer += i + '\n';
}
console.log(answer);
```
<br/>

#### 📔 시간초과가 난다면 require 방법을 이용하고 console.log를 줄여야한다.

<br/>

---

<br/>





## 	A+B - 7
### A+B를 조금 더 아름답게 출력하는 문제

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오. | 첫째 줄에 테스트 케이스의 개수 T가 주어진다. </br> 각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)| 각 테스트 케이스마다 "Case #x: "를 출력한 다음, A+B를 출력한다. 테스트 케이스 번호는 1부터 시작한다.

<br/>

> 예제 입력 예시

```
5
1 1
2 3
3 4
9 8
5 2
```

> 예제 출력 예시

```
Case #1: 2
Case #2: 5
Case #3: 7
Case #4: 17
Case #5: 7
```

<br/>

> 내가 푼 방식

```javascript
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
});

let T = null;
let countT = 0;
let data = [];

rl.on('line', function (line) {

    if (!T) {
        T = +line;
    } else {

        countT += 1; // data를 입력받으면 countN을 증가시켜주고

        data = line.split(' ').map((el) => parseInt(el));
        console.log("Case #" + countT + ": "+ (data[0] + data[1]));

    }
    if (countT === T) {
        // 입력받은 T 만큼 테스트 케이스를 통과하게되면
        rl.close(); // rl.close()를 호출하고
    }
}).on('close', function () {
    process.exit(); // 종료한다.
});
```
<br/>

---

<br/>

## A+B - 8
### A+B를 바로 위 문제보다 아름답게 출력하는 문제

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오. | 첫 줄에 테스트케이스의 개수 T가 주어진다.<br> 각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10) | 각 테스트 케이스마다 "Case #x: A + B = C" 형식으로 출력한다.<br> x는 테스트 케이스 번호이고 1부터 시작하며, C는 A+B이다.

<br/>


> 예제 입력 예시

```
5
1 1
2 3
3 4
9 8
5 2
```

> 예제 출력 예시

```
Case #1: 1 + 1 = 2
Case #2: 2 + 3 = 5
Case #3: 3 + 4 = 7
Case #4: 9 + 8 = 17
Case #5: 5 + 2 = 7
```

<br/>

> 내가 푼 방식

```javascript
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
});

let T = null;
let countT = 0;
let data = [];

rl.on('line', function (line) {

    if (!T) {
        T = +line;
    } else {

        countT += 1; // data를 입력받으면 countN을 증가시켜주고

        data = line.split(' ').map((el) => parseInt(el));
        console.log("Case #" + countT + ": " + data[0] + " + " + data[1] + " = " + (data[0] + data[1]));

    }
    if (countT === T) {
        // 입력받은 T 만큼 테스트 케이스를 통과하게되면
        rl.close(); // rl.close()를 호출하고
    }
}).on('close', function () {
    process.exit(); // 종료한다.
});
```
<br/>
<br/>

---

<br/>

## 별 찍기 - 1
### 별을 찍는 문제 1

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
첫째 줄에는 별 1개, 둘째 줄에는 별 2개, N번째 줄에는 별 N개를 찍는 문제 | 첫째 줄에 N(1 ≤ N ≤ 100)이 주어진다.| 첫째 줄부터 N번째 줄까지 차례대로 별을 출력한다.

<br/>


> 예제 입력 예시

```
5
```

> 예제 출력 예시

```
*
**
***
****
*****
```

<br/>

> 내가 푼 방식

```javascript
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let input = [];
let answer = '';
rl.on('line', function (line) {
    input.push(line)
    rl.close();
}).on('close', function () {

    for (let i = 1; i <= input; i++) {
        answer += "*";
        console.log(answer);
    }

    process.exit();
});

```
<br/>

#### 📔 빈 문자열에 *를 넣어 출력하는 방식으로 구현할 수 있습니다.

<br/>

---

<br/>





## 	별 찍기 - 2
### 별을 찍는 문제 2

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
첫째 줄에는 별 1개, 둘째 줄에는 별 2개, N번째 줄에는 별 N개를 찍는 문제 <br/> 하지만, 오른쪽을 기준으로 정렬한 별(예제 참고)을 출력하시오. | 첫째 줄에 N(1 ≤ N ≤ 100)이 주어진다. | 첫째 줄부터 N번째 줄까지 차례대로 별을 출력한다.

<br/>

> 예제 입력 예시

```
5
```

> 예제 출력 예시

```
    *
   **
  ***
 ****
*****
```

<br/>

> 내가 푼 방식

```javascript
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let input = [];
rl.on('line', function (line) {
    input.push(line)
    rl.close();
}).on('close', function () {

    const num = +input;
    let star = '';
    let blank = '';

    for (let i = 1; i <= num; i++) {
        star += '*';
        // num - i -> 4,3,2,1,0
        for (let j = 0; j < num - i; j++) {
            blank += ' ';
        }
        console.log(blank + star);
        blank = '';
    }

    process.exit();
});
```
<br/>

#### 📔 이중 for문을 이용해서 구현할 수 있습니다.

<br/>

---

<br/>





## 	X보다 작은 수
### for와 if를 같이 쓰는 문제

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
정수 N개로 이루어진 수열 A와 정수 X가 주어진다. <br/> 이때, A에서 X보다 작은 수를 모두 출력하는 프로그램을 작성하시오. | 첫째 줄에 N과 X가 주어진다. (1 ≤ N, X ≤ 10,000) 둘째 줄에 수열 A를 이루는 정수 N개가 주어진다. <br/> 주어지는 정수는 모두 1보다 크거나 같고, 10,000보다 작거나 같은 정수이다.| X보다 작은 수를 입력받은 순서대로 공백으로 구분해 출력한다.<br/> X보다 작은 수는 적어도 하나 존재한다.

<br/>

> 예제 입력 예시

```
10 5
1 10 4 9 2 3 8 5 7 6
```

> 예제 출력 예시

```
1 4 2 3
```

<br/>

> 내가 푼 방식

```javascript

const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
});

let N = null;
let X = null;
let data = [];
let result = [];

rl.on('line', function (line) {

    data = line.split(' ').map((el) => parseInt(el));

    if (!N && !X) {
        N = data[0];
        X = data[1];

    } else {

        for (var i = 0; i <= N; i++) {
            if(X > data[i]) {
                result += data[i] + " ";
            }
        }

    }

}).on('close', function () {
    console.log(result);
    process.exit();
});
```
<br/>
<br/>

---