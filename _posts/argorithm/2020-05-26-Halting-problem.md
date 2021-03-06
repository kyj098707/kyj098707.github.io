---
layout: post
title: 앨런 튜링의 Hating problem 설명, 증명
---
## 1. 앨런 튜링 Halting problem
============================
### 안녕하세요 여러분,
### 이번 포스팅에서 다룰 내용은 앨런 튜링의 정지 문제입니다.

### 컴퓨터 프로그래밍을 하다보면 정말 컴퓨터가 연산도 잘하고 우리가 코딩을 
### 잘못 짜게 되면 오류가 난 부분도 잘 찝어주고 못하는게 뭐가 있나 생각이 듭니다.

### 하지만 이런 컴퓨터도 못하는 문제가 있다는 사실을 알고 계신가요?
### 이러한 내용을 컴퓨터 공학의 아버지라고 불리는 앨런튜링이라는 사람이 다루었습니다.

### 결론부터 말하자면 컴퓨터는 프로그램이 연산이 종료가 되나 안 되나,
### 컴파일을 할 때 이 프로그램이 무한 루프에 빠지나 안 빠지나를 알 수 없습니다.

### 예시로 간단한 c의 코드를 보여드리면 

``` c
#include <stdio.h>

int main(){
    while(1){
        printf( "Hello, world"); 
    }
    return 0;
}
```

### 컴퓨터는 이 부분에서 오류를 집어내지 못합니다.

## * 즉 컴퓨터는 프로그램을 보고 이 프로그램이 정지를 할지, 아니면 계속해서 실행이 되는지 알지 못합니다. 

### 그래서 저희가 하는 게임이 한번씩 튕기고, 프로그램들이 갑자기 뚝 멈추고 하는 것이 컴퓨터가
### 프로그램이 돌다가 특정 구간에서 무한루프에 빠지게 되고 컴퓨터는 이를 인지하지 못해서 발생하는 것이죠!

### " 아뉘 근뒈 컴퓨터가 왜 모른다고 확정하는 겁니까? 당신이 컴퓨터 친구도 아니고 그걸 어떻게 아쉽뉘까?"

### 자자 그러면 증명을 해보져!     

## * 앨런튜링의 Hating problem 증명

### 이 증명을 알기 위해서는 먼저  *귀류법 에 대해서 알아야 합니다.
### 귀류법을 모르신다면 그냥 그려려니 하시면 됩니다.( 사실 저도 잘 모릅니다.)

## 1. 만약 무한루프를 판단할 수 있는 func(p,i)가 존재한다고 가정합니다.(여기서 p는 소스코드이며, i는 p의 매개변수입니다)
```c
#include <stdio.h>
bool func(p,i){//무한루프인지 판단하는 함수
    if(p == "무한루프") return false;
    else return true;
}

bool func2(p,i){
    if (func(p,i) == false){//받은 p 함수가 무한루프 안에 있으면 true를 반환 아니면 계속 abc를 출력
        return true;
    }
    else{
        while(1){
            printf("Abc");
        }
    }
} 
```
### 우리는 쉽게 어떠한 함수가 false를 받으면 true값을 반환하고
### 아니면 printf("Abc")의 동작을 하는 프로그램을 만들 수 있습니다.
### func이라는 함수가 존재하면 당연히 이 함수가 적용된 func2도 있을 수 있겠죠?
### 근데 여기서 func2(func2(i))를 하면 어떤 결과가 나올까요?
### 1. func2(func2(p,i))는 어떤 값이 나올까?
### 1) func2(fun2(p,i))가 true 인 경우
### 2) func2(p,i)는 false 
### 3) func(p,i)는 false 값을 반환 하게 된다.
### 4) func2(func2(p,i))는 func2(false값 반환 함수)가 되므로 func2는 계속 abc가 출력이 된다.
### 5) 1),4)가 모순이되어 func는 존재할 수 없다.
### ...
### 1) func2(fun2(p,i))가 계속 반복 될 경우
### 2) func2(p,i)는 true
### 3) func(p,i)는 종료하는 함수
### 4) func2(func2(p,i))는 func2(무한루프 함수)가 되므로 func2는 true가 반환 된다.
### 5) 1),4)가 모순이되어 func는 존재할 수 없다.

## 이상 정리 끗

