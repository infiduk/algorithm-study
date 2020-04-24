1. `scanf`, `printf`가 `cin`, `cout` 보다 더 빠름
2. 변수 출력이 아닌 간단한 문자열 출력은 puts("")를 활용할 수 있음
3. 새로운 입력이 들어오지 않을 때 까지 ~ (EOF 활용)
    ``` c++
    // scanf는 받아온 값을 return
    // 에러가 발생하거나 EOF(End of File)을 만나면 -1을 return
    while (scanf("%d", &n) != EOF) { }
    while (scanf("%d", &n) != -1) { }

    // -1 == 1111 1111 ... 1111 (2진수)
    // ~ -1 == 0000 0000 ... 0000 (2진수) == 0
    while (~scanf("%d", &n)) { }
    ```
4. while 조건문 빠져나올 때
    ``` c++
    // 비교연산자 안 쓰고 사칙연산해서 0이 나오면 빠져나올 수 있음
    while(a - b) { }
    ```
5. `sort` 함수
    ``` c++
    // 시간 복잡도 nlogn
    #include <algorithm>
    sort(시작, 끝, (내림차순 or 사용자 정의);

    // 길이가 3인 arr 배열을 오름차순으로 정렬
    sort(arr, arr + 3);
    ```
6. c++도 삼항 연산자 사용 가능, if문 보다 속도가 빠르다고 함
7. while(여기) 증감 연산자 사용 가능
    ``` c++
    while(n++) { }
    while(--n) { }
    ```
8. `for` vs. `while`
    ``` c++
    // for문은 특정한 범위가 주어졌을 때
    // 100까지만 돌 것임
    for(int i = 1; i <= 100; i++) { }

    // while문은 조건에 따라 값을 얻을 때
    // 행복할 때 까지 돌 것임
    while(!isHappy()) { }

    // 속도는 비슷하다고 함

    // 출처: https://kldp.org/node/116277
    ```