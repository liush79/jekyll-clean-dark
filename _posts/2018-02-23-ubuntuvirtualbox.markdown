---
layout: post
title: "[ubuntu] virtualbox"
date: "2018-02-23 23:49:51 +0900"
---

## Clip board problem
* virtualbox를 쓰다보면 클립보드가 공유잘 되다가 갑자기 안되는경우가 생기는데 재부팅을 하면 해결되긴하지만 현재 하던 작업들 다시 원복하려면 귀찮기 마련이다.
* 이때는 아래처럼 하면 해결됨.
  * Host (window) - VM (ubuntu) case
  ```bash
    $ ps -aux | grep VBox (check pid)
    $ kill -9 pid
    $ /usr/bin/VBoxClient --clipboard
  ```
  * Host (ubuntu) - VM (window) case
  ```bash
    Open Task manager
    Terminate VBoxTray.exe on Process TAB
    Run windows/system32/VBoxTray.exe
  ```
