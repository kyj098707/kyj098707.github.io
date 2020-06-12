---
layout: post
title: Arduino/Speakr & Sensor
---
## **_<span style="color:red"> 1_Speaker </span>_**
1. 스피커 출력
    - PWM 신호를 사용하여 단음재생
        - tone함수에서 음의 주파수를 지정하여 사용
        - 50% duty cycle 사용
    - tone(pin, frequency, duration)
        - 한 번에 하나의 음을 재생
        - 다른 핀을 통해 재생중이라면 호출해도 소용 없음
        - 동일한 핀을 통해 다시 호출하면 새로운 톤이 재생
    - noTone(pin)
        - toneㅎ마수로 인해 생긴 출력 정지
    - tone과 noTone을 사용하려면 주파수정의 헤더파일( 각음의 높이에 해당하는 주파수 정보) 라이브러리를 설치
    - PWM신호를 활요한 아날로그 출력에 해당한다.<br/><br/>

## **_<span style="color:red"> 2_Sensor </span>_**
- 아날로그 신호의 입력에 해당
- ADC를 통한 디지털 변호나 과정을 포함
- analogRead()함수의 활용

1. 온도 센서로 섭씨온도 값 구하기
    - 양자화된 값 읽기
        - ```int reading = analogRead(55);```
    - 실제 전압으로 변환
        - ```floating voltage = reading*5.0/1024.0;```
    - 섭씨 온도로 변환
        - ```float temperatureC = voltage * 100;```

1. 조도 센서
    - 광량에 반비례하여 저항 변화

## **_<span style="color:red"> 3_이번 포스팅 맺는말 </span>_**
1. 센서
    - 자연계의 아날로그 양을 측정하는 장치
    - ADC를 통해 양자화된 값을 mc로 입력
    - 온도 센서 : 온도에 비례하는 전압 출력
    - 조도 센서 : 광량에 반비례하여 저항 변화
1. 스피커
    - 아날로그 신호로 소리 재생이 가능한 장치
    - PWM 신호를 사용하여 단음 재생이 가능
    - 재생하고자 하는 음의 주파수를 tone 함수에 사용하여 단음 재생이 가능하다. 

