# 05. JavaScript_Function

- javascript는 일급 함수

- 함수 정의 함수 호출해서 사용

- 정의

  ```js
  function(p1, p2, ...){
  	내용;
  	return data;
  }
  ```

- 호출

  ```js
  let data = 함수명 (p1, p2, ...)
  ```

  ```js
  let functionV = function(p1,p2,...){
  	내용;
  	return data;
  }
  functionV : 함수객체
  arraw function : (p1, p2, ...) => {
    내용;
    return data;
  }
  ```

  ```js
  //함수 정의
  function add(x, y){
      return x+y;
  }
  
  //함수 사용
  let sum = add(10,20);
  console.log("add(10,20 = ", sum);
  
  //익명 함수
  let substarct = function(x, y){
      return x - y;
  }
  console.log("substract(20,10) = ", substarct(20,10), typeof substarct);
  
  //arrow function
  let divide = (x, y) => console.log(`divide(${x},${y}) = `, x/y);
  divide(20,10);
  
  //함수 선언 및 실행
  let multiply = ((x,y)=>{console.log(`multiply(${x}*${y} = `, x*y)})(20,10);
  
  //클로져
  //함수에서 다른 함수 리턴
  function makeAdder(x){
      let y = 1; //makeAdder function local variable
      return function(z){
          y = 100; // 외부함수 local variable 사용
          return x+y+z;
      }
  }
  
  let add5 = makeAdder(5);
  let add10 = makeAdder(10);
  console.log(add5(2), add5);
  console.log(add10(2), add10);
  
  //클로져
  function multi(n){
      return function(){
          return n *= n;
      }
  }
  
  let multi5 = multi(5);
  let multi10 = multi(10);
  console.log(multi5, multi5());
  console.log(multi10, multi10());
  
  //재귀함수
  function factorial(n){
      if(n === 1){
          console.log('호출 끝');
          return 1;
      }
      else{
          console.log('호출' + n);
          return n*factorial(n-1);
      }
  }
  console.log("10!", factorial(10));
  ```

  

