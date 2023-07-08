# Chapter 03 명령어

### 03-1 소스 코드와 명령어

###### 고급 언어와 저급 언어

​	![2-1](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-1.jpg
)

- **고급 언어** : 컴퓨터가 이해하는 언어가아닌 사람이 이해하고 작성하기 쉽게 만들어진 언어
- **저급 언어** : 컴퓨터가 직접 이해하고 실행할 수 있는 언어
- **기계어** : 0과 1의 명령어 비트로 이루어진 언어
- **어셈블리어** : 0과 1로 표현된 명령어를 읽기 편한 형태로 변역한 언

![3](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-2.jpg)
###### 컴파일 언어와 프리티 언어

![2-3](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-3.jpg)

**컴파일 언어**

컴파일러에 의해 소스 코드 전체가 저급 언어로 변환되어 실행되는 고급 언어 EX) C언어

- 컴파일 : 컴파일 언어로 작성된 소스 코드 코드 전체가 저급언어로 변환되는 과정
- 컴파일러 : 컴파일을 수행해 주는 도구
- 목적 코드 : 컴파일러를 통해 저급언어로 변환된 코드

**인터프리터 언어**

**인터프리터** : 인터프리터 언어는 소스 코드를 한줄씩 한 줄씩 차례로 실행하며, 소스 코드를 한 줄씩 저급 언어로 변환하여 실행해주는                 도구/// 인터프리터에 의해 소스 코드가 한 줄씩 실행되는 고급 언어 EX) Python

###### 목적 파일 vs 실행 파일

**목적 파일** : 목적 코드로 이루어진 파일

**실행 파일** : 실행 코드로 이루어진 파일

 목적 코드가 실행 파일이 되기 위해서는 **링킹(기능들을 연결해준다.)**이라는 작업을 거쳐야 한다.

### 03-2 명령어의 구조

###### 연산 코드와 오퍼랜드

![2-4](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-4.jpg)

**연산코드** : 명령어가 수행할 연산 (연산자)

**오퍼랜드** : 흰색 배경의 필드 값, 즉 '연산에 사용할 데이터' 또는 '연산에 사용할 데이터가 저장된 위치' (피연산자)

**연산 코드 필드** : 빨간 박스 // **오퍼랜드 필드** : 검은색 박스 



***오퍼랜드***

 오퍼랜드 필드에는 숫자와 문자 등을 나타내는 데이터 또는 메모리나 레지스터 주소가 올 수 있다. 다만 오퍼랜드 필드에는 숫자나 문자와 같이 연산에 사용할 데이터를 직접 명시하기보다는, 많은 경우 연산에 사용할 데이터가 저장된 위치, 즉 메모리 주소나 레지스터 이름이 담깁니다. 그래서 오퍼랜드 필드를 **주소 필드**라고 부르기도 한다.

![2-5](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-5.jpg)

- **0-주소 명령어** : 오퍼랜드가 하나도 없는 명령어
- **1-주소 명령어** : 오퍼랜드가 하나인 명령어
- **2-주소 명령어** : 오퍼랜드가 두 개인 명령어
- **3-주소 명령어** : 오퍼랜드가 세 개인 명령어



***연산 코드***

**데이터 전송**

- MOVE : 데이터를 옮겨라
- STORE : 메모리에 저장하라
- LOAD(FETCH) : 메모리에서 CPU로 데이터를 가져와라
- PUSH : 스택에 데이터를 저장하라
- POP : 스택의 최상단 데이터를 가져와라

**산술/논리 연산**

- ADD / SUBTRACT / MULTIPLY / DIVIDE : 덧셈 / 뺄셈 / 곱셈 / 나눗셈을 수행한다.
- INCREMENT / DECREMENT : 오퍼랜드에 1을 더하라 / 오퍼랜드에 1을 빼라
- AND / OR / NOT: AND / OR / NOT 연산을 수행하라
- COMPARE : 두 개의 숫자 또는 TRUE /FALSE 값을 비교해라

**제어 흐름 변경**

- JUMP : 특정 주소로 실행 순서를 옮겨라
- CONDITIONAL JUMP : 조건에 부합할 때 특정 주소로 실행 순서를 옮겨라
- HALT : 프로그램의 실행을 멈춰라
- CALL : 되돌아올 주소를 저장한 채 특정 주소로 실행 순서를 옮겨라
- RETURN: CALL을 호출할 때 저장했던 주소로 돌아가라

**입출력 제어**

- READ(INPUT) : 특정 입출력 장치로부터 데이터를 읽어라
- WRITE(OUTPUT) : 특정 입출력 장치로 데이터를 써라
- START IO : 입출력 장치를 시작하라
- TEST IO : 입출력 장치의 상태를 확인하라



###### 주소 지정 방식

- **즉시 주소 지정 방식**

![2-6](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-6.jpg)

 연산에 사요할 데이터를 오퍼랜드 필드에 직접 명시하는 방식 

단점 : 데이터의 크기가 작아진다. 

장점 : 연산에 사용할 데이터를 메모리나 레지스터로부터 찾는 과정이 없기 때문에 이하 설명할 주소 지정 방식들보다 빠르다.

- **직접 주소 지정 방식**

![2-7](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-7.jpg)

 오퍼랜드 필드에 유효 주소를 직접적으로 명시하는 방법

오퍼랜드 필드에서 표현할 수 있는 데이터의 크기는 즉시 주소 지정 방식보다 더 커졌지만, 여전히 유효 주소를 표현할 수 있는 범위가 연산 코드의 비트 수만큼 줄었다.

- **간점 주소 지정 방식**

![2-8](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-8.jpg)

 유효 주소의 주소를 오퍼랜드 필드에 명시하는 방법

직접 주소 지정 방식보다 표현할 수 있는 유효 주소의 범위가 넓어졌다. 다만 두 번의 메모리 접근이 필요하기 때문에 앞서 설명한 주소 지정 방식들보다 일반적으로 느린 방법이다.

- **레지스터 주소 지정 방식**

![2-9](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-9.jpg)

 직접 주소 지정 방식과 비슷하게 연산에 사용할 데이터를 저장한 레지스털를 오퍼랜드에 직접 명시하는 방법

레지스터 주소 지정 방식은 직접 주소 지정 방식보다 빠르게 데이터에 접근할 수 있다. 다만, 레지스터 주소 지정 방식은 직접 주소 지정 방식과 비슷한 문제를 공유한다. 표현할 수 있는 레지스터 크기에 제한이 생길 수 있다는 점이다.

- **레지스터 간접 주소 지정 방식**

  ![2-10](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-10.jpg)

   연산에 사용할 데이터를 메모리에 저장하고, 그 주소를 저장한 레지스터를 오퍼랜드 필드에 명시하는 방법

  메모리에 접근하는 횟수가 한 번으로 줄어든다는 차이이자 장점이 있다. 

###### 스택과 큐

![2-11](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-11.jpg)

**스택** : 한쪽 끝이 막혀 있는 통과 같은 저장 공간이다. 한쪽 끝이 막혀 있어서 막혀 있지 않은 쪽으로 데이터를 차곡차곡 저장하고. 저장한 자료를 빼낼 때는 마지막으로 저장한 데이터부터 빼낸다. **스택은 '나중에 저장한 데이터를 가장 먼저 빼내는 데이터 관리 방식(후입선출)'으로 LIFO(last in first out)자료구조라고도 부른다.**

- PUSH : 스택에 새로운 데이터를 저장하는 명령어
- POP : 스택에 저장된 데이터를 꺼내는 명령어

![2-12](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/2-12.jpg)

**큐** : 양쪽이 뚫려 있는 통과 같은 저장공간이다. 한쪽으로는 데이터를 저장하고, 다른 한쪽으로는 먼저 저장한 순서대로 데이터를 빼낸다.

**큐는 '가장 먼저 저장된 데이터부터 빼내는 데이터 관리 방식(선입선출)'으로 FIFO(first in first out)자료구조로도 부른다.**
