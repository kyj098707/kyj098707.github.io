---
layout: post
title: 상위 관점에서의 컴퓨터 기능과 상호작용(A Top-Level View of Computer Function and Interconnection)
---
## **_<span style="color:blue"> 1_ 폰 노이만 구조</span>_**
* 현재 컴퓨터의 구조는 존 폰 노이만(john von Newuman)의 구조를 가지고 있다.
* 폰 노이만의 구조는 3가지의 컨셉을 기반으로 두고 있다.
1. Data와 instruciton 은 하나의 read-write 메모리에 저장되어 있다.
2. 이러한 메모리는 주소를 가지고 있으며 어떤 데이터를 가지고 있던 접근이 가능하다.
3. 명령어들은 연속적으로 실행이 일어난다.
* 반대되는 개념으로 hardwired program(선이 연결되어 있는 프로그램) 이있다.
* . 
---
## **_<span style="color:blue"> 2_ Hardware와 Software의 접근방식 Component</span>_**
* 내가 어떤 수를 곱하고 싶다고 하면
1. Hardware에서는
* Data -> 곱셈연산기 -> result
2. Software에서는
* DATA -> 명령어를 넣은 연산기 -> result
* 이런형식이 된다.
* 그런데 내가 만약 여기서 나눗셈을 하고싶다고 하면 hardware에서는 곱셈연산기를 통체로 바꿔야하지만
* software에서는 간단히 명령어만 고치면 된다.
* --> 작업에서 바꾸고 싶은 것이 있을 때 hardware는 싹 다 바꿔야하지만 software는 코드만 바꿔주면 된다.
* .
---
## <span style="color:blue"> 3_ 중요 구성요소 Component</span>
#### *1. CPU*
#### - 명령어 해석기
#### - 산술과 논리 연산 기능의 모듈을 가지고 있다.
#### *2. I/O Components*
#### 1) input module : 외부에서 값을 가져오는 것
#### 2) output module : 결과 값을 내보내 주는 것
#### *3. CPU 내부의 구성요소들(중요한 친구들)*
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
#### **interrupt의 필요성**
#### 프로세서는 프린트 명령어를 가지고오고 , 프린트 명령어가 실행이되고, 프로세서는 프린트 작업이 잘 진행되었는지 확인을 하는 과정이 필요하다. 하지만 여기서 큰 문제가 발생하게 되는데 프린트 명령이 시작되고 끝 날 때까지 이 프로세서는 놀게되는 것이다.(프린트명령어 시간이 프로세서(CPU)작업속도에 비해 현전히 느리다.) 
#### **이런 현상을 Interrupt로 해결할 수 있다.**
#### 프로세서가 프린트 명령어를 가지고오고
#### >> 프린트 명령어가 실행이 될 때
#### >> 다음 명령어를 가지러 가고
#### >> 프린트명령어가 끝이 났다는 것을 interrupt로 알리고
#### >> 프로세서는 하던 것을 멈추고 interrupt handler로 가게 되는 형식
#### 이로인해 CPU의 작업 손실을 최대한으로 막을 수 있다.
--
## <span style="color:blue"> 6> I/O function</span>
#### I/O module은 메모리를 거치지 않고 프로세서랑 바로 데이터를 주고 받을 수도 있다. 아예 프로세서가 I/O module에게 메모리에 직접 접근하라고 권한을 넘겨주는 방식도 있다. 이것을 DMA(Direct Memory Access)라는 방식으로 부른다.
---
## <span style="color:blue"> 7> Computer Modules </span>
#### 지금부터는 컴퓨터 모듈에 관해 살펴 볼 것이다. 전체적으로 데이터를 어떤 식으로 주고 받는지를 살펴볼 것이기 때문에 집중해서 잘 따라오면 좋을겁니닷!
#### 1) Memory to Processor : 프로세서가 주체, 프로세서는 메모리에 접근해서 데이터나 명령어를 read한다.
#### 2) Processor to Memory : 프로세서는 데이터를 메모리에서 write할 수 있다.
#### 3) I/O to Processor : 프로세서는 I/O module을 통해서 I/O device의 데이터를 read할수 있다.
#### 4) Processor to I/O : 프로세서는 데이터를 I/O device에 전송
#### 5) I/O to or from Memory : 아까 위에서 설명한 DMA가 여깃에 속한다. 즉 I/O 모듈이 CPU에게 Memory에 직접 access를 할 수 있또록 허가를 받은 루트
#### Memory에 들어오는 명령어 : Read
---
## <span style="color:blue"> 8> Bus interconnection </span>
#### 컴퓨터 구조에서 버스는 2개 이상의 장치가 연결되어서 서로 데이터를 주고 받는 등의 커뮤니케이션을 할 때 쓰이는 <span style="color:red">통로.</span> 가장 큰 특징이 이 bus를 연결된 장치들이 공유한다는 것, 여러 연결된 디바이스들이 signal을 주고 받을 때 한장치가 보내면 다른 장치는 그 signal을 받아야해서 두 장치가 한번에 데이터를 송신할수는 없다.  보통 벗느느 여러개의 라인으로 구성되어 있으며 라인은 한 binary bit를 전송할수 있고 보통 보내고 싶은 데이터의 bit만큼 라인이 존재한다. Bus는 컴퓨터 구조 여러개를 연결해야 하기 때문에 컴퓨터 내부에 여러 곳에 존재하는데 이들 중 프로세서,메모리,I/O를 연결하는 BUS가 있고 얘네들을 특별히 SYSTEM BUS라고 부른다. 대부분의 컴퓨터 연걸구조는 SYSTEM BUS를 기반으로하고 SYSTEM BUS는 대락 50-100개 정도의 라인으로 구성되어 있다.
#### --> 또한 이 라인들은 기능에 따라 3가지로 분류를 할 수 있다.
#### 1. Data Line - 시스템 모듈간에 데이터를 옮길 때 사용되는데, 얘네를 여러 가닥 모아서 Data Bus라고도 한다.
#### 32,64,128 와 같이 짝수의 배수 개만큼 data line을 구성하고 이 라인의 개수를 data bus의 width라고 한다.
#### 왜냐하면 라인의 개수는 몇 비트를 전송할 수 있냐를 결정하기 때문이다.
#### 2. Address Line - 똑같이 이 Line이 합쳐져 address bus가 되며 , 말 그래도 주소를 전송한다. data bus로 이동하는 data의 출발지와 목적지를 담게 되며 프로세서가 메모리를 read/write 할려고 할 때 address line에 메모리의 주소를 넣게 된다. 여기도 당연히 width가 존재하며, 이는 메모리의 최대 용량을 결정한다. 왜냐하면 이 address line이 가져올 수 있는 가장 큰 비트가 메모리의 마지막주소이기 때문이다. address line 내의 bit에서도  high order 과 low order로 나뉘게 되는데 high는 어느 모듈로 갈것인가를 알려주고 low는 모듈내의 상세주소를 알려주게 된다.
#### 3. Control Line - access 와 데이터라인,어드레스 라인의 사용을 컨트롤 할 때 사용 된다. 데이터라인과 어드레스 라인은 모든 컴퓨터 구성품들이 공유를 하는데, 어떤 모듈이 버스를 사용하는지 컨트롤 해줄 필요가 있다. 그래서 control signal은 명령어도 보낼 뿐만 아니라 timing정보도 전송해준다.
