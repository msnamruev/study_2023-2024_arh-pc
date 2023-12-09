---
## Front matter
title: "Отчет по выполнению лабораторной работы №8"
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

Приобретение навыков написания программ с использованием подпрограмм. Знакомство
с методами отладки при помощи GDB и его основными возможностями

# Задание

1. Релизация подпрограмм в NASM

2. Отладка программ с помощью GDB

3. Добавление точек останова

4. Работа с данными программы в GDB

5. Обработка аргументов командной строки в GDB

6. Задание для самостоятельной работы.

# Выполнение лабораторной работы

## Реализация подпрограмм в NASM

Создаю каталог для выполнения лабораторной работы №9, перехожу в него и создаю файл lab09-1.asm. (рис. [-@fig:001]).

![Создание каталога и файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/1.png){#fig:001 width=70%}

Ввожу в файл lab09-1.asm текст программы из листинга 9.1.(рис. [-@fig:002])

![Ввод программы из листинга 9.1](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/2.png){#fig:002 width=70%}

Создаю исполняемый файл и проверяю его работу.(рис. [-@fig:003])

![Проверка работы программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/3.png){#fig:003 width=70%}

Изменяю текст программы, добавляя подпрограмму _subcalcul в подпрограммы _calcul.(рис. [-@fig:004])

![Изменение текста программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/4.png){#fig:004 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [-@fig:005])

![Запуск программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/5.png){#fig:005 width=70%}

Программа работает корректно.

##  Отладка программам с помощью GDB

Создаю файл lab09-2.asm с текстом программы из Листинга 9.2.(рис. [-@fig:006])

![Создание файла печати сообщения Hello world!](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/6.png){#fig:006 width=70%}

Получаю исполняемый файл.Для работы с GDB в исполняемый файл необходимо добавить отладочную информацию, для этого трансляцию программ необходимо проводить с ключом ‘-g’.Далее загружаю исполняемый файл в отладчик gdb и запускаю его с помощью команды run.(рис. [-@fig:007])

![Получение и загрузка в отлатчик исполняемого файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/7.png){#fig:007 width=70%}

Устанавливаю брейкпоинт на метку _start и запукаю программу.(рис. [-@fig:008])

![Установление брейкпоинта](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/8.png){#fig:008 width=70%}

Смотрю дисассимилированный код программы с помощью команды disassemble начинаю с метки _start .(рис. [-@fig:009])

![Просмотр дисассимилированного кода программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/9.png){#fig:009 width=70%}

Переключаюсь на отображение команд с Intel’овским синтаксисом, введя команду set
disassembly-flavor intel.(рис. [-@fig:010])

![Переключение на Intel'ский синтаксис](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/10.png){#fig:010 width=70%}

Отличия заключаются в том, что в режиме ATT используются "%" перед перед именами регистров и "$" перед именами операндов, а в режиме Intel используется обычный синтаксис.

Включаю режим псевдографики для более удобного анализа программы.(рис. [-@fig:011])

![Включение режима псевдографики](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/11.png){#fig:011 width=70%}

### Добавление точек останова

Проверяю точку останова по имени метки.(рис. [-@fig:012])

![Проверка точки останова](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/12.png){#fig:012 width=70%}

Определю адрес пердпоследней инструкции и устанавливаю точку останова. Далее смотрю информацию о всех установленных точках останова.(рис. [-@fig:013])

![Установка точки останова и её проверка](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/13.png){#fig:013 width=70%}

### Работа с данными программы в GDB

Выполняю 5 инструкций с помощью команды stepi и слежу за изменением регистров.(рис. [-@fig:017])  (рис. [-@fig:018])

![До использования комадны stepi](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/17.png){#fig:017 width=70%}

![После использования команды stepi](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/18.png){#fig:018 width=70%}

Изменились регистры eax,ebx,ecx,edx

Просматриваю значение переменной msg1 по имени.(рис. [-@fig:015])

![Просмотр значения переменной msg1](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/15.png){#fig:015 width=70%}

Также просматриваю значение переменной msg2.(рис. [-@fig:016])

![Просмотр значения переменной msg2](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/16.png){#fig:016 width=70%}

Изменяю первый символ переменной msg1.(рис. [-@fig:019])

![Изменение первого символа msg1](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/19.png){#fig:019 width=70%}

Изменяю первый символ переменной msg2.(рис. [-@fig:020])

![Изменение первого символа переменной msg2](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/20.png){#fig:020 width=70%}

Вывожу в различных форматах значение регистра ebx.(рис. [-@fig:021])

![Вывод значений регистра ebx](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/21.png){#fig:021 width=70%}

С помощью команды set изменяю значение регистра ebx.(рис. [-@fig:022])

![Изменение значения регистра ebx](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/22.png){#fig:022 width=70%}

Разница в том, что в первый раз мы вводим символ, который преобразуется в число, а во второй раз мы вводим само число.

### Обработка аргументов командной строки в GDB

Копирую файл lab8-2.asm, созданный при выполнении лабораторной работы No8,
с программой выводящей на экран аргументы командной строки (Листинг 8.2) в файл с
именем lab09-3.asm.(рис. [-@fig:024])

![Копирование файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/24.png){#fig:024 width=70%}

Создаю исполняемый файл.(рис. [-@fig:025])

![Создание исполняемого файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/25.png){#fig:025 width=70%}

Заргужаю исполняемый файл в отладчик, указав агрументы.(рис. [-@fig:026])

![Загрузка исполняемого файла в отладчик](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/26.png){#fig:026 width=70%}

Для начала устанавливаю точку останова перед первой инструкцией в программе и запускаю её.(рис. [-@fig:027])

![Установка точки остановы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/27.png){#fig:027 width=70%}

Просматриваю вершину стека, то есть число аргументов строки(включая имя программы).(рис. [-@fig:028])

![Просмотр вершины стека](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/28.png){#fig:028 width=70%}

Просматриваю остальные позиции стека.(рис. [-@fig:029])

![Просмотр остальных позиций стека](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/29.png){#fig:029 width=70%}

Шаг изменения адреа равен 4, потому что занчение регистра esp в стеке увеличивается на 4.

# Задание для самостоятельной работы.

1. Открываю программу из лабораторной работы №8 и начинаю её редактировать.(рис. [-@fig:020])

![Редактирование программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/30.png){#fig:030 width=70%}

Создаю исполняемый файл и запускаю его, чтобы проверить работу программы.(рис. [-@fig:031])

![Проверка работы программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/31.png){#fig:031 width=70%}

Программа работает верно.

Текст программы:

%include 'in_out.asm'  
SECTION .data  
msg db "Результат: ",0  
SECTION .text  
global _start  
_start:  
pop ecx   
pop edx   
sub ecx,1  
mov esi, 0  
mov edi, 30  
next1:  
cmp ecx,0  
jz _end   
pop eax   
call atoi   
call _f  
add esi,eax  
loop next1  
push edx  
_end:  
mov eax, msg  
call sprint  
mov eax, esi  
call iprintLF   
call quit  
_f:  
mul edi  
sub eax,11  
ret  

2. Создаю файл test3.asm и ввожу туда текст программы из листинга 9.3.(рис. [-@fig:032])

![Ввод программы из листинга 9.3](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/32.png){#fig:032 width=70%}

Содзаю исполняемый файл и запускаю его.(рис. [-@fig:033])

![Запуск программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/33.png){#fig:033 width=70%}

Убеждаюсь, что программа работает неверно.

Создаю исполняемый файл для работы с GDB и запускаю его через режим отладки. Создаю брейкпойнт и пошагово просматириваю программу.(рис. [-@fig:034])

![Просмотр программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/34.png){#fig:034 width=70%}
 
Замечаю, что после выполнения инструкции mul программы умножент 4 на 2 на не на 5, как должно быть.Из-за этого программа выдает неверный результат.

Далле открываю файл с программой и исправляю ошибку.(рис. [-@fig:035])

![Исправление ошибки](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/35.png){#fig:035 width=70%}

Создаю исполняемый файл и запускаю его.(рис. [-@fig:036])

![Просмотр программы](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/Снимки экрана/36.png){#fig:036 width=70%}

Теперь программа работает верно.

Текст программы:  
%include 'in_out.asm'  
SECTION .data  
div: DB 'Результат: ',0  
SECTION .text  
GLOBAL _start  
_start:  
; ---- Вычисление выражения (3+2)*4+5  
mov ebx,3  
mov eax,2  
add eax,ebx  
mov ecx,4  
mul ecx  
add eax,5  
mov edi,eax  
; ---- Вывод результата на экран  
mov eax,div  
call sprint  
mov eax,edi  
call iprintLF  
call quit  
 
# Выводы

После выполнения данной лабораторной работы я приобрел навыки написания программ с использование подпрограмм и познакомился с методами отладки при помощи GDB и его основными возможностями.

# Список литературы{.unnumbered}

::: {#refs}
:::
