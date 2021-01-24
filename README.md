자바 스크립트 기초
=======================

    [자바스크립트(Javascript) 강의 강좌 Quick Start + DOM 프로그래밍 for VanillaJS] :
    <https://www.youtube.com/playlist?list=PLq8wAnVUcTFWhQrIXNN6kPYXJA6X2IQM4/> 
    위 강좌를 듣고 실습 및 정리한 문서이다.

- - -   

## 0 변수 [예제](00variation.html, "00variation.html")

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

## 1 array [예제](01array.html, "01array.html")
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

## 2 object [링크](02object.html, "02object.html")
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

## 3 json [링크](03json.html, "03json.html")
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

## 참조
    1. [자바스크립트(Javascript) 강의 강좌 Quick Start + DOM 프로그래밍 for VanillaJS](https://www.youtube.com/playlist?list=PLq8wAnVUcTFWhQrIXNN6kPYXJA6X2IQM4 ,"youtube")


     



