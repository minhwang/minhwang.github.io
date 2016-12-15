---
layout: post
title:  "Welcome to Jekyll!"
categories: testing android
---
이 포스트는 안드로이드에서 제공하는 ActivityMonitor 클래스를 이해하기 위해 작성하였다.
https://developer.android.com/reference/android/app/Instrumentation.ActivityMonitor.html

* 클래스 역할과 가장 단순한 예제
* 1
* 2

이 클래스의 역할은 이름에서 쉽게 유추해 볼 수 있을 것 같다. 이 클래스의 인스턴스를 등록(addMonitor()를 이용한다.)하면 모니터링을 시작한다. 
모니터링의 대상은 액티비티와 IntentFilter와 매칭되는 인텐트이다.

