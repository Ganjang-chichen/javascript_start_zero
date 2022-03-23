자바 스크립트 기초
=======================

    [자바스크립트(Javascript) 강의 강좌 Quick Start + DOM 프로그래밍 for VanillaJS] :
    <https://www.youtube.com/playlist?list=PLq8wAnVUcTFWhQrIXNN6kPYXJA6X2IQM4/> 
    위 강좌를 듣고 실습 및 정리한 문서이다.

- - -   

## 0 변수 [예제](00variation.html)

### 0.1 변수 선언
    var x; //변수
    let y; //변수
    const z; //상수

#### 0.1.1 var과 let의 차이점
    var과 let의 차이점은 아래 링크의 블로그에 자세히 설명되어있다.
    [링크](https://velog.io/@bathingape/JavaScript-var-let-const-%EC%B0%A8%EC%9D%B4%EC%A0%90,"link")


### 0.2 Wrapper 클래스 Wrapping

    변수 타입
    부울 : boolean   
    정수, 실수 : Number   
    문자, 문자열 : String   
    null(값 없음) : null
    undefind(미정의) : undefind

    ex)   
    var x = 3; // 변수 선언 시실제 아래의 과정을 거치지만 생략
    var x = new Number(3);

    var w; // undefind 또한 하나의 상태
    if(w === undefind){} (O)   
    if(w === "undefind"){} (X)  

## 1 array [예제](01array.html)
### 1.0 배열
    배열 기본 사용법
        var arr = new Array();

    배열 값 삽입
        arr.push(5);
        arr.push(10);
        arr.push("hello");
        arr[3] = "hi";
        arr[7] = "fxxx";
    
    위와같이 C나 JAVA 등과 같이 배열 안에 서로 다른 타입을 넣어도 됨
    심지어 object나 또 다른 array도 넣을 수 있음

### 1.1 splice

    splice 메소드를 이용한 array 관리
    
    var arr1 = new Array(5,10,21,"hello"); //원본배열
        [5,10,21,"hello"]

    arr1.splice(1); // 1번째 이후 삭제
        [5]

    arr1.splice(1,1); // 1번째 이후 1개 삭제
        [5,21,"hello"] 

    arr1.splice(1,2); // 1번째 이후 2개 삭제
        [5,"hello"]

    arr1.splice(1, 0, "hoho"); // 1번째 위치에 "hoho" 삽입
        [5,"hoho",10,21,"hello"]

    arr1.splice(1, 1, "hoho"); // 1번째 위치에 "hoho" 대체
        [5,"hoho",21,"hello"]

## 2 object [링크](02object.html)
### 2.0 object 선언

    var exam = new Object();

### 2.1 속성 추가
    exam.kor = 30;
    exam.eng = 70;
    exam.math = 80;

        {kor: 30, eng: 70, math: 80}

### 2.2 키를 통한 관리
    exam["kor"] = 40;
    exam["eng"] = 60;
    exam["math"] = 90;
    exam["science"] = 80;

        {kor: 40, eng: 60, math: 90, science: 80}

### 2.3 초기화
 
        exam = {"kor" : 40, "eng" : 60, "math" : 90, "science" : {physics : 50, chemistry : 70}};

        exams = {kor : 40, eng : 60, math : 90, science : {physics : 50, chemistry : 70}};

        
   

## 3 json [링크](03json.html)
### 3.1 JavaScript Object Notation >> JSON
    /*          |    JavaScript Object            |     JavaScript Object Notation(JSON)*/
    /*Boolean   |*/ var b = new Boolean(true);  /*|*/   var b = true;
    /*Number    |*/ var n = new Number(4);      /*|*/   var n = 4;
    /*String    |*/ var s = new String("hello");/*|*/   var s = "hello"; var s = 'hello';
    /*Array     |*/ var ar = new Array();       /*|*/   var ar = [];
    /*Object    |*/ var ob = new Object();      /*|*/   var ob = {};

    위를 응용하면 이러한 것을 할 수 있음
        [
            {"id" : 1, "title" : "hello.json"},
            {"id" : 2, "title" : "hi.json"},
            {"id" : 3, "title" : "ho.json"}
        ]
    위 형식이 편리하기때문에 JSON이 JS 뿐만이 아닌 여러곳에서 많이 쓰이게 됨

### 3.2 eval() : 코드가 문자열일때

    코드를 문자열로 받았을 시 eval 메소드로 코드 실행가능
        eval('var x = 30;');
        
        console.log(x);

    일반적으로 외부에서 json 데이타 받았을시
        
        var data = '[ \
            {"id" : "alpha", "pw" : "1234a"}, \
            {"id" : "beta" , "pw" : "121b"}, \
            {"id" : "aaaa" , "pw" : "122b"}, \
            {"id" : "bbbb" , "pw" : "123b"}, \
            {"id" : "bczc" , "pw" : "125b"} \
        ]';
    
    eval 메소드 이용 시

        eval("var ar = " + data + ";");

### 3.3 parse 파서

    Parse 파서 사용

        var data = '[ \
            {"id" : "alpha", "pw" : "1234a"}, \
            {"id" : "beta" , "pw" : "121b"}, \
            {"id" : "aaaa" , "pw" : "122b"}, \
            {"id" : "bbbb" , "pw" : "123b"}, \
            {"id" : "bczc" , "pw" : "125b"} \
        ]';

        var data2 = JSON.parse(data);


        // 파서 사용 시 주의사항 : key 값에 반드시 "" 사용할 것

        var data0 = '[ \
            {id : "alpha", pw : "1234a"}, \
            {id : "beta" , pw : "121b"}, \
            {id : "aaaa" , pw : "122b"}, \
            {id : "bbbb" , pw : "123b"}, \
            {id : "bczc" , pw : "125b"} \
        ]'; // 에러 발생

        var data3 = JSON.parse(data0);
        console.log(data3);
            에러발생
            Uncaught SyntaxError: Unexpected token i in JSON at position 15 at JSON.parse (<anonymous>)

        다시 문자열 화

        var json = JSON.stringify(data2);
        
            [{"id":"alpha","pw":"1234a"},{"id":"beta","pw":"121b"},{"id":"aaaa","pw":"122b"},{"id":"bbbb","pw":"123b"},{"id":"bczc","pw":"125b"}]

        문자열 화 시에는 키값에 ""꼭 할 필요 없음
        그러나 문자열화 된 값에는 "" 자동으로 처리됨

        var data5 = [ 
            {id : "alpha", pw : "1234a"}, 
            {id : "beta" , pw : "121b"}, 
            {id : "aaaa" , pw : "122b"}, 
            {id : "bbbb" , pw : "123b"}, 
            {id : "bczc" , pw : "125b"} 
        ];

        var json2 = JSON.stringify(data5);

            [{"id":"alpha","pw":"1234a"},{"id":"beta","pw":"121b"},{"id":"aaaa","pw":"122b"},{"id":"bbbb","pw":"123b"},{"id":"bczc","pw":"125b"}]

## 4  연산자 [링크](04calculator.html)
### 4.1 == === 의 차이
        
    A == B : A 와 B의 값이 같은가?
    A === B : A 의 주소값과 B의 주소값이 같은가?

    예제
        var x = 3;
        var y = 3;

        console.log(x == y);    // true
        console.log(x === y);   // true

        var v = 4;
        var w = new Number(4);

        console.log(v == w);    // ture
        console.log(v === w);   // false

        
    사실 x와 y의 비교와 v와 w의 비교가 다른 이유는 
    x와 y같이 선언했을 때 x의 박스를 할당 이후 y를 새로 할당하는것이 아닌
    x와 y의 값이 같기 때문에 y주소를 x와 같은 곳으로 향하게 한다.

    그러나 v와 w 같은 경우 v할당 이후 명시적으로 w를 새로 할당하였기 때문에
    v의 주소값과 w의 주소값이 일치하지 않는다. 따라서 false를 띄운다.

### 4.2 묵시적 변환

    자바 스크립트에서는 다음과 같이 컴파일러에서 자동으로 타입변환을 시켜준다.

        console.log(3 - 2);     // 1
        console.log(3 - "2");   // 1
        console.log("3" - 2);   // 1
        console.log("3" - "2"); // 1
        console.log(5 > 3 - 2); // true
        console.log(5 > "3");   // true
        console.log("5" > 3);   // ture
        console.log("5" > "3"); // true
        console.log("3" - "2s");// NaN (숫자가 아님을 뜻함)

## 5  제어구조 [링크](05control_structure.html)
### 제어구조 종류
    조건문 : if, while, do-while
    반복문 : while, for, for-in
    선택문 : else, else if, switch

    for-in문을 제외하고는 다른 언어와 비슷하다.

### for-in
    for-in문은 array나 object의 key 값을 순회한다.

        var ar = ["hello", "hi", "greetings"];
        for(var i in ar){
            document.write(i + " : " + ar[i] + "<br />");
        }

        결과 : 
            1 : hello
            2 : hi
            3 : greetings

        var  data = {"id" : 1, "title" : "hello.json"};
        for(var i in data){
            document.write(i + " : " + data[i] + "<br />");
        }

        결과 :
            id : 1
            title : hello.json


## 참조
    1. [자바스크립트(Javascript) 강의 강좌 Quick Start + DOM 프로그래밍 for VanillaJS] :
    <https://www.youtube.com/playlist?list=PLq8wAnVUcTFWhQrIXNN6kPYXJA6X2IQM4/>


     



