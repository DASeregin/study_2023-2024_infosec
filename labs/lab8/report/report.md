---
## Front matter
title: "Отчёт по лабораторной работе №8"
author: "Серегин Денис Алексеевич"

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

Освоить на практике применение режима однократного гаммирования на примере кодирования различных исходных текстов одним ключом. 

# Задание

2. Два текста кодируются одним ключом (однократное гаммирование). Требуется не зная ключа и не стремясь его определить, прочитать оба текста. Необходимо разработать приложение, позволяющее шифровать и дешифровать тексты P1 и P2 в режиме однократного гаммирования. Приложение должно определить вид шифротекстов C1 и C2 обоих текстов P1 и P2 при известном ключе ; Необходимо определить и выразить аналитически способ, при котором злоумышленник может прочитать оба текста, не зная ключа и не стремясь его определить.

# Выполнение лабораторной работы

1. Изучил указания к лабораторной работе 

2. Написал функцию генерации случайного ключа. (рис. @fig:001)

   ![Функция генерации ключа](/Users/denis_seregin/study_2023-2024_infosec/labs/lab7/report/image/Shot 2023-10-21 в 17.02.30.png){#fig:002 width=70%}

3. Написал функцию шифрования текста основываюсь на однократном гаммировании.  (рис. @fig:002)

   ![Функция шифрования](/Users/denis_seregin/study_2023-2024_infosec/labs/lab7/report/image/Shot 2023-10-21 в 17.02.44.png){#fig:002 width=70%}

4. Взял два текста и зашифровал их друг другом (рис. @fig:004)

5. Попробовал расшифровать полученный текст используя изначальные тексты. Как итог расшифровывая одним текстом я получал другой исходный. (рис. @fig:003)

   ![Вывод работы программы](/Users/denis_seregin/study_2023-2024_infosec/labs/lab8/report/image/Shot 2023-10-28 в 19.53.09.png){#fig:003 width=70%}


# Выводы

В результате выполнения работы я смог освоить метод однократного гаммирования и написать на его основе шифруюшее приложение, чтобы зашифровать два текста. 

