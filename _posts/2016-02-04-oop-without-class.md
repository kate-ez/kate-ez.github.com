---
layout: post
title:  "Class 없이 OOP 하기"
description: "이 글은 번역을 하면서 느낀 어려운 점들을 정리하는 문서이기도 하지만, 다른 사람들이 번역을 할 때 정리하면 좋은 것들과 기술 문서, 오픈 소스에 기여하는 첫 단계인 번역에 대해 이야기 하고자 한다."
author: ashal
date:   2016-02-04 13:54:09 +0900
categories: javascript
published: true
---

## 저자
[@ahastudio](http://j.mp/1ea27KW) - 우아한형제들에서 Ruby on Rails로 LINE WOW를 개발했고, 최근엔 Java와 Spring Boot로 배달의민족 신규시스템을 개발하고 있습니다.

## 시작하며
[한국 루비 커뮤니티 2015년 대림절 달력 첫 글](http://j.mp/1QPHpTf)을 JavaScript로 옮겨보겠습니다. 그냥 Copy&Paste해서 몇몇 부분만 고칠 거라 이상해도 양해 부탁드립니다.

OOP라고 하면 Class와 Instance 개념을 떠올리는 경우가 많습니다. 객체끼리 서로 협력한다는 기본 원리만 가지고도 프로그래밍이 가능하다면 어떻게 될까요? Class가 없는 언어 중 하나인 JavaScript(ES6 이전 기준)를 통해 Class 없는 OOP를 경험해 봅시다.

## 준비물
- Node.js
- 흥미
- 용기
- 사랑과 우정 (필수는 아님)

## 객체 만들기
간단한 객체를 만들어 봅시다. 일단 Node 인터프리터 환경을 실행하죠.

```
$ node
```

객체가 뭘까요? 객체를 설명하는 방법은 너무나도 많은데, 추상화 단계를 너무 높이지 않고 손에 만져지는 걸로 살펴봅시다. “한 소년이 있었습니다” 정도면 어떨까요?

```javascript
var boy = new Object();
```

소년이 하나 만들어졌습니다. 제대로 잘 됐는지 한번 확인해 보죠.

```javascript
console.log(boy);
```

결과:
```
{}
```

우리가 잘 아는 게 나왔죠? 그냥 빈 객체를 만들 땐 힘들게 `new Object` 하지 말고, 그냥 `{}` 쓰시면 됩니다.

## 객체에 특성 부여하기
소년을 소년이라고 부르니 뭔가 밋밋한 것 같네요. 소년에게 이름을 붙여주면 어떨까요? 무난하게 “강동원”이라고 합시다. 객체에 이름을 넣어주면 간단히 해결됩니다.

```javascript
boy.name = 'Kang Dong-won';
```

자, 이제 소년의 이름을 한번 확인해 볼까요?

```javascript
console.log(boy.name);
```

결과:
```
Kang Dong-won
```

## 또 다른 객체 만들기
소년은 혼자 있으니 슬펐습니다. 그러니 여자친구를 하나 만들어보죠.

```javascript
var girl = Object.create(boy);
```

강동원을 프로토타입으로 소녀 객체가 만들어졌습니다. 강동원을 프로토타입으로 삼고 있기 때문에 한가지 문제가 있습니다. 소녀가 강동원가 똑같이 행동한다는 거죠.

```javascript
console.log(girl.name);
```

결과:
```
Kang Dong-won
```

“그럴 땐 얘기를 나누자 거울 속의 나하고”가 아니라면 이 상황을 벗어나야겠죠? 여자친구에게 이름을 하나 지어줍시다.

```javascript
girl.name = 'Don Don';
```

이제 둘을 사랑스럽게 엮어줄 수 있겠네요.

```javascript
console.log([boy.name, girl.name].join(' ♥ '));
```

결과:
```
Kang Dong-won ♥ Don Don
```

## 액션!
Class 없이 객체를 만들고, 특성을 부여하고, 이걸 활용하는 게 얼마나 쉬운지 우리는 경험했습니다. 강동원에게 구마 의식을 수행하게 하는 것도 이제는 쉽겠죠?

```javascript
girl.bad = true;

// 소녀의 상태 확인
console.log(girl.bad);

// 강동원에게 구마 능력 부여
// ES6 arrow function 사용함. MDN 문서 참고: http://j.mp/1NQfCfS
boy.performExorcism = target => { target.bad = false };

// 구마
boy.performExorcism(girl);

// 소녀의 상태 다시 확인
console.log(girl.bad);
```

## 정리하며
객체지향의 핵심은 객체입니다. 타입을 명확히 하고 싶어서 클래스를 사용하는 거죠. 이 둘을 명확히 구분해서 쓸 때, 유연함과 견고함의 균형을 맞출 수 있지 않을까요? [TypeScript](http://j.mp/VHCBT8)도 한번 써보세요!

**EOT**