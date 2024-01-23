# 동기와 비동기의 차이

## 동기(Synchronous)와 비동기(Asynchronous)

### 정의

작업의 진행 방식 처리 방법으로, 작업들이 함께 시작되고, 끝나는 지 여부로 구분한다.

### 동기(Synchronous)란?

동기는 작업들이 같이 시작해 같이 끝나는 방식이다.

![sync](https://github.com/CHZZK-Study/cs-study/assets/84820008/25172ba3-3015-4e72-8219-3d098f03c2e1)

### 비동기(Asynchronous)란?

비동기는 작업들의 시작과 끝이 다른 방식이다.

![async](https://github.com/CHZZK-Study/cs-study/assets/84820008/6df75858-85f4-4e0c-b84a-c550c2a25d97)

### 각 방식의 장단점

동기는 업무가 단순하지만 자원을 비효율적으로 사용하고, 비동기는 업무가 복잡해질 수 있지만(콜백지옥, 에러 처리 등등) 자원을 효율적으로 사용한다.

## 블로킹(Blocking) 과 논블로킹(Non-Blocking)

### 정의

제어할 수 없는 대상의 처리 방법으로, 다른 작업의 실행이 현재 작업의 실행을 막는지 여부로 구분한다.

### 블로킹(Blocking)이란?

Blocking은 호출자가 직접 제어할 수 없는 대상에게 제어권을 넘김으로써 해당 대상의 작업이 끝날때까지 기다려야하는 방식이다.

![blocking](https://github.com/CHZZK-Study/cs-study/assets/84820008/032cddfa-1920-422c-9c62-9315534b4de6)

### 논블로킹(Non-Blocking)이란?

Non-Blocking은 직접 제어할 수 없는 대상의 작업이 완료되기 전에 제어권을 넘김으로써 새로운 작업을 수행할 수 있는 방식이다.

![non-blocking](https://github.com/CHZZK-Study/cs-study/assets/84820008/426d0c31-9b28-4a40-a9a2-64b02b6e483f)

## 동기, 비동기, 블로킹, 논블로킹의 목적

CPU 자원을 효율적으로 사용하고 성능을 향상시키기 위함이다.