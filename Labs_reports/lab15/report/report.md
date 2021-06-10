---
# Front matter
lang: ru-RU
title: "Лабораторная работа №15"
subtitle: "Именованные каналы."
author: "Сергей Михайлович Роман"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Приобретение практических навыков работы с именованными каналами.

# Задание

- Изучите приведённые в тексте программы server.c и client.c. Взяв данные примеры за образец, напишите аналогичные программы, внеся следующие изменения:
- 1. Работает не 1 клиент, а несколько (например, два).
- 2. Клиенты передают текущее время с некоторой периодичностью (например, раз в пять секунд). Используйте функцию sleep() для приостановки работы клиента.
- 3. Сервер работает не бесконечно, а прекращает работу через некоторое время (например, 30 сек). Используйте функцию clock() для определения времени работы сервера. Что будет в случае, если сервер завершит работу, не закрыв канал?

# Выполнение лабораторной работы

1.  Я изучил и написал приведённые в тексте программы server.c и client.c.(рис. - @fig:001):

![Программы из примера](image/1.jpg){ #fig:001 width=100% }

2. Пишу программы с изменениями. Работают 2 клиента.(client.c уже написан с изменениями, а client_2.c написан без изменений и передаёт сообщение серверу).(рис. - @fig:002):

![Программы с изменениями](image/2.jpg){ #fig:002 width=100% }

 - Работа сервер-клиент-сервер:(рис. - @fig:003):

![Сервер-клиент-сервер](image/3.jpg){ #fig:003 width=100% }

 - Переписал программу, где клиент работает с некоторой периодичностью, с использование функции sleep(), а сервер прекращает работу через некоторое время. Также клиент передаёт серверу время работы.(рис. - @fig:004):
 
![с функцией sleep()](image/4.jpg){ #fig:004 width=100% }

  На последнем скриншоте видно, что клиент передаёт информацию серверу несколько раз, спустя некоторое время.(рис. - @fig:005):

![Работа](image/5.jpg){ #fig:005 width=100% } 

# Выводы

Сегодня я приобрёл практические навыки работы с именованными каналами. 
