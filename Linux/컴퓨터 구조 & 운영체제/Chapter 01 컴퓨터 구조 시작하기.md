# Chapter 01 컴퓨터 구조 시작하기

### 01-1 컴퓨터 구조를 알아야 하는 이유

###### 문제 해결

 컴퓨터 구조를 이해하고 있다면 문제 상황을 빠르게 진단할 수 있고, 문제 해결의 실마리를 다양하게 찾을 수 있다. 이런 사고가 가능 이들에게 컴퓨터란 '미지의 대상'이 아닌 '분석의 대상'이 될 것 이다.

###### 성능, 용량, 비용

 개발 프로그램이 어떤 환경에서 어떻게 작동하는지를 가장 잘 이해하고 있어야 하고, 프로그램을 위한 최적의 컴퓨터 환경을 스스로 판단할 수 있어야 한다. 이러한 문제는 프로그래밍 언어의 문법만 알아서는 해결하기 어렵다. 많은 프로그램은 필연적으로 성능, 용량, 비용이 고려된다. 컴퓨터 구조를 이해하면 입력과 출력에만 집중하는 개발을 넘어 성능, 용량, 비용까지 고려하며 개발하는 개발자가 될 수 있다.

### 01-2 컴퓨터 구조의 큰 그림

![1-1](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/1-1.jpg))

 데이터 : 컴퓨터가 이해하는 숫자, 문자, 이미지, 동영상과 같은 정적인 정보

 명령어 : 데이터를 움직이고 컴퓨터를 작동시키는 정보

 CPU(contral Processing Unit)

 주기억장치(main memory) : 메모리

 보조기억장치(secondary storage)

 입출력장치(input/output device)

![(Linux/컴퓨터 구조 & 운영체제/컴퓨터 구조 & 운영체제 image/1-2.jpg)](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/1-2.jpg)

###### 메모리

현재 실행되는 프로그램의 명령어와 데이터를 저장하는 부품이다.

메모리에는 저장된 값에 빠르고 효율적으로 접근하기 위해 주소라는 개념이 사용된다.

- 프로그램이 실행되기 위해서는 반드시 메모리에 저장되어 있어야 한다.
- 메모리는 현재 실행되는 프로그램의 명령어와 데이터를 저장한다.
- 메모리에 저장된 값의 위치는 주소로 알 수 있다,

###### CPU

메모리에 저장된 명령어를 읽어 들이고, 읽어 들인 명령어를 해석하고, 실행하는 부품

***메모리의 약점**

1. 가격이 비싸 저장 용량이 적다.
2. 전원이 꺼지면 저장된 내용을 잃는다.

**CPU 내부 구성 요소**중 가장 중요한 세 가지는 **산술논리연산장치(ALU), 레지스터, 제어장치** 이다.

**ALU** : 계산만을 위해 존재하는 부품으로, 컴퓨터 내부에서 수행되는 대부분의 계산을 맡아 수행한다.

**레지스터** : CPU 내부의 작은 임시 저장 장치로, 프로그램을 실행하는 데 필요한 값들을 임시로 저장한다. CPU 안에는 여러 개의 레지스터가 존재하고 각기 다른 이름과 역할을 가지고 있다.

**제어장치** : 제어 신호라는 전기 신호를 내보내고 명령어를 해석하는 장치이다.

- CPU가 메모리에 저장된 값을 읽고 싶을 땐 메모리를 향해 메모리 읽기라는 제어 신호를 보낸다.
- CPU가 메모리에 어떤 값을 저장하고 싶을 땐 메모리를 향해 메모리 쓰기라는 제어 신호를 보낸다.

###### 보조기억장치

메모리보다 크기가 크고 전원이 꺼져도 저장된 내용을 잃지 않는 메모리를 보조할 저장 장치

EX) 하드 디스크, SSD, USB 메모리, DVD, CD-ROM

###### 입출력장치

마이크, 스피커, 프린트, 마우스, 키보드처럼 컴퓨터 외부에 연결되어 컴퓨터 내부의 정보를 교환하는 장치를 의미

###### 메인보드와 시스템 버스

메인보드는 마더보드라고도 불리며, 메인보드에는 앞서 소개한 부품을 비롯한 여러 컴퓨터 부품을 부착할 수 있는 슬롯과 연결 단지가 있다. 메인보드에 연결된 부품들은 서로 정보를 주고받을 수 있는데, 이는 메인보드 내부에 **버스**라는 통로가 있기 때문이다. 컴퓨터 내부에는 다양한 종류의 통로, 즉 버스가 있다. 하지만 여러 버스 가운데 컴퓨터의 네 가지 핵심 부품을 연결하는 가장 중요한 버스는 **시스템 버스**이다.

시스템 버스

- 주소 버스 : 주소를 주고받는 통로
- 데이터 버스 : 명령어와 데이터를 주고받는 통로
- 제어 버스 : 제어 신호를 주고받는 통로
