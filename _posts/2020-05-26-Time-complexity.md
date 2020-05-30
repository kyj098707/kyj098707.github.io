---
layout: post
title: 알고리즘에서의 시간 복잡도(Time complexity)
---
# " 시간 복잡도 "
========================
## 저희가 알고리즘을 풀고 공부를 할 때 가장 중요한 친구 중 한명입니다.
## 알고리즘 문제를 풀다보면 거의 모든 문제에는 시간 제한이 있습니다. (1~5초)
## 그러면 1~5초 정도에 저희가 짠 프로그램의 코드가 돌아가야 합니다.

## Q. 엇 그러면 컴퓨터는 1초에 어느정도의 작업을 하나요?
## A. 3~5억번 정도의 연산을 합니다. 하지만 연산에 따라 또 시간이 틀리닌깐 어림잡아서 알면 됩니다.
## Q. 연산의 종류는 머가 있는데요?
## A. 매우 빠르게 진행되는 비트연산자의 AND, OR 부터 해서 더하기 나눗셈등의 단순한 계산연산 부터
##    비교적 시간이 걸리는 값을 입력,출력, 대입, 함수를 호출하는 등 여러 연산들이 있습니다.
## Q. 아니 근데 그러면 1초에 3~5억번이면 이것을 신경을 써야하는 순간이 오나요?
## A. 넵 정말 많이 옵니다. 당장 백준알고리즘만 들어가셔도 시간복잡도를 신경써서 풀어야할 문제들이 많습니다.
##    그리고 같은 문제를 보더라도 어떤 사람은 1초에 끝내는 걸 내가 0.5초만에 끝내면 멋지잖아요?
##    그래서 이 시간 복잡도는 항상 코딩을 할 때 신경쓰셔서 짚고 가셔야할 부분입니다.
## Q. 예를 하나만 들어주세요
## A. 쇼로롭

## ---------------------------------------------------------------------------------------------
## 백준 10808문제) 알파벳 소문자로만 이루어진 단어 S가 주어진다. 각 알파벳이 단어에 몇 개가 포함되어 있는지 구하는 프로그램을 작성하시오.(시간제한 1초, 메모리 256MB)
## ----------------------------------------------------------------------------------------------
## 문제 ) 알파벳 소문자로만 이루어진 단어 S가 주어진다. 각 알파벳이 단어에 몇 개가 포함되어 있는지 구하는 프로그램을 작성하시오.
## 입력 ) 첫째 줄에 단어 S가 주어진다. 단어의 길이는 100을 넘지 않으며, 알파벳 소문자로만 이루어져 있다. 
    

## 밑을 보지마시고 한번 풀어보십시요.
## 어떤식으로 코드를 짜실건가요?(c++)

## 시간 복잡도를 생각하지 않고 풀어빕을 생각하셨으면
## 아마 a를 들고 입력받은 문자열을 쭉 훑고 .. z까지 훑는 방법을 생각하셨을 수도 있습니다.
 
## 하지만 한번만 훑고 이 문제를 해결할 수 있다는 걸 아시나요?  
 

```C++
#include <bits/stdc++.h>
using namespace std;
int alpa[26];
int main(){
    
    string abc;
    cin >> abc;
    for(int i = 0; i < abc.size(); i++){
        alpa[abc[i] - 'a']++;
    }
    for(int i = 0; i< 25 ; i++){
        cout << alpa[i] <<' ';
    }
    cout << alpa[25];

    return 0;
}

```
## 이런식으로 만날 때마다 그 알파벳을 배열에 저장하는 방법입니다.
## 알파벳 갯수만큼 훑으면 시간복잡도는 저 코드의 26배가 됩니다.
  
## 항상 어떻게하면 연산을 최소화 할지 생각하며 코딩을 합시다! ^^7
## 
# < 시간 복잡도 이론>
 
## 시간 복잡도를 조금 더 깊이 알아볼까요?
## 시간 복잡도는 크게 6가지로 나눌 수 있습니다.
## O(1) : 어떤 값이 입력되더라도 연산의 횟수가 일정한 경우
```C++
#include <bits/stdc++.h>
using namespace std;
int main(){
    
    int num1;
    cin >> num1;
    cout << num1 +3 ;
}
```

## O(N) : 값이 커질 때마다 연산의 크기가 같은 크기로 커질 경우
## 위에 풀었던 백준문제의 크기가 O(N)입니다!

## O(NlogN) 
## O(N^2)
## O(2^N)
## O(N!)
 
## 남은 시간 복잡도 문제들은 나중에 백준 문제를 풀이하면서 다루겠습니다!.
## 위에서 아래로 복잡도가 커지며 가능한 복잡도가 낮은 코딩을 하셔야합니다!.
 
## 그러면 모두 시간복잡도를 낮춰 효율적인 프로그래밍을 하시길 바랍니다
## 끗.!