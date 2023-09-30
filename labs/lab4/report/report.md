---
## Front matter
title: "Отчёт по лабораторной работе №4"
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

Получение практических навыков работы в консоли с расширенными атрибутами файлов

# Выполнение лабораторной работы

1. От имени пользователя guest определим расширенные атрибуты файла /home/guest/dir1/file1 командой ``lsattr /home/guest/dir1/file1`` (рис. @fig:001).

![Определим атрибуты](image/1 (3).png){#fig:001 width=70%}

2. Установим командой ``chmod 600 file1`` на файл file1 права, разрешающие чтение и запись для владельца файла. Попробуем установить на файл /home/guest/dir1/file1 расширенный атрибут a от имени пользователя guest: ``chattr +a /home/guest/dir1/file1`` В ответ мы получим отказ от выполнения операции.  (рис. @fig:002).

   ![Меняем права и ставим расширенные атрибуты](image/2 (3).png){#fig:002 width=70%}

3. Установим расширенные атрибуты при помощи прав суперпользователя  (рис. @fig:003).

   ![Ставим расширенные атрибуты](image/3 (3).png){#fig:003 width=70%}

4. Запишем в файл слово test (рис. @fig:004)![запись в файл](image/4 (2).png){#fig:004 width=70%}



5. Попробуем перезаписать содержимое файла и сменить его имя - не получилось. (рис. @fig:005)

   ![смена имени и перезапись файла](image/6 (2).png){#fig:005 width=70%}

6. Попробуем сменить права для файла (рис. @fig:006)![смена прав файла](image/7 (2).png){#fig:006 width=70%}



7. Снимем расширенные атрибуты и попробуем проделать те же действия. (рис. @fig:007)

   ![снимем расширенные атрибуты](image/8 (2).png){#fig:007 width=70%}

# Выводы

В результате выполнения работы я повысил свои навыки использования интерфейса командой строки (CLI), познакомился на примерах с тем, как используются основные и расширенные атрибуты при разграничении доступа. Имел возможность связать теорию дискреционного разделения доступа (дискреционная политика безопасности) с её реализацией на практике в ОС Linux. Составил наглядные таблицы, поясняющие какие операции возможны при тех или иных установленных правах. Опробовал действие на практике расширенных атрибутов «а» и «i».

