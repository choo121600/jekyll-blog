---
layout: post
type: tech
date: 2021-12-19 19:56
category: Backend
title: Nodejs vs Spring Boot
tech-header: true
hash-tag: [Backend]
---


Backend 부문의 서버 사이드 애플리케이션 플랫폼은 Node.js와 Spring Boot가 있다.

내가 진행하려는 프로젝트에 필요한 기능은 회원 관리, 주문 및 결제 정도가 있다.

그리고 현재 나는 1인 개발을 하려고 하고 있고 최대한 빠르게 개발을 해서 가설 검증을 하고자 한다.

Node.js
<ul class="post-ul">
    <li>하나의 스레드로 요청에 대한 작업을 수행하여 메모리를 아낄 수 있다.</li>
    <li>빈번한 I/O처리에 있어 우수한 성능을 가졌고 서버 확장의 용이성이 있다.</li>
    <li>JavaScript를 기반으로 하여 진입장벽이 비교적 낮다.</li>
    <li>비교적 가벼운 I/O가 발생하는 웹서버나 동영상, 스트리밍 같은 컨텐츠 딜리버리 서버다.</li>
    <li>오류 핸들링을 안 하면 프로그램이 꺼진다.</li>
</ul>

Spring Boot
<ul class="post-ul">
    <li>멀티 스레드라서 CPU 연산이 많은 요청을 처리할 수 있다. </li>
    <li>각 스레드는 맡은 요청이 마무리될 때까지 그 요청을 담당한다.</li>
    <li>Java를 기반으로 하여 진입장벽이 비교적 높다.</li>
    <li>길고 반복적인 I/O를 처리하는데 효율적이다.</li>
    <li>Java이기 때문에 Type Safe하고 커뮤니티가 잘되어 있다.</li>
</ul>

따라서 현재 나의 상황에선 Node.js를 사용하는 것이 더 합리적이라고 판단된다.