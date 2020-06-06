---
layout: post
title: 컴퓨터 구조 Orientation
---
## 1> 무엇을 배울 것인가? 
#### 1) Computer architecture 포스팅들에서는 당연하겠지만 컴퓨터 구조에 대해서 배울 것이다.
#### 2) 조금 더 자세하게 CPU, memory system, I/O device, bus, Cache, internal & external memory,
####    interconnection mechanism, computer arithmeti 등에 대해 공부할 것이다. 
---
## 2> 컴퓨터 구조란 무엇일까?
#### 이는 두 가지 관점으로 나눌 수 있다
#### 1) Hardware desinger 관점 : 컴퓨터 구조를 회로, 구성요소(components), 타이밍, 기능성, 디버깅 제거의 관점으로 컴퓨터 구조를 바라보고
#### 2) Computer architect 관점 : 컴퓨터 구조를 high-level 구성요소와 그들으 어떻게 효율적으로 조합시키고 상호작용 시킬지에 대해서 바라본다.
---
## 3> Architecture & Organization
#### 둘 다 한국어 뜻으로 구조의 의미를 가지고 있다.
#### 하지만 이 두 개는 컴퓨터 구조에서 조금 씩 다른 의미를 가지고 있다.
#### 1) Architecture(구조) : 컴퓨터 시스템 속성들 중에서 프로그래머(system)에게 보이는 속성들(attributes)이다.
#### 비트의 수, 입출력 메커니즘, 명령어 세트, 데이터 표현에 사용되는 비트의 수, I/O 메커니즘, 주소지정(addressing) 방식 등이다.
#### 2) Organization(조직) : 조직은 쉽게 설명을 하자면 구조들의 특성을 구현하는 방법으로도 생각을 할 수 있다. 프로그래머들에게 보이지 않으며
####                         예를 들면 제어신호, 기억장치 제조기술등을 의미한다.
---
## 4> 컴퓨터랑 우리가 소통을 하는 방식
#### 우리는 사람말을 쓰고, 컴퓨터는 컴퓨터말을 쓴다.
#### 그럼 우리가 하는 사람말을 컴퓨터는 어떻게 받아 드릴까?
#### 바로 컴파일러와 어셈블러라는 통역사들의 변환으로 서로 소통을 하게되나. 변환과정을 설명을 해보면
#### High level language Program이 있다. 여기서 High level language는 사람들이 쉽게 알아들을 수 있는 언어들을 이야기한다.(ex.C언어,java,python)
#### high level language를 우리는 컴파일을 한다. 그러면 컴파일러가 돌아가게 되고 컴파일러는 high level language를 assembly language로 바꾼다.
#### 그럼 이런 assembly language를 어셈블러가 기계어로 바꾸게되고 , 해석기가 이것을 보고 컴퓨터에게 신호를 주게 된다.
#### 대략적인 순서를 보면 다음과 같다.
#### high level language Program ---> assembly language Program ---> machine language program ---> control signal
#### '                       '(compiler)'                     '(assembler)'           '(machine interpretation)
---
## 5> 복잡한 컴퓨터 시스템
#### 현재 컴퓨터 시스템은 매우 복잡한 시스템을 가지고 있다.(수백만 가지의 전자회로를 가지고 있다.)
#### 우리는 이러한 컴퓨터 시스템을 두 가지 관점으로 이야기할 수 있다.
#### structure : 컴포넌트들이 어떤 식으로 연결되어 있는지
#### function : 이런 structure의 구성요소들이 어떤 기능을 하는지
---
## 6> CPU
#### 우리가 움직이고, 생각하고 하는 것은 우리의 뇌로 인해 가능한 일들이다.
#### 컴퓨터가 움직이고 생각하는 것 또한 컴퓨터의 뇌로 인해 가능한 일일 것이다.
#### 그러면 이러한 컴퓨터 뇌는 무엇일까?
#### 우리는 이것을 CPU라고 부른다.
#### CPU는 뒤에서 더 자세하게 다루게 될 것이다.
#### CPU의 구성요소는
#### control unit , ALU, Registers, CPU interconnection들이 있다.
#### 각각의 역할을 살펴보면
#### 1) control unit : cpu의 작동을 제어하게되며 이는 크게 보면 컴퓨터의 작동을 제어한다.
#### 2) ALU : 컴퓨터 데이터의 PROCESSING의 기능을 수행한다. 산술연산 또는 논리연산
#### 3) Register : CPU의 저장공간이다. 앞으로 배울 컴퓨터 구조에서 REGISTER라는 이름이들어간 구성요소들은 보통 저장소의 개념으로 보면 편할것이다
#### 4) Cpu interconnection : cpu 내부장치들의 상호작용을 도와주는 친구이다.
###### .
###### .
###### .
###### .
###### .
###### .
###### . 
## 이상 끗!