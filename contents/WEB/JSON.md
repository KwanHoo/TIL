# _JSON_

## JSON

- javascript object notation
- 브라우저와 서버 사이에서 오고 가는 데이터 형식

## JSON.stringify(value, replacer, space)

- value(필수) : JSON 문자열로 변환할 값임
  - 배열, 객체, 숫자, 문자 등
- replacer(선택) : 함수 또는 배열이 될 수 있음
  - null이거나 제공되지 않으면, 객체의 모든 속성들이 JSON 문자열 결과에 포함됨
  - replacer가 함수인 경우 필수값인 value가 replacer 함수를 한번 거치고 문자열화됨
  - replacer가 배열인 경우 배열의 값과 일치하는 값만 문자열화 됨

[참고포스팅](https://steemit.com/kr-dev/@cheonmr/json-stringify)
