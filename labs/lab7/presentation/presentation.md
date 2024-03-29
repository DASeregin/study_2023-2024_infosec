---
## Front matter
lang: ru-RU
title: Лабораторная работа № 7.
author:
  - Серегин Д.А.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 21 октября 2023

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

# Цель работы

Освоить на практике применение режима однократного гаммирования. 

# Выполнение работы

## Задание

Нужно подобрать ключ, чтобы получить сообщение  **«С Новым Годом, друзья!»**. Требуется разработать приложение, позволяющее шифровать и дешифровать данные в режиме однократного гаммирования. Приложение должно: 

1. Определить вид шифротекста при известном ключе и известном открытом тексте. 
2. Определить ключ, с помощью которого шифротекст может быть преобразован в некоторый фрагмент текста, представляющий собой один из возможных вариантов прочтения открытого текста.

## Генерация ключа

1. Изучил указания к лабораторной работе 

2. Написал функцию генерации случайного ключа.

   ![Функция генерации ключа](/Users/denis_seregin/study_2023-2024_infosec/labs/lab7/report/image/Shot 2023-10-21 в 17.02.30.png){#fig:002 width=70%}

## Шифрование текста

3. Написал функцию шифрования текста основываюсь на однократном гаммировании.

![Функция шифрования](/Users/denis_seregin/study_2023-2024_infosec/labs/lab7/report/image/Shot 2023-10-21 в 17.02.44.png){#fig:003 width=70%}

## Нахождение ключа

4. Написал функцию нахождения ключа при наличии исходного текста и зашифрованного текста.  (рис. @fig:003)

![Функция нахождения ключа](/Users/denis_seregin/study_2023-2024_infosec/labs/lab7/report/image/Shot 2023-10-21 в 17.02.50.png){#fig:003 width=70%}

## Результаты

5. Проверил работу своих методов на фразе «С Новым Годом, друзья!» 

   ![Вывод работы программы](/Users/denis_seregin/study_2023-2024_infosec/labs/lab7/report/image/Shot 2023-10-21 в 17.03.05.png){#fig:004 width=70%}



# Вывод
В результате выполнения работы я смог освоить метод однократного гаммирования и написать на его основе шифруюшее приложение. 

