---
# Front matter
lang: ru-RU
title: "Лабораторная работа №7"
subtitle: "Поиск файлов. Перенаправлениеввода-вывода. Просмотр запущенных процессов"
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

Ознакомление с инструментами поиска файлов и фильтрации текстовых дан-ных. Приобретение практических навыков: по управлению процессами (и заданиями), по проверке использования диска и обслуживанию файловых систем.

# Задание

- 1.Осуществите вход в систему, используя соответствующее имя пользователя.
- 2.Запишите в файл file.txt названия файлов, содержащихся в каталоге /etc. Допишите в этот же файл названия файлов, содержащихся в вашем домашнем каталоге.
- 3.Выведите имена всех файлов из file.txt, имеющих расширение .conf, после чего запишите их в новый текстовой файл conf.txt. 
- 4.Определите, какие файлы в вашем домашнем каталоге имеют имена, начинавшиеся с символа c? Предложите несколько вариантов, как это сделать.
- 5.Выведите на экран (по странично) имена файлов из каталога /etc, начинающиеся с символа h.
- 6.Запустите в фоновом режиме процесс, который будет записывать в файл ~/logfile файлы, имена которых начинаются с log. 
- 7.Удалите файл ~/logfile.
- 8.Запустите из консоли в фоновом режимередактор gedit.
- 9.Определите идентификатор процесса gedit, используя команду ps, конвейер и фильтр grep. Можно ли определить этот идентификатор более простым способом?
- 10.Прочтите справку (man) команды kill, после чего используйте её для завершения процесса gedit.
- 11.Выполните команды df и du, предварительно получив более подробную информацию об этих командах, с помощью команды man.
- 12.Воспользовавшись справкой команды find, выведите имена всех директорий, имеющихся в вашем домашнем каталоге.


# Выполнение лабораторной работы

1. Вхожу в систему под своим именем пользователя, затем записываю в файл file.txt все каталги директории /etc и домашней папки. Полный список обрезан в целях экономии места(рис. - @fig:001):

![Каталоги в file.txt](1.jpg){ #fig:001 width=100% }

2. Вывожу имена всех файлов из file.txt, имеющих расширение .conf, после чего записываю их в новый текстовой файл conf.txt.Полный список обрезан в целях экономии места(рис. - @fig:002):

![Каталоги в conf.txt](2.jpg){ #fig:002 width=100% }

3. Определяю, какие файлы в домашнем каталоге имеют имена, начинавшиеся с символа c(рис. - @fig:003):

![Имена на с](3.jpg){ #fig:003 width=100% } 

4. Вывожу на экран (по странично) имена файлов из каталога /etc, начинающиеся с символа h(рис. - @fig:004):

![Имена на с](4.jpg){ #fig:004 width=100% } 

5. Запукаю в фоновом режиме процесс, который будет записывать в файл ~/logfile файлы, имена которых начинаются с log. После завершения процесса удаляю файл. Полный список обрезан в целях экономии места(рис. - @fig:005):

![Запуск фонового процесса, список имен на log](5.jpg){ #fig:005 width=100% } 

6. Запускаю в фоновом режимередактор gedit. Затем определяю идентификатор процесса gedit, используя команду ps, конвейер и фильтр grep. Узнать идентификатор процесса можно также с помошью команд pgrep gedit и  pidof gedit. После чего использую, предварительно прочитав о ней, команду kill для заврешения процесса(рис. - @fig:006):

![Запуск фонового процесса gedit](6.jpg){ #fig:006 width=100% } 

7. Выполняю команды df и du, предварительно получив более подробную информацию об этих командах, с помощью команды man. Полный список обрезан в целях экономии места(рис. - @fig:007):

![Запуск фонового процесса, список имен на log](7.jpg){ #fig:007 width=70% } 

8. Воспользовавшись справкой команды find, вывожу имена всех директорий, имеющихся в домашнем каталоге. Полный список обрезан в целях экономии места(рис. - @fig:008):

![Вывод имён всех директорий домашней папки](8.jpg){ #fig:008 width=70% }


# Выводы

Сегодня я ознакомился с инструментами поиска файлов и фильтрации текстовых данных, а также приобрёл практические навыки в управлению процессами. 
