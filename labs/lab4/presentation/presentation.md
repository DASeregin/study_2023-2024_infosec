---
## Front matter
lang: ru-RU
title: Лабораторная работа № 4.
author:
  - Серегин Д.А.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 30 сентября 2023

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
theme: metropolis
section-titles: true
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
---

## Цель работы

Получение практических навыков работы в консоли с расширенными атрибутами файлов

## Выполнение лабораторной работы

1. От имени пользователя guest определим расширенные атрибуты файла /home/guest/dir1/file1 командой ``lsattr /home/guest/dir1/file1`` 

![Определим атрибуты](/Users/denis_seregin/study_2023-2024_infosec/labs/lab4/report/image/1 (3).png){#fig:001 width=70%}

## Выполнение лабораторной работы

2. Установим командой ``chmod 600 file1`` на файл file1 права, разрешающие чтение и запись для владельца файла. Попробуем установить на файл /home/guest/dir1/file1 расширенный атрибут a от имени пользователя guest: ``chattr +a /home/guest/dir1/file1`` В ответ мы получим отказ от выполнения операции.

![Меняем права и ставим расширенные атрибуты](/Users/denis_seregin/study_2023-2024_infosec/labs/lab4/report/image/2 (3).png){#fig:002 width=70%}

## Выполнение лабораторной работы

3. Установим расширенные атрибуты при помощи прав суперпользователя. 

![Ставим расширенные атрибуты](/Users/denis_seregin/study_2023-2024_infosec/labs/lab4/report/image/3 (3).png){#fig:003 width=70%}

4. Запишем в файл слово test.![запись в файл](/Users/denis_seregin/study_2023-2024_infosec/labs/lab4/report/image/4 (2).png){#fig:004 width=70%}



## Выполнение лабораторной работы

5. Попробуем перезаписать содержимое файла и сменить его имя - не получилось.

   ![смена имени и перезапись файла](/Users/denis_seregin/study_2023-2024_infosec/labs/lab4/report/image/6 (2).png){#fig:005 width=70%}

## Выполнение лабораторной работы

6. Попробуем сменить права для файла. ![смена прав файла](/Users/denis_seregin/study_2023-2024_infosec/labs/lab4/report/image/7 (2).png){#fig:006 width=70%}

## Выполнение лабораторной работы

7. Снимем расширенные атрибуты и попробуем проделать те же действия. 

![снимем расширенные атрибуты](/Users/denis_seregin/study_2023-2024_infosec/labs/lab4/report/image/8 (2).png){#fig:007 width=70%}




## Выводы

В результате выполнения работы я повысил свои навыки использования интерфейса командой строки (CLI), познакомился на примерах с тем, как используются основные и расширенные атрибуты при разграничении доступа. Имел возможность связать теорию дискреционного разделения доступа (дискреционная политика безопасности) с её реализацией на практике в ОС Linux. Составил наглядные таблицы, поясняющие какие операции возможны при тех или иных установленных правах. Опробовал действие на практике расширенных атрибутов «а» и «i».
