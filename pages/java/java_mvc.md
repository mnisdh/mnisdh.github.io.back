---
title: MVC, MVP, MVVM 패턴
keywords: MVC, MVP, MVVM 패턴
last_updated:
tags:
summary: "MVC, MVP, MVVM 패턴 설명"
sidebar: mydoc_sidebar
permalink: java_mvc.html
folder: java
---

### MVC 패턴

하나의 어플리케이션을 크게 Model, View, Controller 의 세영역으로 구분하고 각 영역간의 코드 결합도를 최소화 시키는 개발 패턴중 하나이다

- Model : 데이터와 상태를 유지하며 데이터 처리 로직을 포함(데이터를 의미)
- View : Model을 표현해주는 역할을 하며 Controller와 통신을 함
- Controller : 사용자가 보기 위해 데이터를 가공, 혹은 조작 하는 것을 의미하며 Model 과 View를 컨트롤함(액티비티, 프래그먼트)

- Model과 View를 분리할수 있지만 Controller가 많이 엮여 있어 Model, View가 변경될때마다 Controller의 변경이 잦아지며 복잡해질 가능성이 큼


### MVP 패턴

MVC를 대체하기 위한 가장많이 사용되는 대안책중 한가지이며 Model, View, Presenter 의 세영역으로 구분

- Model : 데이터와 상태를 유지하며 데이터 처리 로직을 포함(데이터를 의미)
- View : MVC와 달리 액티비티, 프래그먼트가 View의 역할을 대신하며 액티비티가 뷰 인터페이스를 구현해 Presenter에게 넘겨줌
- Presenter : View에 연결해서 조작하는것이 아닌 인터페이스를 구현한 것이므로 모듈화나 유연성에 좋음

- MVC와 비슷하게 Presenter에 역할이 가중되어 복잡해지고 분리하는데에 어려움이 발생할수 있음


### MVVM 패턴

MVC를 대체하기 위한 가장많이 사용되는 대안책중 다른 한가지이며 Model, View, ViewModel 의 세영역으로 구분

- Model : 데이터와 상태를 유지하며 데이터 처리 로직을 포함(데이터를 의미)
- View : MVP와 같이 액티비티, 프래그먼트가 View의 역할을 하며 ViewModel을 통해 Model의 데이터를 요청
- ViewModel : Model을 래핑하여 View에서 요청한 것들을 처리해줌(Presenter의 역할을 함)

- View에서 ViewModel을 연결할때 DataBinding이 많이 사용되며 ViewModel도 역할이 가중되어 복잡해질 가능성이 큼


### 지금(2018.01) 내가 추구하는 방법

기존에 익숙한 MVC패턴에 부합되는 구조로 개발을 하려고 노력하며
공통 사용에 필요한 Custom View 구현시에는
DataBinding을 사용하여 Model과 View를 Control하는 코드들을 최소화해서 개발하는것을 추구하는중
하지만 언제 생각이 바뀔지 모름 1시간뒤에 바뀌어있을수도 후

[참고한 자료](https://academy.realm.io/kr/posts/eric-maxwell-mvc-mvp-and-mvvm-on-android/)