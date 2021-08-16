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