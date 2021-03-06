---
layout: single
title: "[C++]Ch.0 시작해봅시다"
---

## 내가 이 강의를 듣는 이유

개발 1년 8개월차... 이지만 기술용어? 기초코딩용어를 너무 몰라서
Java에서 C Language로 갈아타는 김에 새롭게 시작할겸 용어도 정리 할겸 적당한 강의를 찾다 걍 아무거나 지르고 보았다. 어차피 기초 강의니까


## 0.0 꼭 C/C++ 공부를 해야할까?

1. 가장 기본적인 언어이므로 배워야한다.
2. 올바른 타이핑 방법을 연습해라.
3. 간단한 개념을 이해해라.
4. 예제를 따라 해봐라 
5. 문제가 생기면 오류를 해결하려 노력해봐라
6. 예제를 보고 내 마음대로 바꾸어 봐라

1번은 솔직히 희망 개발직군에 따라 기본적인 언어는 바뀐다고 생각을 한다.
2~6번까지의 방식은 내가 좀 따라서 행동을 해보아야겠다 생각을 했다. 너무 이해를 안하려고 드는게 너무 큰 문제

## 0.1 프로그래밍 언어란?

### 기계어(Machine Language)
    전자회로 방식 - 전압의 차이(Low-High) 0,1로 구분하여 인식


### 어셈블리 언어(Assembly Language)
    CPU의 단위기능, 메모리의 직접 제어를 하기 위한 언어

### 고수준 언어(High-Level Language)
    C,C++,Java,Python 등 흔히 알고 있는 개발 언어들

### Low / High & Hard-ware / Soft-ware의 관계
    Hard-ware <------> Soft-ware
    Low-Level <------> High-Level

### 컴파일러(Compiler)
    내가 만든 코드를 기계어로 바꾸는 역할을 하는 도구
    실행파일을 만들어 주는 역할
    C/C++은 컴파일을 하게 될 경우 실행파일 생성
    생성파일을 CPU를 통하여 실행

### 인터프리터(Interpreter)
    컴파일과는 달리 실행파일을 만들지 않고 바로 CPU를 통하여 실행
    같은 코드를 반복적으로 실행하는 경우 시간이 오래 걸림

### 이식성(Portability)
    컴파일러 언어 - 운영체제마다 컴파일러가 달라 호황성을 따져가져 개발해야함.
    자바 - JVM을 사용하여 운영체제 간의 호환성이 좋은편


## 0.2 C/C++언어 소개
    C++ C에 객제치향 개념을 확장한 언어

### C/C++언어의 설계 철학
    1. 프로그래머를 믿어라.
    2. 실제세계에 쓸모가 있어야한다.
    3. 유용한 기능 추가하는것이 오용보다 중요하다.
    4. 프로그래머의 의도를 알수없다면 스스로 명시하게 한다.


## 0.3 프로그맹 과정 소개
1. 풀어야 할 문제를 정의한다. <br/>
2. 해법을 설계한다.<br/>
3. 해법을 구현하는 프로그램을 작성한다.<br/>

#### 과정
    1. 프로그램을 작성한다.
    2. 프로그램을 컴파일 한다.
    3. 오브젝트 파일들을 링킹한다.
    4. 테스트 해보면서 문제 발생시 수정한다.[debug]

#### 예시
    g++ -c file.cpp, file2.cpp
    => g++(컴파일러)를 이용하여 C컴파일 하여라.
    소스파일(.cpp) -> compile -> 오브젝트 파일(.o/.obj)
    소스코드에 따라 오브젝트 파일이 각각 생성이 된다.
    file.cpp -> file.obj
    file2.cpp -> file2.obj
    링커를 통하여 오브젝트 파일들을 합쳐 실행 파일로 만든다.
    file.obj + file2.obj = project.exe

#### 컴파일 방식 / 모드
    Build = compile에 linking을 합한 행위
    Debug mode - 디버깅 도구 포함 > 파일 용량이 커짐
    Release mode - 디버깅 도구 미포함  > 파일 용량이 작아짐 > 사용자에게 배포하기 위하여 디버깅 도구를 포함하지 않는다.
    처리속도가 Release가 더 빠르다.




## 0.4 솔루션,프로젝트 관리
난 맥북으로 테스트를 진행 할것이므로 일단 VSCode를 사용하여 골부를 진행 하다가 막히는 부분이 생길때마다 VSCode 빌드에 관해 검색을하거나 정 안되면 Clion을 구매하여 사용해볼 생각


## 0.5 코딩하다 막혔을 때는?
    당황하지 말고 분노하지 말자!
    그냥 검색하여 해결하면 그만이다.
    나의 친구는 누구? Google


# 이번강의 용어정리
    기계어
    어셈블리 언어
    고수준 언어
    컴파일러
    인터프리터
    이식성
    오브젝트 파일
    소스파일
    링커
    런타임서포트 - 이미 만들어진 코드를 사용하는 도구
    >> 오픈소스?같은 개념이라 생각하면 편할듯
    Debug
    Release
