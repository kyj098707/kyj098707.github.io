---
layout: post
title: Arduino/SerialCommunication
---
## <span style="color:red"> ```1_UART통신``` </span>
- 하드웨어로 지원되는 기능
- 메가2560은 4개, 우노는 1개의 채널 제공
- 하나의 채널에는 하나의 장치만 연결 가능

1. SoftwareSerial 클래스
    - 하드웨어로 지원되는 UART통신을 소프트웨어로 에뮬레이션
    - 우노의 경우 하나의 UART채널만 존재, 프로그램 업로드에 사용되므로 UART통신을 위해 흔히 사용
    - 메가2560의 경우 개의 채널이 존재, 흔히 사용되지 않음

```C
#include <SoftwareSerial.h>//보내는 친구
SoftwareSerial mySerial(4,5);
int button_pin = 2;   
```
<br/><br/>

