---
layout: post
title: 상위 관점에서의 컴퓨터 기능과 상호작용(A Top-Level View of Computer Function and Interconnection)
---
## <span style="color:blue"> 1> 폰 노이만 구조</span>
#### 현재 컴퓨터의 구조는 존 폰 노이만(john von Newuman)의 구조를 가지고 있다.
#### 폰 노이만의 구조는 3가지의 컨셉을 기반으로 두고 있다.
#### 1. Data와 instruciton 은 하나의 read-write 메모리에 저장되어 있다.
#### 2. 이러한 메모리는 주소를 가지고 있으며 어떤 데이터를 가지고 있던 접근이 가능하다.
#### 3. 명령어들은 연속적으로 실행이 일어난다.
####  반대되는 개념으로 hardwired program(선이 연결되어 있는 프로그램) 이있다.
---
## <span style="color:blue"> 2> Hardware와 Software의 접근방식 Component</span>
#### 내가 어떤 수를 곱하고 싶다고 하면
### 1 : Hardware에서는
### Data -> 곱셈연산기 -> result
### 2: Software에서는
### DATA -> 명령어를 넣은 연산기 -> result
#### 이런형식이 된다.
#### 그런데 내가 만약 여기서 나눗셈을 하고싶다고 하면 hardware에서는 곱셈연산기를 통체로 바꿔야하지만
#### software에서는 간단히 명령어만 고치면 된다.
#### --> 작업에서 바꾸고 싶은 것이 있을 때 hardware는 싹 다 바꿔야하지만 software는 코드만 바꿔주면 된다.
---
## <span style="color:blue"> 3> 중요 구성요소 Component</span>
#### *1. CPU*
#### - 명령어 해석기
#### - 산술과 논리 연산 기능의 모듈을 가지고 있다.
#### *2. I/O Components*
#### 1) input module : 외부에서 값을 가져오는 것
#### 2) output module : 결과 값을 내보내 주는 것
#### *3. CPU 내부의 구성요소들(*중요한 친구들)*
#### - PC(Program Counter) : 다음번 실행 될 명렁어의 주소를 가지게 된다.
#### - IR(Instruction Register) : 명령어를 저장하는 레지스터, PC가 가르킨 명령어를 지니게 된다.
#### - MBR(Memory Buffer Register) : 출력을 할 데이터, 메모리로 갈 데이터들을 저장한다.
#### - MAR(Memory Address Register) : 데이터들이 어디로 갈지의 주소를 가지게 된다.
#### - I/O AR(Input/output address register) : 어느 IO디바이스 인지 가르키는 주소값을 저장한다.
#### - I/O BR(Input/output buffer register) : IO 모듈과 CPU사이에 데이터를 입출력 할 때 데이터를 잠시 저장한는 곳
---
## <span style="color:blue"> 4> Instruction cycle </span>
#### CPU가 명령을 처리하는 기본적인 사이클은 
#### 명령이 시작되고 -> 다음 명령어를 가져온다. 다하면 중지이고 이 과정속에서 패치(가져오는 것)은 매우 중요한 역할을 한다. 이 과정을 좀 더 자세하게 살펴 보자
#### *1) Fetch cycle*
#### 1: 프로세서가 주소 정보를 줘서 주소 정보에 해당되는 위치에 있는 명령어를 가지고 온다.
#### 2: PC는 다음 패치해올 명령어의 주소값을 가지고 있는 상태.
#### 3: IR은 PC에 저장된 주소 값을 토대로 명령어를 가지고 온다.
#### 4: 명령어를 토대로 AC에 저장하거나 메모리는 제어하는 등 그 값을 사용하며 종료될 때 까지 반복한다. 
#### *2) Instruction cylce*
#### 앞서 명령 사이클이 명령어를 시작하고 다음 명령어를 가져오고 하는 것이 기본적이었다. 이를 좀 더 세부적으로 본다면
#### Instruction address calculation(명령어 주소를 계산) 
#### >> Instruction fetch(명령어를 가지고 온다.)
#### >> Instruction operating decoding(명령어 작동 해석)
#### >> Operand address calculation(피연산자 주소 계산)
#### >> Operand fetch (피연산자를 가지고 온다.)
#### >> Data operation (데이터 작동) 
#### >> Operand fetch (피연산자를 가지고 온다.)
#### >> Opearnd store (피연산자를 저장한다.)
#### 여기서 명령어를 가져오고 , 피연산자를 가져오고 , 피연산자를 저장하는 것은 메모리 쪽에서 하는 일이고 나머지는 CPU에서 하는 일들이다.
---
## <span style="color:blue"> 5> Interrupts Component</span>
#### *interrupt* : 효율성을 위해 만들어졌으며, 프로세서는 유저 프로그램을 계속 진행하면도 들어오는 interrupt를 처리고하려고 했다. interrupt의 종류를 알아보고 처리과정을 자세히 알아보자! 
#### *1) Interrupt의 종류*
#### 1. Program) 명령어가 실행되는 결과로부터 실행될 수 있는 신호, overflow, divison by zero, 메모리양의 초과 등이 있다.
#### 2. Timer) 프로세서 내부에 있는 타이머에 의해 발생될 수 있는데, 운영체제가 특정조건에 따라서 실행을 할 수 있게 도와준다.
#### 3. Hardware failure) 하드웨어로 일어나는 문제로 가장먼저 고쳐야하는 부분이다.
#### 4. I/O) 입출력에 의해 생기는 Interrupt로 가장 많이 사용되며 , 입력이 끝난 것을 알려준다.
