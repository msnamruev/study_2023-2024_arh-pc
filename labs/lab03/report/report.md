---
## Front matter
title: "Отчет по выполнению лабораторной работы №3"
subtitle: "Дисциплина: архитектура компьютеров"
author: "Намруев Максим Саналович"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью работы является освоение процедуры оформления отчетов с помощью легковесного
языка разметки Markdown.

# Задание

1.Заполнение отчета по выполнению лабораторной работы с помощью языка разметки Markdown.
2.Задание для самостоятельной работы.

# Теоретическое введение

Markdown — язык текстовой разметки, созданный писателем и блогером Джоном Грубером. Он предназначен для создания красиво оформленных текстов в обычных файлах формата TXT. Вам не нужны громоздкие процессоры вроде Word или Pages, чтобы создавать документы с жирным или курсивным начертанием, цитатами, ссылками и даже таблицами. Достаточно запомнить простые правила Markdown, и можно писать хоть в «Блокноте». Хотя специализированные Markdown-редакторы, конечно, намного удобнее.



# Выполнение лабораторной работы

Открываю терминал. Перехожу в каталог курса и обновляю локальный репозиторий с помощью команды git pull.(рис. [-@fig:fig1]).

![Обновление репозитория ]( /afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/обновление.png){#fig:fig1 width=70%}

Перехожу в каталог с шаблоном отчета по лабораторной работе №3 и провожу компиляцию шаблона с использованием Makeifile с помощью команды make.Также проверил наличие и корректность полученных файлов.(рис. [-@fig:fig2]).

![Компиляция шаблона]( /afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/компиляция.png){#fig:fig2 width=70%}

Далее удаляю полученные файлы с использованием Makefile и проверяю то, что файлы действительно удалились.(рис. [-@fig:fig3])

![Удаление файлов](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/удаление.png){#fig:fig3 width=70%}

Открываю файл report.md и начинаю работу над заполнением отчета.(рис. [-@fig:fig4])

![Начало работы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/начало.png){#fig:fig4 width=70%}

Компилирую отчет и загружаю на Github.
#Выполнение заданий для самостоятельной работы
 
1. В соответствующем каталоге сделайте отчёт по лабораторной работе № 2 в формате
Markdown. В качестве отчёта необходимо предоставить отчёты в 3 форматах: pdf, docx
и md.

Перехожу в каталог с лабораторной работой номер 2

![Переход в директорию](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/переход.png){#fig:fig4 width=70%}

Далее начинаю работу над заполнением отчета по лабораторной работе №2 в markdown.

2. Загрузите файлы на github.

Загружаю файлы на Gitub с помощью команд git add . git commit -m и git push
# Выводы

После выполнения данной работы я научился пользоваться языком разметки Markdown.

# Список литературы{.unnumbered}

(https://esystem.rudn.ru/course/view.php?id=112)

