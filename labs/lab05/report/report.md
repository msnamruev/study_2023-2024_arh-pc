---
## Front matter
title: "Отчет по лабораторной работе №5"
subtitle: "Дисциплина: архитектура компьютера"
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

Приобретение практических навыков работы в Midnight Commander. Освоение инструкций
языка ассемблера mov и int.

# Задание

1. Основы работы с Midnight Commander
2. Структура программы на языка ассемблера NASM
3. Подключение внешнего файла

# Теоретическое введение

Midnight Commander (или просто mc) — это программа, которая позволяет просматривать
структуру каталогов и выполнять основные операции по управлению файловой системой,
т.е. mc является файловым менеджером. Midnight Commander позволяет сделать работу с
файлами более удобной и наглядной.
Программа на языке ассемблера NASM, как правило, состоит из трёх секций: секция кода
программы (SECTION .text), секция инициированных (известных во время компиляции)
данных (SECTION .data) и секция неинициализированных данных (тех, под которые во
время компиляции только отводится память, а значение присваивается в ходе выполнения
программы) (SECTION .bss).

# Выполнение лабораторной работы

Открываю Midnight Commander с помощью команды mc. (рис. [-@fig:fig1]).

![Открытие Midnight Commander](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/1.png){#fig:fig1 width=70%}

Пользуясь клавишами вверх, вниз и enter перехожу в каталог ~/work/arch-pc, созданный при выполнении прошлой лабораторной работы.(рис. [-@fig:fig2]).

![Переход в каталог](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/2.png){#fig:fig2 width=70%}

С помощью функциональной клавиши f7 создаю папку lab05 и перехожу в созданный каталог.(рис. [-@fig:fig3]).

![Создание нового каталога](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/3.png){#fig:fig3 width=70%}

Пользуясь строкой ввода и командой touch создаю файл lab5-1.asm. (рис. [-@fig:fig4]).

![Создание файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/4.png){#fig:fig4 width=70%}

С помощью функционвльной клавиши F4 открываю файл lab05-1.asm для редактирования во встроенном редакторе.(рис. [-@fig:fig5]).

![Открытие редактора](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/5.png){#fig:fig5 width=70%}

Ввожу текст программы из листинга 5.1, сохраняю изменения и закрываю файл. (рис. [-@fig:fig6]).

![Ввод текста](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/6.png){#fig:fig6 width=70%}

С помощью функциональной клавиши F3 открываю файл lab5-1.asm для просмотра. Убеждаюсь что файл содержит текст программы.(рис. [-@fig:fig7]).

![Просмотр файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/7.png){#fig:fig7 width=70%}

Далее оттранслирую текст программы lab5-1.asm в объектный файл, выполняю компоновку объектного файла и запускаю получившийся исполняемый файл. Ввожу своё ФИО.(рис. [-@fig:fig8]).

![Запуск файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/8.png){#fig:fig8 width=70%}

## Подключение внешнего файла

Скачиваю файл in_out.asm со страницы курса в ТУИС.(рис. [-@fig:fig91]).

![Скачивание файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/91.png){#fig:fig91 width=70%}

В одной панели mc открываю каталок с файлом lab5-1.asm. В другом открываю каталог со скаченным файлом in_out.asm. Копирую файл in_out.asm в каталог с файлом lab5-1.asm с помощью функциональной клавиши F5. (рис. [-@fig:fig101]).

![Копирование файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/101.png){#fig:fig101 width=70%}

С помощью функциональной клавиши f6 создаю копию файла lab5-1.asm с именем lab5-2.asm.(рис. [-@fig:fig111]).

![Копирование файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/111.png){#fig:fig111 width=70%}

Исправляю текст программы в файле lab5-2.asm с использованием подпрограмм из внешнего файла in_out.asm. Далее создаю исполняемый файл и проверяю его работу.(рис. [-@fig:fig12]).(рис. [-@fig:fig13]).

![Исправление файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/12.png){#fig:fig12 width=70%}

![Создание исполняемого файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/13.png){#fig:fig13 width=70%}

После того как я изменил sprintLF на sprint и ещё раз создал исполняемый файл, вводимое сообщение перестало переноситься на следующую строку.(рис. [-@fig:fig14]).

![Запуск новой программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/14.png){#fig:fig14 width=70%}

#  Задание для самостоятельной работы

Создаю копию файла lab5-1.asm с помощью клавиши F5.(рис. [-@fig:fig15]).

![Создание копии](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/15.png){#fig:fig15 width=70%}

Далее редактирую файл labcopy.asm так, чтобы она выводила то, что вводит пользователь.(рис. [-@fig:fig16]).

![Редактирование программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/16.png){#fig:fig16 width=70%}

Создаю объектный и исполняемый файлы и запускаю полученную программу. Ввожу свою фамилию и программа выводит мне её обратно.(рис. [-@fig:fig17]).

![Проверка программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/17.png){#fig:fig17 width=70%}

После этого созадю другую компию файла lab5-2.asm и называю его labcopy2.asm.(рис. [-@fig:fig18]).

![Создание новой копии](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/18.png){#fig:fig18 width=70%}

Также редактирую файл чтобы он выводил строку, введённую пользователем.(рис. [-@fig:fig19]).

![Редактирование нового файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/19.png){#fig:fig19 width=70%}

После создаю объекстный и исполняемый файлы для labcopy2.asm и запускаю эту программу. Также ввожу свою фамилию и получаю её обратно.(рис. [-@fig:fig20]).

![Проверка работы программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/20.png){#fig:fig20 width=70%}


# Выводы

После выполнения данной лабораторной работы я научился навыкам работы в Midnight Commnader и основе инструкция ассемблера mov и int. 
