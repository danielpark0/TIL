# 02. JavaScript_commnad

1. if 조건문

   ```js
   if(조건식) {
   	실행문;
   }
   ```

   ```js
   let month = prompt("월 입력 :", "");
   if(month==1||month==3||month==5||month==7||month==8||month==10||month==12){
       console.log(`${month}월은 31일 까지 있습니다.`)
   }
   else if(month==2){
       console.log(`${month}월은 28일 까지 있습니다.`)
   }
   else if(month==4||month==6||month==9||month==11){
       console.log(`${month}월은 30일 까지 있습니다.`)
   }
   else{
       console.log(`${month}월이 맞는지 확인하세요.`)
   }
   ```

   

2. switch 문

   ```js
   switch(변수명){
   	case 변수값 : 실행문
   								break;
   	case 변수값 : 실행문
   								break;
   	default : 기타 실행문;
   }
   ```

   ```js
   switch(month){
       case '1':
       case '3':
       case '5':
       case '7':
       case '8':
       case '10':
       case '12': console.log(`${month}월은 31일까지 있습니다.`)
               break;
       case '2': console.log(`${month}월은 28까지 있습니다.`)
               break;
       case '4':
       case '6':
       case '9':
       case '11': console.log(`${month}월은 30일까지 있습니다.`)
               break;
       default: console.log(`${month}월이 맞는지 확인하세요.`)
   }
   ```

   

3. 반복문

   1. while 문

      ```js
      초기값;
      while(조건식){
      	참일때 실행문;
      	증감식;
      }
      ```

      ```js
      let index = 1;
      let sum = 0;
      while(index < 11){
          sum += index; // sum = sum + index;
          index++; // index = index + 1;
      }
      console.log(`1~10 합 : ${sum}`);
      ```

      

   2. do while 문

      ```js
      초기값;
      do{
      	실행문;
      	증감식;
      }while(조건식);
      ```

      ```js
      let index = 1;
      let sum = 0;
      do{
          sum += index;
          index++;
      }
      while(index < 11);
      console.log(`1~10 합 : ${sum}`);
      ```

      

   3. for 문

      ```js
      for(초기값; 조건식; 증감식){
      	실행문;
      }
      
      for(데이터 in|of 리스트 데이터){
      	실행문;
      }
      ```

      ```js
      let sum = 0;
      for(index = 1; index < 11; index++){
          sum += index;
      }
      console.log(`1~10 합 : ${sum}`);
      ```

4. 기타 (return - 함수종료(반환), break - 반복문 종료, continue - 뒤에 skip하고 반복문)

   ```js
   let sum = 0;
   for(index = 1; index< 11; index++){
       if(index%2==0) continue;
       sum += index;
   }
   console.log(`1~10 홀수 합 : ${sum}`);
   
   //nested for문
   for(i1 = 1; i1 < 10; i1++){
       for(i2 = 1; i2 < 10; i2++){
           console.log(`${i1} * ${i2} = ${i1*i2}`);
       }
   }
   ```

   