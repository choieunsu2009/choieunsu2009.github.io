---
layout: post
title: "command-injection-chatgpt 풀이"
date: 2026-05-12 21:08:21 +0900
tags: []
---
https://dreamhack.io/wargame/challenges/768
문제를 풀어보겠습니다

## 문제 내용 분석
일단 문제 내용을 보면
![](/assets/img/posts/command-injection-chatgpt/01.png)
문제 설명과 함께 문제 파일을 다운로드 받을 수 있습니다.
Command Injection을 통해 플래그를 얻으라 하는데 Command Injection이 뭔지 모르니 서칭을 해봅시다

https://noirstar.tistory.com/267 의 내용을 보면 대충 SQLi 처럼 서버로 전송해서 실행되는 커멘드를 조작해서 정보를 취득하는 공격수법으로 보입니다.
일단 소스코드보다 먼저 사이트를 보면서 대충 감을 잡아봅시다.

## 문제 분석
드림핵 VM을 실행하고 접속하니 이 화면이 떴습니다.

![](/assets/img/posts/command-injection-chatgpt/02.png)
Ping을 들어가서 실제로 어떤 공격이 어떤 느낌으로 실행될지 감을 잡아보겠습니다.

![](/assets/img/posts/command-injection-chatgpt/03.png)
여기 input에 아까 분석한대로 Command Injection을 시도해야 하는듯 합니다.
이제 코드를 보겠습니다.

![](/assets/img/posts/command-injection-chatgpt/04.png)
예상대로 클라이언트 측에서 보낸 공격을 아무런 검증 없이 실행하고 있습니다
문제 정보에서 플래그는 flag.py에 있다고 하였으나 한 번 더 확인을 하기 위해 `127.0.0.1; ls`를 input에 입력하여 결과를 보겠습니다
 ![](/assets/img/posts/command-injection-chatgpt/05.png)
 이를 통해 flag.py의 위치를 알아냈습니다
 이제 `127.0.0.1; cat flag.py`를 input에 입력하여 결과를 보겠습니다
 ![](/assets/img/posts/command-injection-chatgpt/06.png)
이렇게 flag를 찾는데 성공했습니다.
