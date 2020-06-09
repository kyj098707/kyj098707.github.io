---
layout: post
title: Arduino/Basic
---
## **_<span style="color:red"> 1_Basic function </span>_**
1. Serial.begin(9600) - serial과 통신을 할 때 setup부분에 사용한다.
1. Serial.print(ln)() - serial모니터에 출력할 때 사용
1. Serial.write() - serial 모니터에 출력할 때 사용
1. **_print와 write의 차이점_**
    - 둘의 차이는 숫자를 보낼 때 발생하게 되는데,
    - write는 아스키코드값으로 바꿔서 출력이되며,<br/>print는 적은 값 그대로를 출력한다.
```c
byte data = 65; //byte는 정수형 자료형, 크기는 당연히 1byte
Serial.println(data); // 65 가출력
Serial.write(data); // 'A'가 출력된다.
```
1. pinMode(핀 번호, 핀 모드) - 핀의 모드를 설정 ex) output,input,input_pullup등이 있다.
    - pinMode(핀 번호, input) : 핀을 입력 상태로 설정하여 센서 값을 읽어오는데 사용한다.
    - pinMode(핀 번호, output) : 핀을 출력 모드로 설정하게 되며, LED를 켜거나 구동하는데 사용할 수 있다.
    - pinMode(핀 번호, INPUT_PULLUO) : 내부의 풀업저항을 사용하는 형태.
1. digitalWrite(핀 번호, 값) - 디지털핀에게 값을 준다.
    - digitalWrite(핀 번호, high) - 5v를 준다. (보통 led를 킬 때 사용)
    - digitalRead(핀 번호, low) - 0v를 준다. (보통 led를 끌 때 사용)
1. digitalRead(pin) - 디지털 핀의 신호 값을 읽는다
    - 결과 값이 high or low로 나오게 된다.

```c
int led = 13;
void setup(){
    pinMode(led, OUTPUT) // 13번 핀을 출력 모드로
}

void loop(){
    digitalWrite(led, HIGH);// 13번 핀에게 5v를 인가 ( = 킨다.)
    delay(1000); // 1000ms(1초)를 기다리고
    digitalWrite(led,LOW); // 13번 핀에게 0V를 인가( = 끈다.)
    delay(!000);
}
```

1. 정리를 하자면,pinMode로 함수로 먼저 출력,입력을 정하고 digitalWrite,digitalRead로 값을 주고 받는다.

1. 이외에 기본적 함수들
    - Serial.available() // 수신된 데이터가 있는지의 여부
    - Serial.print(value,형식)// BIN : 2진법, OCT : 8진법,DEX : 10진법(default) 등등
    - Serial.read() : 데이터를 읽어온 후 시리얼 버퍼에 데이터를 하나 씩 지우는 형태
    - Serial.peek() : 데이터를 읽어온후 버퍼의 데이터를 지우지 않음 <br/><br/>

## **_<span style="color:red"> 2_String </span>_**
1. String의 연산

```c
String str1 = "one string", str2 = "Another string";
int n = 1234;
float f = 3.14;
char c = 'A';
Serial.println(str1); // one string 출력
Serial.println(str1+ " " + str2); // one string Another string 출력
Serial.println(string(n)); // 정수로부터 10진 문자열 생성
Serial.println("string + integer : " + string(n));
Serial.println("string + integer : " + 1234); //오류 --> 문자열과 정수의 덧셈은 안됨
```
1. String 함수
    - string변수1.compareTo(string변수1) : 같으면 true를 반환
    - .length() : 길이 반환
