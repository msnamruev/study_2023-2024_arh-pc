---
## Front matter
title: "Отчет по выполнению лабораторной работы №2"
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

Целью работы является изучить идеологию и применение средств
контроля версий. Приобрести практические навыки по работе с системой
git.

# Задание

1. Настройка Github
2. Базовая настройка Git
3. Создание SSH ключа
4. Создание рабочего пространства и репозитория курса на основе
шаблона
5. Создание репозитория курса на основе шаблона
6. Настройка каталога курса

# Теоретическое введение

Системы контроля версий (Version Control System, VCS) применяются при работе
нескольких человек над одним проектом. Обычно основное дерево проекта хранится в
локальном или удалённом репозитории, к которому настроен доступ для участников про-
екта. При внесении изменений в содержание проекта система контроля версий позволяет
их фиксировать, совмещать изменения, произведённые разными участниками проекта,
производить откат к любой более ранней версии проекта, если это требуется.

# Выполнение лабораторной работы

1. Настройка github
Так как у меня уже была учётная запись на сайте GitHub, я пропускаю этот
пункт.(рис. [-@fig:001])


![Создание аккаунта](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/01.png){#fig:001 width=70%}

2. Базовая настройка git.
Сначала делаю предварительную конфигурацию git. Открываю терминал и
ввожу команды, указывая своё имя и email.(рис. [-@fig:002])

![Ввод имени и email](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/1.png){#fig:002 width=70%}

Настраиваю utf-8 в выводе сообщений git.(рис. [-@fig:003])

![настройка utf-8](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/2.png){#fig:003 width=70%}

Задаю имя master для начальной ветки.(рис. [-@fig:004])

![настройка autocrlf](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/3.png){#fig:004 width=70%}

А также параметр safecrlf со значением warn.(рис. [-@fig:005])

![настройка safecrlf](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/4.png){#fig:005 width=70%}

3. Создание SSH ключа

Для последующей идентификации пользователя на сервере репозиториев
необходимо сгенерировать пару ключей (приватный и открытый). Для
этого ввожу команду ssh-keygen -C, вводя имя и почту владельца.(рис. [-@fig:006])

![Генерация ключей](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/5.png){#fig:006 width=70%}

Нахожу этот ключ и копирую его. Далее захожу на сайт github, открываю
свой профиль, захожу в настройки, выбираю SSH and GPG keys и
вставляю свой ключ предварительно назвав его в поле title.(рис. [-@fig:007] и [-@fig:008])

![Нахождение ключа](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/6.png){#fig:007 width=70%}

![Копирования ключа](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/7.png){#fig:008 width=70%}

4. Создание рабочего пространства и репозиторя курса на основе шаблона
С помощью команды mkdir и ключа -p создаю все директории
~/work/study/2023-2024/"Архитектура компьютера", не забывая проверить
их создание командой ls.(рис. [-@fig:009] и [-@fig:010])

![Создание директорий](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/8.png){#fig:009 width=70%}

![Проверка создания директорий](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/9.png){#fig:010 width=70%}

5. Создание репозитория курса на основе шаблона
Перехожу на страницу репозитория с шаблоном курса. Далее выбираю Use
this template.(рис. [-@fig:011])

![Use this template](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/10.png){#fig:011 width=70%}

В открывшемся окне задаю имя репозитория study_2023–2024_arh-pc и
создаю репозиторий.(рис. [-@fig:012])

![Создание перозитория](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/11.png){#fig:012 width=70%}

Репозиторий успешно создан.(рис. [-@fig:013])

![Клонирование](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/12.png){#fig:013 width=70%}

Открываю терминал и перехожу в каталог курса. Клонирую репозиторий с
помощью команды git clone —recursive, взяв ссылку со страницы
созданного репозитория.(рис. [-@fig:014])

![Ссылка](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/13.png){#fig:014 width=70%}

6. Настройка каталога курса.

![??](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/14.png){#fig:015 width=70%}

Перехожу в каталог курса и удаляю ненужные файлы.(рис. [-@fig:016] и [-@fig:017])

![Переход в каталог курса](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/15.png){#fig:016 width=70%}

![Удаление ненужного файла](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/16.png){#fig:017 width=70%}

Создаю необходимые каталоги.(рис. [-@fig:018])

![Создание каталога](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/17.png){#fig:018 width=70%}

Отправляю файлы на сервер с помощью команд git add, git commit и git
push.(рис. [-@fig:019] и [-@fig:020]) 

![Отправление файлов](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/18.png){#fig:019 width=70%}

![Отправление файлов](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/19.png){#fig:020 width=70%}

Проверяю сайт Github, чтобы убедиться, что всё сделано правильно. (рис. [-@fig:021])

![Проверка создания файлов](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/20.png){#fig:021 width=70%}

#Выполнение хаданий для самостоятельной работы

1. Создайте отчет по выполнению лабораторной работы в
соответствующем каталоге рабочего пространства (labs>lab02>report).

Чтобы создать файл с отчетом, использую команду touch, предварительно
перейдя в папку report.(рис. [-@fig:022])

![Проверка создания файлов](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/21.png){#fig:022 width=70%}

Далее я могу начать писать отчёт в этом файле с помощью программы
libreoffice.

2. Скопируйте отчеты по выполнению предыдущих лабораторных работ в
соответствующие каталоги созданного рабочего пространства.

Для того чтобы скопировать отчет по выполнению предыдущей
лабораторной работы, нужно сначала найти его.(рис. [-@fig:023])

![Нахождение отчета](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/22.png){#fig:023 width=70%}

После того как я узнал, где он находится, можно скопировать его в
соответствующую папку с помощью команды cp.(рис. [-@fig:024])

![Копирование отчета](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/23.png){#fig:024 width=70%}

3. Загрузите файлы на github.

Перехожу в каталог с моей лабораторной работой и с помощью команды
git add добавляю файл Л1_Намруев_отчет.odt. Далее сохраняю изменения
командой git commit -m.(рис. [-@fig:025] )

![Добавление отчета](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/26.png){#fig:025 width=70%}

Также использую команду git push -f origin master.(рис. [-@fig:026])

![Отправка отчета](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/27.png){#fig:026 width=70%}

На сайте проверяю правильность сделанных действий.(рис. [-@fig:027])

![Проверка отправки](/afs/.dk.sci.pfu.edu.ru/home/m/s/msnamruev/Изображения/лаба2/28.png){#fig:027 width=70%}

То же самое делаю с файлом Л03_Намруев_отчет.odt.

# Выводы

После выполнение данной работы я изучил идеологию git, а также
научился пользоваться системой контроля версий.

# Список литературы{.unnumbered}

::: {#refs}
:::
