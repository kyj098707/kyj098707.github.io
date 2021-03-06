---
layout: post
title: C++ 기초; 기존 C언어와의 차이점
---
### 시작하기에 앞서 많은 사람들이 C를 배우지않고 C++을배워도 되냐고 물어본다. 나한테 가르침을 주셨던 교수님은 배워도 된다. 오히려 C를 배우지않고 C++을 배워야 
### C++에서 C의 개념을 사용하지않고 C++을 배울 수 있어 더 좋을 것이라고 하셨다. 그만큼 C와 C++은 많은 부분에서 차이를 들어내고 다르게 사용된다.
### 이번 포스팅에서는 C++에 대해서 기초적인 부분들을 배울 것이고 C와 다른 점들에 대해서 알아 볼 것이다.
### =-=-=-=-=-=-=-=-=-=-=-=--=-==--=-=-=-=-=-=-=-=-=-=--==-=-=-=-=-=-=-=--=-=-=-=-=-=-=-=-=-=-=-=-=-==
```C++
#include <iostream> 
#include <string> 

using namespace std;  // c와다르게 namespace가 있다. < 추후에 다룰 내용>

int main(){//메인함수는 항상 하나여야 한다. 메인함수는 진입점 

    cout << "Enter your name : "; // pritnf가 아닌 cout으로 출력을 한다.
    string name;
    cin >> name; // scanf가 아닌 cin 으로 입력을 받는다.

    cout << "Hello, " << name << endl;
}
```
### 위에서 보이는 코드는 이름을 입력하고 출력하는 형식의 매우 간단한 코드이다.
### 이 코드를 통해 조금이나마 C++에 대해서 알아보자

### 먼저
```C++
#include <iostream>
#include <string>
```
### 이 부분이다. 기존의 c에서도 #이 들어간 부분을 볼 수 있었을 것이다.
### 이런 부분을 헤더파일이라고 하는데 도대체 이 헤더파일이란 것이 멀까?
# 1> 헤더파일
### 헤더파일은 #이 붙어 있는 프로그래밍 코드에서 보통 가장 윗 부분에 있는 녀석들을 의미한다.
### 프로그램은 컴파일 되기전에 항상 전처리기라는 친구가 먼저 프로그램을 들린다
### 그 후 헤더파일을 확인하고 그 헤더파일안에 있는 소스들을 프로그램 안에 넣게 되며
### 이 후 컴파일러가 프로그램에 오고 모든 소스를 읽게된다.
### 컴퓨터는 우리가 아는 것만큼 우리의 마음을 읽지못한다. 그래서 우리가 출력은 이렇게 했으면 좋겟어, 입력은 이렇게 했으면 좋겠어 등등 미리 
### 똑똑하신 분들이 만들어 놓은 코드를 사용해야 입력과 출력을 원하는 것 처럼 할 수 있게되고, 이를 사용하기 위해서 헤더파일을 추가시키는 것이다.
### c++에서의 헤더파일은 c와는 다르게 .h가 붙지 않는 특징을 보인다.
### c에서 제공되는 헤더파일은 거의 모두 c++ 에서도 제공되기 때문에 c의 헤더파일을 사용하지 말고 c++의 헤더파일을 사용하길 권장한다.
### ex) string.h -> cstring, stlib.h -> cstdlib , stdio.h -> cstdio

```C++
using namespace std;
```
# 2> Namespace
### c와 다른 기능으로 c++에서는 namespace라는 개념이 있다.
### 옜날 옜적 여러 회사가 작업을 할 때 회사마다 print의 개념이 달랐고, scan의 개념이 달랐고 각각 변수의 이름이 달라.
### 다른회사끼리 작업을 하여 이를 하나의 프로젝트로 병합시킬 때 에러가 많이 났다고한다.
### 이것을 막기 위해 만든 것이 namespace다
### 삼성 :: cout <<,  LG :: cout << 이런식으로 삼성이라는 네임 스페이스가 존재했고 이 안에 cout을 넣고 다른 회사와 엇갈리지 않게 만드는 용도이다.
### 하지만 우리가 매번 함수를 호출할 때 삼성:: 이런식으로 붙이면 힘들고 귀찮다.
### 그래서 우리가 사용하는 것이 using namespace다.
### 만약 이것을 사용하게 되면 using namespcae 삼성. 이라고 했을 때 cout 의 namespace가 따로 없더라도 컴퓨터는 ' 어 namespace가 원래 필요한데
### 따로 안적혀있네?' 하며 삼성이라는 namespace를 가져오게 된다.
### 이런 느낌으로 원래 cout이 std::cout이지만 매번 이렇게 적으면 코드도 길어지고 손도 아프닌깐 필자는 코딩할 때 맨처음
### using namespace std;를 적고 시작하는 것을 추천하고 보통 다 이것을 적고 시작한다. 
## ==============================================================================

## 생성인자에 대해서도 알아보자 초보자분들이라면 다소 생소할 수 있는 부분들도 있다.
```C++
//arg.cpp
#include <iostream>
using namespace std;

void main(int argc,char* argv[]){
    cout << argc << endl;

    for( int i = 0 ; i < argc ; i++){
        cout << argv[i] << endl;
    }
    cout << "End" << endl;
}
```
### 이 함수는 도대체 뭘까?

### 먼저 main함수는 컴파일러가 가장 먼저 들르는 곳이다. 그래서 프로그램 코드에서 한 개의 메인함수만 올 수 있게 된다.
### 이런 메인함수도 결국 근본은 '함수' 이기 때문에 파라미터를 전달해 줄 수 있다.
### 여기서는 argc, argv를 파라미터로 받고
### 우리가 이 프로그램을 실행할때 파라미터를 같이 넣어줄 수 있는 것이다.
### 이 프로그램명은 arg.cpp이고 컴파일을 하게되면 arg.exe라는 파일이나오며 이를 실행할때
### arg.exe i am kim 이런식으로 입력을 하게되면 총 argc는 4 arv는 arg.exe, i , am , kim 이 저장되여 값이 나오게된다.
### 이 내용을 모두 이해할 필요는 없다. (사실 나도 잘 모른다.) 나중에 가면 구체적으로 배울 것이기 때문에 이런게 있다고 생각하고 넘어가자.

### ===========================================================================================================
## 마지막으로 오늘 다룰 것은 함수 오버로딩에 관해서다
### 함수 오버로딩이란 무엇일까?
### 함수 오버로딩은 쉽게말해서 동명이인의 함수이다.
### 먼저 코드를 보자.
```C++
#include <iostream>
using namespace std;
int findMax(int numbers[],int size){
    int maxValue = numbers[0];
    for(int i = 0 ; i < size; i++)
        maxValue = myMax(maxValue,numbers[i]);
    return maxValue;
}
int findMax(float numbers[],int size){
    float maxValue = numbers[0];
    for(int i = 0 ; i < size; i++)
        maxValue = myMax(maxValue,numbers[i]);
    return maxValue;
}
int main(){
   int intValues[] = {10,20,50,30,5};
   cout << findMax(intValues,5) << endl;//50
   float floatValues[] = {10.5F, 97.3F,50.1F,30};
   cout << findMax(floatValues,4) << endl;//50
   
 }
```
### 메인함수에서 보면 findmax함수가 있는데 이 함수는 배열과 사이즈를 받아서, 가장 큰 값을 뽑아 내는 것이다.
### 실질적인 두 함수의 실행 알고리즘은 같지만 두 함수는 파라미터의 자료형이 다르다.
### c에서는 이렇게 이름이 같은 함수를 허용하지않았지만.
### c++에서는 이름이 같아도 파라미터가 다른함수는 허용을 해주고 있다.
# 이상 기초 끗

