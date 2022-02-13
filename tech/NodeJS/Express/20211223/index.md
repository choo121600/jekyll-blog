---
layout: post
type: tech
date: 2021-12-30 12:56
category: WEB
title: Express (작성중)
tech-header: true
hash-tag: [Express, JavaScript, WEB, Backend]
---


익스프레스는 웹사이트에서 '단일, 다중 페이지, 하이브리드 웹 애플리케이션을 만드는데 필요한 견고한 기능 집합을 제공하는, 최소화되고 유연한 노드 웹 애플리케이션 프레임워크라고 설명한다.

노드의 핵심 철학은 이벤트 기반 프로그래밍이다. 이벤트 기반 프로그래밍에서는 프로그래머가 어떤 이벤트를 사용할 수 있는지, 거기에 어떻게 응답해야 하는지 이해해야 한다.

### Node.js
#### HelloWorld 코드를 작성해보자.

```javascript
const http = require('http');

http.createServer(function (req, res) {
    res = res.writeHead(200, {'Content-Type': 'text/plain'});
    res.end('Hello World\n');
}).listen(3000);

console.log('Server running on localhost:3000; press Ctrl-C to terminate..');
```

#### 라우팅
라우팅이란 요청받은 콘텐츠를 클라이언트에 보내는 메커니즘이다. 웹 기반 클라이언트/서버 애플리케이션에서는 클라이언트가 원하는 콘텐츠를 URL에 표시, 즉 경로와 쿼리스트링에 표시한다.

### Express

#### HelloWorld 코드를 작성해보자.

```javascript
const express = require("express")
const app = express()

app.set('port', process.env.PORT || 3000)

app.get('/'. (req, res) {
    res.send("helloWorld");
})

app.listen(app.get('port'), function() {
    console.log(
        'Express started on http://localhost:' + 
        app.get('port') + '; press Ctrl-C to terminate.');
});

```

#### 뷰와 레이아웃

뷰는 사용자에게 전송되는 것을 말한다.
뷰는 정적일 필요가 없으므로 이미지나 CSS 같은 정적자원과는 다르다.


### QA
#### 페이지 테스트
페이지 테스트라는 이름이 암시하듯이 페이지의 표현과 프론트엔드 기능을 테스트 합니다.
단위 테스트와 통합 테스트 모두 쓸 수 있다. 페이지 테스트에는 Mocha를 사용한다.

#### 교차 페이지 테스트
교차 페이지 테스트는 한 페이지에서 다른 페이지로 이동하는 기능을 테스트 한다.
교차 페이지 테스트에는 Zombie.js를 사용한다.

#### 논리 테스트
논리 테스트는 논리 영역을 대상으로 단위 테스트와 통합테스트를 실행합니다.
표현 기능을 제외한 오직 자바스크립트만을 테스트한다.
#### Lint
Lint는 에러를 찾는 게 아니라 잠재적 에러를 찾는다.
Lint에는 JSHint를 사용한다.