---
# Front matter
lang: ru-RU
title: "Лабораторная работа №6"
subtitle: "Анализ файловой системы Linux. Команды для работы с файлами и каталогами"
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

Ознакомление с файловой системой Linux, её структурой, именами и содержанием каталогов. Приобретение практических навыков по применению команд для работы с файлами и каталогами, по управлению процессами (и работами), по проверке использования диска и обслуживанию файловой системы

# Задание

- 1.Выполните все примеры, приведённые в первой части описания лабораторной работы.
- 2.Выполните следующие действия, зафиксировав в отчёте по лабораторной работеиспользуемые при этом команды и результаты их выполнения:
	- 2.1.Скопируйте файл /usr/include/sys/io.h в домашний каталог и назовитеего equipment. Если файла io.h нет, то используйте любой другой файл в каталоге /usr/include/sys/ вместо него.
	- 2.2.В домашнем каталоге создайте директорию ~/ski.plases.
	- 2.3.Переместите файл equipment в каталог ~/ski.plases.
	- 2.4.Переименуйтефайл ~/ski.plases/equipment в ~/ski.plases/equiplist.
	- 2.5.Создайте в домашнем каталоге файлa bc1 и скопируйте его в каталог ~/ski.plases, назовите его equiplist2.
	- 2.6.Создайте каталог с именем equipment в каталоге ~/ski.plases.
	- 2.7.Переместите файлы ~/ski.plases/equiplistиequiplist2 в каталог ~/ski.plases/equipment.
	- 2.8.Создайте и переместите каталог~/newdirв каталог ~/ski.plases и назовите его plans.
- 3.Определите опции команды chmod, необходимые для того, чтобы присвоить перечисленным ниже файлам выделенные права доступа, считая, что в начале таких прав нет:
	- 3.1.drwxr--r--   ...   australia
	- 3.2.drwx--x--x   ...   play
	- 3.3.-r-xr--r--   ...   my_os
	- 3.4.-rw-rw-r--   ...   feathers При необходимости создайте нужные файлы.
- 4.Проделайте приведённые ниже упражнения, записывая в отчёт по лабораторной работе используемые при этом команды:	
	- 4.1.Просмотрите содержимое файла /etc/password.
	- 4.2.Скопируйте файл ~/feathers в файл ~/file.old.
	- 4.3.Переместите файл ~/file.old в каталог ~/play.
	- 4.4.Скопируйте каталог ~/play в каталог ~/fun.
	- 4.5.Переместите каталог ~/fun в каталог ~/play и назовите его games.
	- 4.6.Лишите владельца файла ~/feathers права на чтение.
	- 4.7.Что произойдёт, если вы попытаетесь просмотреть файл ~/feathers командой cat?
	- 4.8.Что произойдёт, если вы попытаетесь скопировать файл ~/feathers?
	- 4.9.Дайте владельцу файла ~/feathers право на чтение.
	- 4.10.Лишите владельца каталога ~/play права на выполнение.
	- 4.11.Перейдите в каталог ~/play. Что произошло?
	- 4.12.Дайте владельцу каталога ~/play право на выполнение.
- 5.Прочитайте man по командам mount, fsck ,mkfs ,kill и кратко их охарактеризуйте, приведя примеры.


# Выполнение лабораторной работы

1. Выполняю примеры, описанные в лабораторной работе(рис. - @fig:001):

![Создаю текстовый файл](1.jpg){ #fig:001 width=100% }

	- 1.1. Просматриваю его содержимое (рис. - @fig:001):

	![Содержимое файла](2.jpg){ #fig:002 width=100% }

	- 1.2. Изменяю немного файл и просматриваю его другими способами(рис. - @fig:003):

	![Содержимое через head и tail](3.jpg){ #fig:003 width=100% }

	- 1.3. Начинаю выполнение второго примера. Создаю файл abc1, после чего копирую его в april и may. Потом создаю каталог monthly и копирую в него предыдущие файлы. Потом коппирую monthly/may в monthly/june(рис. - @fig:004):

	![Пример 2](4.jpg){ #fig:004 width=100% }
	
	- 1.4 Пример 3. Cкопировал каталог monthly в каталог monthly.00, потом скопировал  каталог monthly.00 в каталог /tmp(рис. - @fig:005):
	
	![Пример 3](5.jpg){ #fig:005 width=100% }
	
	- 1.5 Пример 4. Изменил название файла april на july в домашнем каталоге, после чего, переместил файл july в каталог monthly.00(рис. - @fig:006):
	
	![Пример 4](6.jpg){ #fig:006 width=80% }
	
	- 1.6 Пример 5. Переименовал каталог monthly.00 в monthly.01, переместил каталог monthly.01 в каталог reports и переименовал каталог reports/monthly.01 в reports/monthly(рис. - @fig:007):
	
	
	![Пример 5](7.jpg){ #fig:007 width=100% }
	
	- 1.7 Пример 6. Создаю файл ~/may с правом выполнения для владельца, затем лишаю владельца файла ~/may права на выполнение; Cозда. каталог monthly с запретом на чтение для членов группы и всех остальных пользователей; Cоздаю файл ~/abc1 с правом записи для членов группы(рис. - @fig:011):
	
	![Пример 6](11.jpg){ #fig:011 width=100% }
	
- 2. Начинаю выполнять второе задание.Копирую файл /usr/include/sys/io.h в домашний каталог и называю его equipment(рис. - @fig:008):

	![Задание 2. ч.1](8.jpg){ #fig:008 width=100% }
	
В домашнем каталоге создаю директорию ~/ski.plases, затем перемещаю туда файл equipment, после чего переименовываю его в equiplist(рис. - @fig:009):

![Задание 2. ч.2](9.jpg){ #fig:009 width=100% }	

Создайю в домашнем каталоге файл abc1 и копирую его в каталог ~/ski.plases, с именем equiplist2. Создаю каталог с именем equipment в каталоге ~/ski.plases. Перемещаю файлы ~/ski.plases/equiplist и equiplist2 в каталог ~/ski.plases/equipment, потом создаю и перемещаю каталог ~/newdir в каталог ~/ski.plases и называю его plans(рис. - @fig:010):

![Задание 2. ч.3](10.jpg){ #fig:010 width=100% }

- 3. Приступаю к выполнению задания 3. Если я правильно понял задание, то изначально у этих файлов нет никаких прав.
	
	- 3.1 u+r; u+w; u+x; g+r; o+r;
	- 3.2 u+r; u+w; u+x; g+x; o+x;
	- 3.3 u+r; u+x; g+r; o+r;
	- 3.4 u+r; u+w; g+r; g+w; o+r.
	
- 4. Выполняю задание 4.
	
	- 4.1 Такого файла не нашёл. Был файл passwd. 
	- 4.2 Нет файла feathers.
	- 4.3 Нет файла file.old (может я не там ищу?) (рис. - @fig:012)
	
	![Нет файлов](12.jpg){ #fig:012 width=100% }
	
- 5.Выполняю 5-ое задание. 
 mount - используется для привязки файлов к конкретным хранилищам. Например, есть 4 SSD, которые стоят в одной машине, для удобства с помощью команды маунт можно привзять какой-либо файл на какой-то конкретный из этих хранилищ(рис. - @fig:013).
 
![Mount](13.jpg){ #fig:013 width=80% }

 fsck - как я понял, это своего рода дэбаггер. Это программа которая будет проверять и в случае чего "чинить" файловую систему компьютера. Также он может балансировать нагрузку между хранилищами для большей оптимизации(рис. - @fig:014).
 
![fsck](14.jpg){ #fig:014 width=80% } 

 mkfs - настройщик/строитель хранилища файловой системы. зачастую является частью жёсткого диска(рис. - @fig:015).
 
![mkfs](15.jpg){ #fig:015 width=80% } 

 kill - как можно догадаться из названия, команда принудительно останавливает какой-либо процесс(рис. - @fig:016).
 
![kill](16.jpg){ #fig:016 width=100% } 

# Выводы

Сегодня я приобрёл практический навык по применению команд дляработы с файлами и каталогами, по управлению процессами (и работами), по проверке использования диска и обслуживанию файловой системы.
