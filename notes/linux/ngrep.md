---
tags: [linux]
title: ngrep
created: '2020-10-12T19:26:12.823Z'
modified: '2021-01-15T18:08:09.981Z'
---

# ngrep

```bash
ngrep -d eth0 port 80
```

Просмотр трафика на с интерфейса eth0 на порту 80.

```bash
ngrep port 9000 -d any -W byline "192.168.3.45"
```

Просмотр трафика на порту 9000 (`port 9000`) с любого интерфейса (`-d any`) в человеко-читаемом виде (`-W byline`), содержащий строку "192.168.3.45".

```bash
ngrep -x -d any "192.168.3.45" port 9000
```

Просмотр трафика в hex-формате (`-x`)

Sources:
* https://wall-skills.com/2016/ngrep-cheat-sheet-with-examples/
* http://ngrep.sourceforge.net/usage.html
* https://medium.com/@bromiley/full-packet-friday-ngrep-4167a5f7f5f8

