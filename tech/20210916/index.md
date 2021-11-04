---
layout: post
type: tech
date: 2021-09-16 10:42
category: Algorithm
title: 백준 11723 집합 Python
tech-header: true
hash-tag: [BitMask, Algorithm]
---

<h3> 문제 </h3>
<hr>

<a href="https://www.acmicpc.net/problem/11723"><strong><i>BOJ 11723 집합</i></strong></a>

비어있는 공집합 S가 주어졌을 때, 아래 연산을 수행하는 프로그램을 작성하시오.


1. add x: S에 x를 추가한다. (1 ≤ x ≤ 20) S에 x가 이미 있는 경우에는 연산을 무시한다.
2. remove x: S에서 x를 제거한다. (1 ≤ x ≤ 20) S에 x가 없는 경우에는 연산을 무시한다.
3. check x: S에 x가 있으면 1을, 없으면 0을 출력한다. (1 ≤ x ≤ 20)
4. toggle x: S에 x가 있으면 x를 제거하고, 없으면 x를 추가한다. (1 ≤ x ≤ 20)
5. all: S를 {1, 2, ..., 20} 으로 바꾼다.
6. empty: S를 공집합으로 바꾼다. 


<br>
<h3>아이디어</h3>
<hr>
이 문제를 처음 풀었을 때, 메모리 초과가 떴다.<br>
30분 정도 고민을 해보다 지금 한 것이 내 지식 내에서는 최선이라는 생각이 들어 구글링을 해보니 이 문제는 비트마스크라는 테크닉을 사용해야하는 문제라는 것을 알게 되었다.

<h3>풀이</h3>
<hr>

<pre>
    <code id="sourcecode" class="python">
        import sys

        N = int(input())
        
        S = [0] * 21
        
        def add (x, S):
            S[x] = 1
            return S
        
        def remove(x, S):
            S[x] = 0
            return S
        
        def check(x, S):
            print(int(S[x]==1))
            return S
        
        def toggle(x, S):
            S[x]= 1-S[x]
            return S
        
        command_dic = {
            "add" : add,
            "remove": remove,
            "check": check,
            "toggle": toggle
        }
        
        for _ in range(N):
            command = sys.stdin.readline().strip().split()
            if len(command) > 1:
                S = command_dic[command[0]] (int(command[1]), S)
            else:
                if command[0] == "all":
                    S = [1]*21
                elif command[0] == "empty":
                    S = [0]*21
    </code>
</pre>