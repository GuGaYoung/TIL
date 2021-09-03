## Big O란?

**알고리즘 속도 표현법**
(가장 최악의 경우를 판단)

알고리즘은 빠르다, 느리다를 시간으로 표현하지 않는다

**why?**

같은 알고리즘이더라도 컴퓨터의 사양에 따라 속도는 다르기 때문! (속도는 하드웨어가 결정한다.)

**그래서**

알고리즘은 "완료까지 걸리는 절차의 수"로 결정이 된다

<br/>

---

**시간복잡도의 문제해결 단계**

- O(1) – 상수 시간 : 문제를 해결하는데 오직 한 단계만 처리함. (매번 동일한 수의 스탭이 필요)
  <br/>
  ex) 배열의 첫번째 값을 출력하는 경우
  <br/>
  <br/>

- O(log n) – 로그 시간 : 문제를 해결하는데 필요한 단계들이 연산마다 특정 요인에 의해 줄어듬.
  <br/>
  ex) 이진검색알고리즘
  <br/>
  <br/>

- O(n) – 직선적 시간 : 문제를 해결하기 위한 입력 N 만큼의 단계가 필요.
  <br/>
  ex) 선형검색알고리즘
  <br/>
  <br/>
- O(n log n) : 문제를 해결하기 위한 단계의 수가 N번에 그 하나의 N번당 필요한 단계들이 연산마다 특정 요인에 의해 줄어듬.
  <br/>
  <br/>

- O(n^2) – 2차 시간 : 문제를 해결하기 위한 단계의 수는 입력값 n의 제곱.
  <br/>
  ex) 반복문이 두번 있는 케이스
  <br/>
  <br/>

- O(C^n) – 지수 시간 : 문제를 해결하기 위한 단계의 수는 주어진 상수값 C 의 n 제곱.
  <br/>
  <br/>

---

  <br/>

**빅-오 표기법의 성능(수행시간, 연산횟수)**
O(1) > O(log n) > O(n) > O(n * log n) > O(n²) > O(n³) > O(2^n) > O(n!)

  <br/>
  <br/>
  <br/>

참고

[https://www.youtube.com/watch?v=BEVnxbxBqi8&list=PL7jH19IHhOLMdHvl3KBfFI70r9P0lkJwL&index=5](https://www.youtube.com/watch?v=BEVnxbxBqi8&list=PL7jH19IHhOLMdHvl3KBfFI70r9P0lkJwL&index=5)

[https://blog.chulgil.me/algorithm/](https://blog.chulgil.me/algorithm/)