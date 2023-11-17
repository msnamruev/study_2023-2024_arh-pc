---
## Front matter
title: "Отчет по выполнению лабораторной работы №6"
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

Освоение арифметических инструкций языка ассемблера NASM.

# Задание

1. Символьные и численные данные в NASM
2. Выполнение арифметических операций в NASM

# Теоретическое введение

Большинство инструкций на языке ассемблера требуют обработки операндов. Адрес операнда предоставляет место, где хранятся данные, подлежащие обработке. Это могут быть данные хранящиеся в регистре или в ячейке памяти.

    Регистровая адресация – операнды хранятся в регистрах и в команде используются имена этих регистров, например: mov ax,bx.
    Непосредственная адресация – значение операнда задается непосредственно в команде, Например: mov ax,2.
    Адресация памяти – операнд задает адрес в памяти. В команде указывается символическое обозначение ячейки памяти, над содержимым которой требуется выполнить операцию.

Ввод информации с клавиатуры и вывод её на экран осуществляется в символьном виде. Кодирование этой информации производится согласно кодовой таблице символов ASCII. ASCII – сокращение от American Standard Code for Information Interchange (Американский стандартный код для обмена информацией). Согласно стандарту ASCII каждый символ кодируется одним байтом. Среди инструкций NASM нет такой, которая выводит числа (не в символьном виде). Поэтому, например, чтобы вывести число, надо предварительно преобразовать его цифры в ASCII-коды этих цифр и выводить на экран эти коды, а не само число. Если же выводить число на экран непосредственно, то экран воспримет его не как число, а как последовательность ASCII-символов – каждый байт числа будет воспринят как один ASCII-символ – и выведет на экран эти символы. Аналогичная ситуация происходит и при вводе данных с клавиатуры. Введенные данные будут представлять собой символы, что сделает невозможным получение корректного результата при выполнении над ними арифметических операций. Для решения этой проблемы необходимо проводить преобразование ASCII символов в числа и обратно

# Выполнение лабораторной работы

## Символьные и численные данные в NASM
Создаю каталог для программ лабораторной работы №6, перехожу в него и создаю файл lab6-1.asm (рис. [@fig:001]).

![Создание каталога](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/1.png){#fig:001 width=70%}

Ввожу в файл lab6-1.asm текст программы из листинга 6.1.(рис. [@fig:002]).
 
![Ввод программы из листинга 6.1](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/2.png){#fig:002 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [@fig:003]).

![Запуск файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/3.png){#fig:003 width=70%}

Изменяю текст программы и вместо символов записываю в регистры числа.(рис. [@fig:004]).

![Исправление программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/4.png){#fig:004 width=70%}

Далее создаю исполняемый файл и запускаю его.(рис. [@fig:005]).

![Запуск исправленной программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/5.png){#fig:005 width=70%}

Пользуясь таблицей ASCII можно определить,что код 10 соответствует символу переносу строки. Этот символ не отображается на экране.

Создаю новый файл lab6-2 в том же каталоге и ввожу в него текст программы из листинга 6.2.(рис. [@fig:006]).

![Создание нового файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/6.png){#fig:006 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [@fig:007]).

![Запуск новой программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/7.png){#fig:007 width=70%}

Аналогично предыдущему примеру изменяю символы на числа.(рис. [@fig:008]).

![Изменение программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/8.png){#fig:008 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [@fig:009]).

![Запуск исправленной программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/9.png){#fig:009 width=70%}

При исполнении программы было получено число 10.

Заменяю функцию iprintLF на iprint. Создаю исполняемый файл и запускаю его.(рис. [@fig:010]).(рис. [@fig:011]).

![Изменение файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/10.png){#fig:010 width=70%}

![Запуск программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/11.png){#fig:011 width=70%}

Вывод функции iprint отличается от iprintLF тем, что выведенное сообщение не переносится на слудующую строку.

## Выполнение фрифметических операций в NASM

Создаю файл lab6-3.asm в каталоге ~/work/arch-pc/lab06.(рис. [@fig:121]).

![Создание файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/121.png){#fig:121 width=70%}

После внимательного прочтения текста программы из листинга 6.3 ввожу его в lab6-3.asm.(рис. [@fig:012]).

![Ввод программы из листинга 6.3](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/12.png){#fig:012 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [@fig:013]).

![Запуск программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/13.png){#fig:013 width=70%}

Изменяю тест программы для вычисления выражения f(x)=(4*6+2)/5.(рис. [@fig:014]).

![Редактирование текста программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/14.png){#fig:014 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [@fig:015]).

![Запуск программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/15.png){#fig:015 width=70%}

Создаю файл variant.asm в каталоге ~/work/arch-pc/lab06.(рис. [@fig:161]).

![Создание файла variant.asm](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/161.png){#fig:161 width=70%}

Внимательно изучаю текст программы из листинга 6.4 и ввожу в файл variant.asm.(рис. [@fig:17]).

![Создание файла variant.asm](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/16.png){#fig:16 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [@fig:17]).

![Запуск файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/17.png){#fig:17 width=70%}

Ответы на вопросы

1. За вывод сообщение "Ваш вариант" отвечают строки:
mov eax,rem
call sprint

2. Эти строки используются чтобы считать x.

3. Call atoi преобразовывает код ASCII в целое число

4. За вычисление варианта отчечают строки:
xor edx,edx
mov ebx,20
div ebx
inc edx

5. Остаток от деление записывается в регистр edx.

6. Инструкция inc edx используется для того, чтобы увеличить значение регистра edx на 1.

7. Для вывода на экран результата выислений используются строки:
mov eax,edx
call iprintLF

#Задание для самостоятельной работы

Создаю файл lab6-4.asm в каталоге ~/work/arch-pc/lab06. Проверяю создание файла.(рис. [@fig:18]).

![Создание файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/18.png){#fig:18 width=70%}

Открываю созданную файл и начинаю печатать в него текст программы для вычисления (10*x-5)^2 (вариант 16)(рис. [@fig:19]).

![Ввод программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/19.png){#fig:19 width=70%}

Далее сохранию файл, создаю исполняемый файл и запускаю его. (рис. [@fig:20]).

![Проверка для значения x1](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/20.png){#fig:20 width=70%}

Запускаю программу ещё раз для проверки её работы при x2.(рис. [@fig:21]).

![Проверка для значения x2](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/21.png){#fig:21 width=70%}

Всё верно работает.
Сама программа:

%include 'in_out.asm'
SECTION .data
msg: DB 'Введите x: ',0
rem: DB 'Ответ: ',0
SECTION .bss
x: RESB 80
SECTION .text
GLOBAL _start
_start:
mov eax, msg
call sprintLF
mov ecx, x
mov edx, 80
call sread
mov eax,x ; 
call atoi ; 
mov ebx,10
mul ebx
add eax,-5
mul eax
mov edi, eax
mov eax,rem
call sprint
mov eax,edi
call iprintLF
call quit

# Выводы

После выполнения данной работы я освоил фрифметические инструкции языка ассемблера NASM

# Список литературы{.unnumbered}

::: {#refs}
:::
