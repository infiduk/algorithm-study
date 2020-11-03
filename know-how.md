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
9. `vector`
    ``` c++
    // 헤더가 필요하고, 사용할 때 std:: 가 있어야 함
    #include <vector>
    using namespace std;

    // vector 생성
    vector<int> vec(길이, 초기화할 값); // {값, 값, 값, ...}
    vector<int> vec2(vec); // vec를 vec2에 복사

    // 값 넣기
    vec.push_back(10);
    vec.insert(vec.begin() + 1, 10);

    // 값 삭제
    vec.erase(vec.begin());

    // 처음부터 끝까지 참조
    for(vector<int>::iterator itr = vec.begin(); itr != vec.end(); itr++) {
        cout << *itr << endl;
    }
    // or
    for (vector<int>::size_type i = 0; i < vec.size(); i++) {
        cout << vec[i] << endl;
    }
    ```
10. 수학 공식으로 풀 수 있는 문제는 공식으로 풀자
11. `string`
    ``` c++
    #include <iostream>
    // string 사용을 위한 헤더
    #include <string>
    // string은 cin, cout으로 사용
    using namespace std;

    string s = "abc";
    cout << s; // abc

    s.at(찾을 문자열의 인덱스);
    // 문자열의 0번째 값을 리턴
    s.at(0); // a
    
    s[찾을 문자열의 인덱스];
    // 문자열의 1번째 값을 리턴
    s[1]; // b

    // 문자열의 첫번째 값을 리턴
    s.front(); // a
    // 문자열의 마지막 값을 리턴
    s.back(); // c

    // 문자열의 첫번째 문자를 가리키는 포인터 리턴
    s.begin();
    // 문자열의 마지막 문자를 가리키는 포인터 리턴
    s.end();
    
    // 문자열의 사이즈를 반환
    s.size(); // 3
    s.length(); // 3
    
    // 문자열의 사이즈를 변환
    s.resize(1); // a
    s.resize(5); // abc(빈칸)
    s.resize(5, 'e'); // abcee

    // 문자열에서 해당 문자의 (시작) 인덱스를 반환
    s.find('a'); // 0
    s.find("bc"); // 1
    
    // 문자열 자르기
    s.substr(1); // bc
    s.substr(1,1); // b
    
    // 문자열 지우기 (값만 삭제)
    s.clear();
    
    // 문자열이 비어있는지 확인
    s.empty(); // false
    ```
12. `getline` 함수
    ``` c++
    #include <iostream>
    // string 헤더 필요
    #include <string>
    using namespace std;
    string str_1;
    string str_2;

    // 띄어쓰기도 입력 받음
    getline(cin, str_1);

    // 5개의 문자만 입력을 받음 (단, 맨 마지막에 null 포함)
    cin.getline(str_1, 5);
    ```
13. `max` 함수
    ``` c++
    // a랑 b를 비교해서 큰 값을 리턴
    max(a, b);
    ```
14. 배열 초기화
    ``` c++
    // 선언 시 0으로 초기화
    int arr[10] = {};
    int arr[10] = {0};
    int arr[10] = {0,}; // 처음 값만 0으로 
    
    fill(시작 위치, 끝 위치, 값);
    fill_n(시작 위치, 갯수, 값);
    ```
15. `string::npos`
    ``` c++
    // 찾는 문자열이 없으면 string::npos 반환
    string::npos

    string s = "abced";
    if(s.find("ab") != string::npos)
        cout << "존재";
    ```








