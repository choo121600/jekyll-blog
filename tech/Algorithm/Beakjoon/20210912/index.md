---
layout: post
type: tech
date: 2021-09-12 14:48
category: Algorithm
title: 백준 2667 단지번호붙이기 Python
tech-header: true
hash-tag: [Algorithm, DFS]
---

<h3> 문제 </h3>
<hr>

<a href="https://www.acmicpc.net/problem/2667"><strong><i>BOJ 2667 단지번호붙이기</i></strong></a>

<그림 1>과 같이 정사각형 모양의 지도가 있다. 1은 집이 있는 곳을, 0은 집이 없는 곳을 나타낸다. 철수는 이 지도를 가지고 연결된 집의 모임인 단지를 정의하고, 단지에 번호를 붙이려 한다. 

여기서 연결되었다는 것은 어떤 집이 좌우, 혹은 아래위로 다른 집이 있는 경우를 말한다. 대각선상에 집이 있는 경우는 연결된 것이 아니다. 

<그림 2>는 <그림 1>을 단지별로 번호를 붙인 것이다. 지도를 입력하여 단지수를 출력하고, 각 단지에 속하는 집의 수를 오름차순으로 정렬하여 출력하는 프로그램을 작성하시오.


<img src="img/problem.PNG" alt="boj 2667">

<h3> 풀이 </h3>
<hr>

<pre>
    <code id="sourcecode" class="python">
    import sys
    
    N = int(input())
    dx = [1, -1, 0, 0]
    dy = [0, 0, 1, -1]
    graph = [list(map(int, sys.stdin.readline().strip())) for _ in range(N)]
    con = 0
    
    def dfs (x, y):
        graph[x][y] = 0
        global con
    
        con += 1
        for i in range(4):
            nx = x + dx[i]
            ny = y + dy[i]
            if nx < 0 or nx >= N or ny < 0 or ny >= N:
            continue
            if graph[nx][ny] == 1:
            dfs(nx,ny)
    
    li = []
    for i in range(N):
        for j in range(N):
            if graph[i][j] == 1:
            con = 0
            dfs(i, j)
            li.append(con)
    
    print(len(li))
    li.sort()
    for i in li:
        print(i)
        
    </code>
</pre>