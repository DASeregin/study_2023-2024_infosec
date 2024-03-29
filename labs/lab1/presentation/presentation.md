---
## Front matter
lang: ru-RU
title: Лабораторная работа No 1.
author:
  - Серегин Д. А.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 15 сентября 2023

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'

---

## Цель работы

Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

# Выполнение лабораторной работы

## Подготовка виртуальной машины к установке

1. Создадим виртуальную машину, с диском VDI, размера 20гб, выделим 2048мб оперативной памяти на её работу.

2. Подключим iso образ инсталятора Rocky Linux.

3. Запустим и перейдем к установке.

## Установка Rocky Linux

1. Выбираем язык операционной системы English и язык раскраски English (United States).

2. Выбираем автоматическую разметку диска.

## Установка Rocky Linux

3. Добавляем нового пользователя, учитывая соглашение об именовании.

4. В предустанавливаемом ПО выбираем базовое окружение "Сервер с GUI" и группу "Developments tool".

![ПО](./image/1.png){width=70%}

## Установка Rocky Linux

5. Отключаем kdump.

6. Выставляем пароль для рута.

7. Задаем hostname.

8. Запускаем установку.

## Установка Rocky Linux

9. Проверяем правильность установленного hostname и username (согласно соглашению об именовании).

![Проверка](./image/2.png){width=70%}

## Домашнее задание

![Версия ядра](./image/3.png){width=70%}

![Частота процессора](./image/4.png){width=70%}

## Домашнее задание

![Модель процессора](./image/5.png){width=70%}

![Объем памяти](./image/6.png){width=70%}

## Домашнее задание

![Гипервизор](./image/8.png){width=60%}

![Тип FS и последовательность монитрования](./image/7.png){width=50%}

## Выводы

По итогам выполнения работы, я настроил виртуальную машину с Rocky Linux. А также смог выполнить поиск основных характеристик системы
