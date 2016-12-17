---
layout: post
title:  "ActivityMonitor 이해하기"
categories: testing android
---
처음 이 클래스를 사용한 것은 재생 중인 비디오를 탭했을 때, 전체화면으로 재생되는 앱을 대상으로 테스트 코드를 작성할 때 였다. 모니터링을 시작하고 대상 액티비티가 원하는 시점에 시작되는지를 확인하거나, 대상 액티비티 내의 특정 UI 요소들이 존재하는지를 확인하는 용도로 사용했었다. 그 때는 각 인자들에 대한 이해없이 여기저기서 찾아낸 예제를 가져다 사용하는 수준이었다.
최근에 이 클래스를 다시 사용할 필요에 의해 문서를 살펴보게 되었는데, 눈에 들어온 생성자 파라미터가 있었다.

# ActivityMonitor
이 클래스의 역할은 이름에서 어렵지 않게 유추할 수 있다. 그래도 원작자인 구글이 제공하는 개발자 문서에서 제공하는 [ActivityMonitor](https://developer.android.com/reference/android/app/Instrumentation.ActivityMonitor.html) 클래스의 설명을 빌려 이해해보자면,

Information about a particular kind of Intent that is being monitored. An instance of this class is added to the current instrumentation through addMonitor(Instrumentation.ActivityMonitor); after being added, when a new activity is being started the monitor will be checked and, if matching, its hit count updated and (optionally) the call stopped and a canned result returned.

An ActivityMonitor can also be used to look for the creation of an activity, through the waitForActivity() method. This will return after a matching activity has been created with that activity object.

문서에서는 모니터링의 대상이 되는 특정 유형의 인텐트에 대한 정보라고 소개하고 있다. 모니터링을 시작하면 대상 액티비티가 시작할 때 마다 Hit count를 갱신하고, 설정에 따라 액티비티의 이 후 동작을 수행하지 않고 미리 정의한 결과를 반환할 수 있다고 명시하고 있다. 물론, 대상 액티비티가 시작될 때까지 대기 할 수 있는 기능도 제공하고 있다.

# 문제
'(optionally) the call stopped and a canned result returned.' 처음에는 이 부분을 이해하기 쉽지 않았다. Stack Overflow에도 이해를 돕기 위한 질문을 올렸지만, 명쾌한 답을 얻지 못 했다.(영어를 이해하지 못한 것일 수도 있다.) 그리하여 요리조리 예제를 바꿔가며 확인해 본 결과, 생성자의 2, 3번째 파라미터와 연관이 있는 내용이었다는 것을 알 수 있었다.
이 클래스는 두 개의 생성자를 제공하는데, 첫번째 파라미터를 제외하고는 동일하다.

Instrumentation.ActivityMonitor (String cls, Instrumentation.ActivityResult result, boolean block)

A canned result to return if the monitor is hit; can be null.
Controls whether the monitor should block the activity start (returning its canned result) or let the call proceed.

# 가가



