# 문자열 내 p와 y의 개수 (Level 1)

## Javascript
1. 처음에 생각해 본 방법
    ``` javascript
    function solution(s){
        // s의 길이만큼 반복문을 돌려서 문자열 내에 p나 y인 문자가 있으면 카운트 + 1
        // p의 개수 === y의 개수 이면 true를, 그렇지 않으면 false를 리턴
        let pc = 0, yc = 0
        for(let i = 0, length = s.length; i < length; i++) {
            s[i] ==='P' || s[i] === 'p' ? pc += 1 : ""
            s[i] === 'Y' || s[i] === 'y' ? yc += 1 : ""
        }
        return (pc === yc ? true : false)                   
    }
    ```

2. 뭔가 한 줄로 끝날 것 같아서 다시 생각해 본 방법
    ``` javascript
    function solution(s) {
        // 문자열을 다 소문자로 만들고, match와 정규식을 이용해 카운트를 셈
        return s.toLowerCase().match(/p/gi).length === s.toLowerCase().match(/y/gi).length ? true : false
    }
    ```
    - 근데 match는 문자열에 p나 y가 없을 경우 null을 리턴하기 때문에 length에서 오류 발생

3. 2번을 다시 생각해본 방법
    ``` javascript
    function solution(s) {
        // 그냥 카운트를 변수로 빼고 null 값 체크 후 비교
        let pc = s.toLowerCase().match(/p/gi)
        let yc = s.toLowerCase().match(/y/gi)
        return (!pc ? 0 : pc.length) === (!yc ? 0 : yc.length) ? true : false
    }
    ```
    - 성공!

- 다른 분들의 풀이
    ``` javascript
    function solution(s){
        return s.toLowerCase().split('p').length === s.toLowerCase().split('y').length
    }
    ```
    - split... wow....
    - 그냥 match 말고.. split 쓰면 null 값 체크를 안해도..ㅎ.. 되네