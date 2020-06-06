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
#### Hardware에서는
## Data -> 곱셈연산기 -> result
#### Software에서는
## DATA -> 명령어를 넣은 연산기 -> result
#### 이런형식이 된다.
#### 그런데 내가 만약 여기서 나눗셈을 하고싶다고 하면 hardware에서는 곱셈연산기를 통체로 바꿔야하지만
#### software에서는 간단히 명령어만 고치면 된다.
#### --> 작업에서 바꾸고 싶은 것이 있을 때 hardware는 싹 다 바꿔야하지만 software는 코드만 바꿔주면 된다.
---
## <span style="color:blue"> 3> 중요 구성요소 Component</span>
#### 1. CPU
#### - 명령어 해석기
#### - 산술과 논리 연산 기능의 모듈을 가지고 있다.
#### 2. I/O Components
#### 1) input module : 외부에서 값을 가져오는 것
#### 2) output module : 결과 값을 내보내 주는 것
#### 3. CPU 내부의 구성요소들(*중요한 친구들)
#### - PC : 다음 명령어가