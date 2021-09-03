## Bubble Sort 버블정렬
###인접한 두 개의 원소를 비교하여 자리를 교환하는 방식

<br/>

###작동 방식

---
0번째와 1번째를 비교 후 정렬<br/>
1번째와 2번째를 비교 후 정렬<br/>
...<br/>
n-1번째와 n번째를 비교 후 정렬
---

첫 번째 원소부터 마지막 원소까지 반복하여 한 단계가 끝나면 가장 큰 원소가 마지막 자리로 정렬된다 (오름차순으로 비교 시)
<br/>

맨 마지막 자리로 이동하는 모습이 물속에서 물 위로 올라오는 물방울 모양과 같아 버블(Bubble) 정렬이라고 한다.
<br/>

거의 모든 상황에서 최악의 성능을 보여주어, 실제로 많이 사용하지는 않음
<br/>

### CODE

```js
 // arr : 배열
function bubbleSort(arr) {
    let noSwaps;
    for (let i = arr.length; i > 0; i--) {
        noSwaps = true;
        for (let j = 0; j < i - 1; j++) {
            if (arr[j] > arr[j+1]) {
                let temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
                noSwaps = false;
            }
        }
        if (noSwaps) break;
    }
    return arr;
}
```

### 시간 복잡도 O(n^2)

---

## Selection Sort 선택정렬

###전체 원소들 중에서 기준 위치에 맞는 원소를 찾아 자리를 교환하는 방식

<br/>

###작동 방식

---
전체 원소 중에서 가장 작은 원소를 찾아 첫 번째 원소와 자리를 교환<br/>
그다음 두 번째로 작은 원소를 찾아서 두 번째 원소와 자리를 교환<br/>
그다음에는 세 번째로 작은 원소를 찾아 세 번째 원소와 자리를 교환<br/>
...<br/>
이 과정을 반복하면 정렬이 완성<br/>
---

### CODE

```js
 // arr : 배열
function selectionSort (arr) {
    for (let i = 0; i < arr.length; i++) {
        let minIndex = i;
        for (let j = i + 1; j < arr.length; j++) {
            if (arr[minIndex] > arr[j]) {
                minIndex = j;
            }
        }
        if (minIndex !== i) {
            let swap = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = swap;
        }
        console.log(`${i}회전: ${arr}`);
    }
    return arr;
}
```

### 시간 복잡도는 O(n^2)

---

## Insertion Sort 삽입정렬
###현재위치의 값을 현재위치보다 아래쪽으로 순회하며 알맞은 위치에 넣어주는 알고리즘

<br/>

###작동 방식

---
0번 인덱스는 건너뛴다.<br/>
0~1번 인덱스 중 1번 인덱스 값이 들어가야할 위치를 찾아서 넣는다<br/>
0~2번 인덱스 중 2번 인덱스 값이 들어가야할 위치를 찾아서 넣는다<br/>
…<br/>
0~n번 인덱스 중 n번 인덱스 값이 들어가야할 위치를 찾아서 넣는다<br/>
---

인간이 직접 정렬하는 순서와 제일 흡사
<br/>

선택정렬보다 빠르다 why? 필요한 아이템만 스캔을 하기 때문
<br/>

### CODE

```js
 // arr : 배열
function insertionSort(arr) {

    for (let i = 1; i < arr.length; i++) {
        let currentVal = arr[i];
        let targetIdx = 1;

        for (let j = i - 1; j >= 0 && arr[j] > currentVal; j--) {
            targetIdx = j;
            arr[targetIdx + 1] = arr[targetIdx];
        }
        if (targetIdx) {
            arr[targetIdx] = currentVal;
        }
    }
    return arr;
}
```

### 시간 복잡도는 O(n^2)

---

성능이 모두 다르지만 모두 같은 O(n^2)를 가지고 있다.
이 경우에는 최악의 시나리오 대신 평균 시나리오를 봐야한다.
