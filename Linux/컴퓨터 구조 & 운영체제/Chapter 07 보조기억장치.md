# Chapter 07 보조기억장치

### 07-1 다양한 보조기억장치

**하드 디스크(자기 디스크)**

하드 디스크는 자기적인 방식으로 데이터를 저장하는 보조기억장치이다.

 ![6-1](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-1.jpg
)

하드 디스크는 동그란 원판에 데이터를 저장하고, 그것을 회전시켜 뾰족한 리더기로 데이터를 읽는다.

- **플래터** : 하드 디스크에서 실질적으로 데이터가 저장되는 곳으로 동그란 원판이다.

- **스핀들** : 플래터를 외전시키는 구성요소

- **RPM** : 스핀들이 플래터를 돌리는 속도의 분당 회전수를 나타내는 단위
- **헤드** : 플래터를 대상으로 데이터를 읽고 쓰는 구성 요소, 헤드는 원하는 위치로 헤드를 이동시키는 **디스크 암**이 부착되어 있다.

하드 디스크는 많은 양의 데이터를 저장해야 하므로 일반적으로 여러 겹의 플래터로 이루어져 있고 플래터 양면을 모두 사용할 수 있다. 양면 플래터를 사용하면 위아래로 플래터당 두개의 헤드가 사용된다.

***플래터에 데이터가 저장되는 방법***

![6-2](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-2.jpg)

플래터는 **트랙**과 **섹터**라는 단위로 데이터를 저장한다. 플래터를 여러 동심원으로 나누었을 때 그중 하나의 원을 **트랙**이라고 부르며, 트랙은 여러 조각으로 나누어지는데, 이 한 조각을 **섹터(하드 디스크의 가장 작은 단위)**라고 부른다.

**트랙** : 플래터를 여러 동심원으로 나누었을 때 그중 하나의 원

**섹터(하드 디스크의 가장 작은 단위)** : 트랙은 여러 조각으로 나누어지는데 그 조각중 한 조각을 말한다.

**실린더** : 여러 겹의 플래터 상에서 같은ㅇ 트랙의 위치한 곳을 모아 연결한 논리적 단위

연속된 정보는 보통 한 실린더에 기록된다.  그 이유는 디스크 암을 움직이지 않고도 바로 데이터에 접근할 수 있기 때문이다.

***하드 디스크가 저장된 데이터에 접근하는 시간***

- **탐색 시간** : 접근하려는 데이터가 저장된 트랙까지 헤드를 이동시키는 시간을 의미 

  ![6-3](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-3.jpg)

- **회전 지연** : 헤드가 있는 곳으로 플래터를 회전시키는 시간을 의미

![6-4](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-4.jpg)

- **전송 시간** : 하드 디스크와 컴퓨터 간에 데이터를 전송하는 시간을 의미

![6-5](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-5.jpg)

탐색 시간과 회전 지연을 단축시키기 위해서는 플래터를 빨리 돌려 RPM을 높이는 것도 중요하지만, 접근하려는 데이터가 플래터 혹은 헤드를 조금만 옮겨도 접근할 수 있는 곳에 위치해 있는 것도 중요하다.

**플래시 메모리**

플래시 메모리는 전기적으로 데이터를 읽고 쓸 수 있는 반도체 기반의 저장 장치이다. //EX) USB메모리, SD카드, SSD // 

**셀** : 플래시 메모리에서 데이터를 저장하는 가장 작은 단위, 이 셀이 모여 MB, GB, TB 용량을 갖는 저장 장치가 된다.

***플래시 메모리 종류***

- **SLC 타입** :  한 셀에 2비트를 저장할 수 있는 플래시 메모

  ![6-6](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-6.jpg)

  **특징**

1. 홀로 거주하는 집에 제약 없이 출입이 가능하듯 빠른 입출력이 가능하다.
2. 수명도 긴 편으로 수만에서 수십만번 가까이 데이터를 쓰고 지우고를 반복할 수 있다.
3.  용량 대비 가격이 높다.

- **MLC 타입** : 한 셀에 2비트를 저장할 수 있는 플래시 메모리

![6-7](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-7.jpg)

​	**특징**

1. SLC 타입보다 일반적으로 속도와 수명이 떨어진다.
2. 한 셀에 두 비트씩 저장할 수 있다는 점에서 SLC타입보다 대용화하기 유리하다.
3. SLC 타입보다 용량 대비 가격이 저렴하다.
4. 시중에서 사용되는 많은 플래시 메모리 저장 장치들이 MLC 타입으로 만들어진다.

- **TLC 타입** : 한 셀에 3비트를 저장할 수 있는 플래시 메모리

![6-8](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-8.jpg)

​	**특징**

1. MLC보다 대용화 하기 유리하다.
2. 일반적으로 다른 타입보다 수명과 속도가 떨어진다.
3. 용량 대비 가격이 저렴하다.

**정리**

|      구분      |  SLC   | MLC  |  TLC   |
| :------------: | :----: | :--: | :----: |
|    셀당 bit    |  1bit  | 2bit |  3bit  |
|      수명      |  길다  | 보통 |  짧다  |
| 읽기/쓰기 속도 | 빠르다 | 보통 | 느리다 |
| 용량 대비 가격 |  높다  | 보통 |  낮다  |

***셀보다 더 큰 단위***

![6-9](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-9.jpg)

- **페이지** : 셀들이 모여 만들어진 단위
- **블록** : 페이지가 모여 만들어진 단위, **삭제가 이루어지는 단위**
- **플레인** : 블록이 모여 만들어진 단위, **읽기와 쓰기가 이루어지는 단위**
- **다이** : 플레인이 모여 만들어진 단위

***페이지의 세 개의 상태***

- **Free 상태** : 어떠한 데이터도 저장하고 있지 않아 새로운 데이터를 저장할 수 있는 상태
- **Vaild 상태** : 이미 유요한 데이터를 저장하고 있는 상태
- **Invaild 상태** : 쓰레기값이라 부르는 유효하지 않은 데이터를 저장하고 있는 상태

플래시 메모리는 덮어쓰기가 불가능하여 Vaild 상태인 페이지에는 새 데이터를 저장할 수 없다.

***플래시 메모리의 간단한 동작의 예***

- 새로운 데이터 c 저장

![6-10](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-10.jpg)

- A를 A'로 수정

![6-11](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-11.jpg)

플래시 메모에서 덮어쓰기는 불가능 하기 떄문에 기존에 저장된 A는 Invaild 상태가 되어 더 이상 값이 유효하지 않은 쓰레기 값이 되고, 새로운 데이터 A' 데이터가 저장된다. 결과적으로 Vaild 페이지는 B, C, A'가 된다.

여기서 문제가 있다. A와 같이 쓰레기 값을 저장하고 있는 공간은 용량 낭비로 저장되어 있다. 그렇다고 A만 지울 수 없다. 그 이유는 플래시 메모리 삭제는 블록 단위로 수행되기 때문이다. 이런 쓰레기 값을 정리하기 위해 **가비지 컬렉션**기능을 제공한다.

**가비지 컬렉션**

![6-12](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-12.jpg)

​	**기능**

1. 유효한 페이지들만을 새로운 블록으로 복사한다.
2. 기존의 블록을 삭제한다.

### 07-2 RAID의 정의와 종류

**RAID의 정의**

주로 하드 디스크와 SSD를 사용하는 기술로, 데이터의 안전성 혹은 높은 성능을 위해 여러 개의 물리적 보조기억장치를 마치 하나의 논리적 보조기억장치처럼 사용하는 기술

**RAID의 종류**

RAID의 구성 방법을 **RAID 레벨**로 표현하는데, RAID 레벨에는 대표적으로 RAID0, RAID1, RAID2, RAID3, RAID4, RAID6이 있고, 그로부터 파생된 RAID10, RAID50 등이 있다.

- **RAID 0**

![6-13](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-13.jpg)

어떠한 데이터를 저장할 때 각 하드 디스크는 아래와 같이 번갈아 가며 데이터를 저장한다. 즉, 저장되는 데이터가 하드 디스크 개수만큼 나뉘어 저장된느 것이다. 이때 마치 줄무늬처럼 분산되어 저장된 데이터를 **스트라입**이라 하고, 분산되어 저장하는 것을 **스트라이핑**이라고 한다. 데이터가 분산되어 저장되면, 저장된 데이터를 읽고 쓰는 속도가 빨라진다.                                                                                             하나의 저장 장치를 이용했더라면 여러 번에 걸쳐 읽고 썼을 데이터를 동시에 읽고 쓸 수 있기 때문이다.

RAID 0 에 단점은 저장된 정보가 안전하지 않다. RAID 0으로 구성된 하드디스크 중 하나에 문제가 생긴다면 다른 모든 하드 디스크의 정보를 읽는 데 문제가 생길 수 있다.

- **RAID 1**

  ![6-14](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-14.jpg)

RAID 1은 복사본을 만드는 방식이다.  마치 거울처럼 완전한 복사본을 만드는 구성이기에 **미러링**이라고도 부른다.

RAID 1에 어떠한 데이터를 쓸 때는 원본과 복사본 두군데에 쓴다. 그렇기에 쓰는 속도는 RAID 0 보다 느리다. 또한 하드 디스크에 개수가 한정되었을 때 사용 가능한 용량이 적어지는 단점이 있다. 하지만 복구가 매우 간단하다는 장점이 있다. 똑같은 디스크가 두 개 있는 셈이니, 하나에 문제가 발생해도 잃어버린 정보를 금방 되찾을 수 있기 때문이다.

- **RAID 4**

![6-15](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-15.jpg)

RAID 4 는 RAID 1처럼 완전한 복사본을 만드는 대신 오류를 검출하고 복구하기 위한 정보를 저장한 장치를 두눈 구성 방식이다. 이때 '오류를 검출하고 복구하기 위한 정보'를 **패리티 비트**라고 한다. 이렇게 패리티를 저장한 장치를 이용해 다른 장치들의 오류를 검출하고, 오류가 있다면 복구한다.

- **RAID 5**

RAID 4에서는 어떤 데이터가 저장될 때마다 패리티를 저장하는 디스크에도 데이터를 쓰게 되므로 패리티를 저장하는 장치에 병목 현상이 발생한다는 문제가 있다.

![6-16](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-16.jpg)

RAID 5는 그림처럼 패리티 정보를 분산하여 저장하는 방식으로 RAID 4의 문제인 병목 현상을 해소한다.

- **RAID 6**

![6-17](https://github.com/JeongHwan0208/Computer-Instruction-operating-system/blob/main/Linux/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C/%EC%BB%B4%ED%93%A8%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%26%20%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%20image/6-17.jpg)

RAID 6의 구성은 기본적으로 RAID 5와 같으나, 서로 다른 두 개의 패리티를 두는 방식이다. 이는 오류를 검출하고 복구할 수 있는 수단이 두개가 생긴 샘으로 RAID 4나 RAID 5보다 안전한 구성이라 볼 수 있다. 다만 새로운 정보를 저장할 때마다 함께 저장할 패리티가 두 개 이므로, 쓰기 속도는 RAID 5보다 느리다. 따라서 데이터 저장 속도를 조금 희생하더라도 데이터를 더욱 안전하게 보관하고 싶을 때 사용하는 방식이다.
