## A+B - 5
### 0 0이 들어올 때까지 A+B를 출력하는 문제

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오. | 입력은 여러 개의 테스트 케이스로 이루어져 있다. <br/>각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)<br/> 입력의 마지막에는 0 두 개가 들어온다.| 각 테스트 케이스마다 A+B를 출력한다.

<br/>


> 예제 입력 예시

```
1 1
2 3
3 4
9 8
5 2
0 0
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

const input = [];
let isFinish = false;
let i = 0;

rl.on('line', function (line) {
    input.push(line);
}).on('close', function () {

    while (!isFinish) {
        let result = input[i].split(' ').map((el) => parseInt(el));

        if(result[0] === 0 && result[1] === 0) {
            isFinish = true;
        } else {
            console.log(result[0] + result[1]);
            i++;
        }
    }

    process.exit();
});
```
<br/>

#### 📔 처음에는 for문으롤 처리했다가 while문을 사용하는 것이 목적이니 while문으로 재수정해서 풀었다.

<br/>

---

<br/>





## 	A+B - 4
### 입력이 끝날 때까지 A+B를 출력하는 문제. EOF에 대해 알아 보세요.

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오. | 입력은 여러 개의 테스트 케이스로 이루어져 있다. </br> 각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10) | 각 테스트 케이스마다 A+B를 출력한다.

<br/>

> 예제 입력 예시

```
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

const input = [];

rl.on('line', function (line) {

    input.push(line);

}).on('close', function () {

    let isFinish = false;
    let i = 0;

    while (!isFinish) {
        let result = input[i].split(' ').map((el) => parseInt(el));

        if(input.length - 1 === i) {
            isFinish = true;
        } else {
            i++;
        }
        console.log(result[0] + result[1]);
    }

    process.exit();
});
```
<br/>

#### 📔 앞문제의 코드를 살짝만 변형하면 풀 수 있는 문제.. EOF에 대해서 알아보자는 설명엔 쓰여있는데 자바스크립트에서는 해당이 안되나부다.. 

<br/>

---

<br/>





## 	더하기 사이클
### 원래 수로 돌아올 때까지 연산을 반복하는 문제

<br/>

| 문제 | 입력 | 출력 |
:---:|:---:|:---:
(생략..) N이 주어졌을 때, N의 사이클의 길이를 구하는 프로그램을 작성하시오. | 첫째 줄에 N이 주어진다. N은 0보다 크거나 같고, 99보다 작거나 같은 정수이다. | 첫째 줄에 N의 사이클 길이를 출력한다.

<br/>

> 예제 입력 예시

```
26
```

> 예제 출력 예시

```
4
```

<br/>

> 내가 푼 방식

```javascript
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
});

const input = [];
let isFinish = false;
let count = 0;

rl.on('line', function (line) {

    input.push(line);
    rl.close();

}).on('close', function () {
    var num = input;

    while (!isFinish) {
        count++;

        var sum = (num % 10) + Math.floor(num / 10);

        num = (num % 10).toString() + (sum % 10).toString();

        if(Number(input) === Number(num)){
            isFinish = true;
        }
    }
    console.log(count);

    process.exit();
});
```
<br/>

#### 📔 많이 헤맸던 문제.. 숫자의 각 자리수의 값을 구해 풀었다.
#### - 1의 자리에 있는 수 구하기: num % 10
#### - 10의 자리에 있는 수 구하기: Math.floor(num / 10)

<br/>

---