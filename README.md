# HW.Suricata

# Мониторинг сетевых событий (Suricata)

В качестве результата пришлите ответы на вопросы в личном кабинете студента на сайте [netology.ru](https://netology.ru/).

## 

### Задание 1

Напишите правило для детектирования Xmas-сканирования.

*Дайте ответ в свободной форме.*

------

### Задание 2

Напишите правило для детектирования стороннего трафика, передающегося службой DNS.

*Дайте ответ в свободной форме.*

------

### Ответ на Задание 1. 
Напишите правило для детектирования Xmas-сканирования.

Ответ: 
alert tcp any any -> any any
(flags: FPU,12; msg: "Xmas scan detected"; sid: 1000001; rev: 1;)

------

### Ответ на Задание 2. 
Напишите правило для детектирования стороннего трафика, передающегося службой DNS.

Ответ:
alert udp any any -> any 53
(msg: "External DNS traffic detected"; content:"|00 00 FC|"; depth: 2; pcre:"/\x09(.)+\x03(.)+x00$/U"; sid:1000002; rev:1;)

------

