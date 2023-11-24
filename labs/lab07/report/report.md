---
## Front matter
title: "Отчет по выполнению лабораторной работы №7"
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

Изучение команд условного и безусловного переходов. Приобретение навыков написания
программ с использованием переходов. Знакомство с назначением и структурой файла
листинга

# Задание

1. Реализация переходов в NASM
2. Изучение структуры файлы листинга

# Теоретическое введение

Для реализации ветвлений в ассемблере используются так называемые команды передачи
управления или команды перехода. Можно выделить 2 типа переходов:
• условный переход – выполнение или не выполнение перехода в определенную точку
программы в зависимости от проверки условия.
• безусловный переход – выполнение передачи управления в определенную точку про-
граммы без каких-либо условий.
Листинг (в рамках понятийного аппарата NASM) — это один из выходных файлов, созда-
ваемых транслятором. Он имеет текстовый вид и нужен при отладке программы, так как
кроме строк самой программы он содержит дополнительную информацию.

# Выполнение лабораторной работы

##Реализация переходов в NASM

Открываю терминал и создаю каталог для программ лабораторной работы, перехожу в него и создаю файл lab7-1.asm (рис. [-@fig:001]).

![Создание файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/1.png){#fig:001 width=70%}

Ввожу в файл lsb7-1.asm текст программы из листинга 7.1.(рис. [-@fig:002])

![Ввод текста из листинга 7.1](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/2.png){#fig:002 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [-@fig:003])

![Запуск файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/3.png){#fig:003 width=70%} 

Изменяю текст программы в соответствии с листингом 7.2.(рис. [-@fig:004])

![Изменение файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/4.png){#fig:004 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [-@fig:005])

![Запуск измененного файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/5.png){#fig:005 width=70%}

Далее изменяю файл так, чтобы он выводил "Сообщения" в обратном порядке.(рис. [-@fig:006])

![Редактирование файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/6.png){#fig:006 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [-@fig:007])

![Запуск программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/7.png){#fig:007 width=70%}

Убеждаюсь, что всё работает верно.

Создаю файл lab7-2.asm в каталоге ~/work/arch-pc/lab07 и вставляю в него текст программы из листинга 7.3.(рис. [-@fig:008])

![Ввод текста из листинга 7.3](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/8.png){#fig:008 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [-@fig:009])

![Запуск программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/9.png){#fig:009 width=70%}

## Изуение структуры файла листинга

Создаю файл лситинга для программы из файла lab7-2.asm.(рис. [-@fig:010])

![Создание файла листинга](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/10.png){#fig:010 width=70%}

Далее открываю файл листинга lab7-2.lst с помощью текстового редактора gedit.(рис. [-@fig:011])

![Открывание файла листинга](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/11.png){#fig:011 width=70%}

Опишу строчку номер 16:

Здесь
"15"-это номер строчки в коде программы
"0000000D"- это адрес 
"5В"- это машинный код
"ret" - исходный кол программы

Опишу строчку номер 36:

Здесь
"35"-это номер строчки в коде программы
"00000027"- это адрес 
"CD80"- это машинный код
"int" - исходный кол программы

Опишу строчку номер 24:

Здесь
"23"-это номер строчки в коде программы
"0000000F"- это адрес 
"52"- это машинный код
"push" - исходный кол программы

Теперь открываю файл с программой lab7-2.asm и удаляю один операнд в случайном месте.(рис. [-@fig:012])

![Удаление операнда](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/12.png){#fig:012 width=70%}

Пытаюсь создать файл листинга, но он не создается из-за ошибки.(рис. [-@fig:013])

![Попытка создание файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/13.png){#fig:013 width=70%}

# Задание для самостоятельной работы

1. Создаю файл test.asm.(рис. [-@fig:014])

![Создание файла для самостотельной работы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/14.png){#fig:014 width=70%}

Далее открываю его и пишу программу для нахождения наименьшей из переменных a,b,c в соответствии с моим вариантом (вариант 16).(рис. [-@fig:015])

![Написание программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/15.png){#fig:015 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [-@fig:016])

![Проверка работы программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/16.png){#fig:016 width=70%}

Программа работает верно

Код программы:
%include 'in_out.asm'  
section .data  
msg2 db "Наименьшее число: ",0h  
A dd '44'  
B dd '74'  
C dd '17'  
section .bss  
min resb 10  
section .text  
global _start  
_start:  
mov ecx,[A]   
mov [min],ecx ;  
cmp ecx,[C] ;  
jg check_B  
mov ecx,[C] ;  
mov [min],ecx ; '  
check_B:  
mov eax,min  
call atoi ;   
mov [min],eax ;   
mov ecx,[min]  
cmp ecx,[B] ;   
jl fin ;   
mov ecx,[B] ;   
mov [min],ecx  
fin:  
mov eax, msg2  
call sprint ;   
mov eax,[min]  
call iprintLF ;  
call quit  

2. Создаю файл test2.asm.(рис. [-@fig:017])

![Создание файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/17.png){#fig:017 width=70%}

Начинаю написание программы, которая для введенных с клавиатуры значение x и a вычисляет значение заданной функции f(x) и выводит результат вычислений.(рис. [-@fig:018])

![Написание программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/18.png){#fig:018 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [-@fig:019])

![Проверка программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/19.png){#fig:019 width=70%}

Программы работает верно

Код программы:  
%include 'in_out.asm'  
section .data  
msg1 db 'Введите X: ',0h  
msg2 db 'Введите A: ',0h  
msg3 db "Результат: ",0h  
section .bss  
x resb 10  
a resb 10  
f resb 10  
section .text  
global _start  
_start:  

mov eax,msg1  
call sprint  
mov ecx,x  
mov edx,10  
call sread  
mov eax,msg2  
call sprint  
mov ecx,a  
mov edx,10  
call sread  
mov eax,x  
call atoi   
mov [x],eax  
mov eax,a  
call atoi   
mov [a],eax   
mov edi,[x]  
mov ecx,edi  
add ecx,4  
mov [f],ecx  
cmp edi,4  
jl fin ;  
mov ebx,[a]  
mov edi,[x]   
mul edi ;   
mov [f],eax ;   
fin:  
mov eax, msg3  
call sprint   
mov eax,[f]  
call iprintLF ;  
call quit   


# Выводы

После выполнения данной лабораторной работы я изучил команды условного и безусловного переходов, приобрел навыки написания программ с использованием переходов и познакомился с назнчением и структурой файла листинга.

# Список литературы{.unnumbered}

::: {#refs}
:::
