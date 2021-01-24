자바 스크립트 기초
=======================
- - -   

## 0 변수

### 0.1 변수 선언
    var x; //변수
    let y; //변수
    const z; //상수

#### 0.1.1 var과 let의 차이점
    var과 let의 차이점은 아래 링크의 블로그에 자세히 설명되어있다.
    [링크](https://velog.io/@bathingape/JavaScript-var-let-const-%EC%B0%A8%EC%9D%B4%EC%A0%90[link])


### 0.2 
    Wrapper 클래스 Wrapping

    변수 타입
    부울 : boolean   
    정수, 실수 : Number   
    문자, 문자열 : String   
    null(값 없음) : null
    undefind(미정의) : undefind

    ex)   
    var x = 3;    
    var x = new Number(3); 위와 같은 뜻   

    var y;   
    if(y === undefind){} (O)   
    if(Y === "undefind"){} (X)  

## 1 array [예제](01array.html "예제링크")
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



## 참조
    1. 자바스크립트(Javascript) 강의 강좌 Quick Start + DOM 프로그래밍 for VanillaJS: https://www.youtube.com/playlist?list=PLq8wAnVUcTFWhQrIXNN6kPYXJA6X2IQM4


     



