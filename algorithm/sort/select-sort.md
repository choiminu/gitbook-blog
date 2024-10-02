---
cover: >-
  https://images.unsplash.com/photo-1724141973274-f3a90b9aa7d8?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHJhbmRvbXx8fHx8fHx8fDE3Mjc4MjkwMTZ8&ixlib=rb-4.0.3&q=85
coverY: 0
---

# 선택 정렬

## 선택 정렬 개념

선택 정렬이란, 정렬 알고리즘 중 하나로, 리스트에서 **가장 작은 원소를 찾아** 정렬되지 않은 리스트의 맨 앞에 있는 데이터와 위치를 교환해나가는 방식으로 정렬하는 알고리즘을 말한다.



### 정렬 과정

<figure><img src="https://blog.kakaocdn.net/dn/BAOXf/btsIYxGs78t/4QUwFHiU5CN3ZZpk8pQd30/img.gif" alt=""><figcaption><p><a href="https://www.lavivienpost.net/selection-sort-gif/">https://www.lavivienpost.net/selection-sort-gif/</a></p></figcaption></figure>

1. 리스트의 첫 번째에  위치한 원소를 기준으로 삼는다.
2. 기준 원소 이후 리스트에서 가장 작은 원소를 찾는다.
3. 기준 원소와 가장 작은 원소의 위치를 교환한다.
4. 기준 원소 옆에 있는 원소를 새 기준으로 삼아 리스트의 끝까지 반복하여 정렬한다.

### 정렬 과정 - 상세

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>첫 번째 자리에 위치한 원소를 기준으로 삼는다.</p></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>기준 원소 이후 리스트에서 가장 작은 원소를 찾는다.</p></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>찾은 가장 작은 원소를 기준 원소와 위치를 교환한다.</p></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption><p>두 번째 위치에 자리한 원소를 기준으로 삼는다.</p></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>기준 원소 이후 리스트에서 가장 작은 원소를 찾고 위치를 교환한다.</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption><p>세번째 위치에 자리한 원소를 기준으로 삼는다.</p></figcaption></figure>

<figure><img src="https://blog.kakaocdn.net/dn/6H1lj/btsIYtjTyXz/Xa2vVA4i2J9cvPqK0hVge1/img.png" alt=""><figcaption><p>기준 원소 이후 리스트에서 가장 작은 원소를 찾는다.</p></figcaption></figure>



<figure><img src="https://blog.kakaocdn.net/dn/dKAXzi/btsIW64nzvy/0I6hXd5mmo7NeErNQaMvUK/img.png" alt=""><figcaption><p>기준 원소 이후 리스트에서 가장 작은 원소를 찾고 위치를 교환한다.</p></figcaption></figure>



<figure><img src="https://blog.kakaocdn.net/dn/be9MNC/btsIYcP4R4Z/a3CKosnv1ynTXMQS8ejnE0/img.png" alt=""><figcaption><p>배열의 모든 위치에 대해 위 과정을 반복한다.</p></figcaption></figure>



### 구현 (Java) <a href="#ec-84-a0-ed-83-9d-20-ec-a0-95-eb-a0-ac-20-ea-b5-ac-ed-98-84-1" id="ec-84-a0-ed-83-9d-20-ec-a0-95-eb-a0-ac-20-ea-b5-ac-ed-98-84-1"></a>

```java
public static void selectSort(int[] arr) {
    // 배열의 모든 원소를 기준으로 삼아 반복
    for (int i = 0; i < arr.length; i++) {
        int index = i; // 현재 위치를 기준으로 삼음

        // 현재 위치 이후의 원소들 중에서 가장 작은 원소를 찾음
        for (int j = i + 1; j < arr.length; j++) {
            // 더 작은 원소를 발견하면 인덱스를 업데이트
            if (arr[index] > arr[j]) {
                index = j;
            }
        }

        // 현재 위치의 원소와 가장 작은 원소를 교환
        int temp = arr[i];
        arr[i] = arr[index];
        arr[index] = temp;
    }
    // 정렬된 배열 출력
    System.out.println(Arrays.toString(arr));
}
```



### 시간 복잡도

* 외부 반복문 :  선택 정렬에서 리스트의 요소를 정렬해야 하므로 요소를 순회해야  한다. 따라서 배열의 길이를 N이라고 하였을 때 반복문은 N번 수행하게 된다.\

* 내부 반복문 :&#x20;

