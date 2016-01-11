---
layout: post
title:  "자바스크립트 객체생성"
author: echo
date:   2016-01-11 19:32:09 +0900
categories: javascript
---

2년전에 쓴 글이라서 ECMA 5.1 Edition 기준으로 작성되어있습니다.
현재 자바스크립트에서는 클래스 기반 객체 생성도 허용합니다.


Class를 기반으로 상속을 구현하는 다른 언어와 달리 JavaScript는 Prototype을 기반으로 상속을 구현합니다.
즉, Class를 생성해서 상속받는 것은 원론적으로 불가능합니다.
자바 언어에서 클래스를 생성하는 예제를 보겠습니다.
 
{% highlight script %}
// Java
// User Class를 생성합니다.
public class User {
    private String name;
    private int age;
    public String getName() {
        return name;
    }
    public void setName(string name) {
        this.name = name;
    }
}
 
// User 클래스를 상속받는 YunaKim 인스턴스를 생성하였습니다.
User YunaKim = new User();
YunaKim.setName("김연아");
 
{% endhighlight %}

