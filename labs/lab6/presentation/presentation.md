---
## Front matter
lang: ru-RU
title: Лабораторная работа № 6.
author:
  - Серегин Д.А.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 14 октября 2023

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

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux. Проверить работу SELinx на практике совместно с веб-сервером Apache.

# Выполнение работы

## Подготовка виртуальной машины

Перед выполнением лабораторной работы я подготовил виртуальную машину в соответствии с указаниями к лабораторной работе 

## Выполнение работы

1. Вошел в систему с полученными учётными данными и убедился, что SELinux работает в режиме enforcing политики targeted. 

   ![Режим и политика SELinux](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/1.png){#fig:001 width=70%}

## Выполнение работы

2. Проверил работу веб-сервера с помощью браузера, убедившись, что он успешно работает.

   ![Стандартная страница Apache](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/2.png){#fig:002 width=70%}
   
## Выполнение работы

3. Нашел процесс веб-сервера Apache в списке процессов. 

   ![Процесс веб-сервера Apache](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/3.png){#fig:003 width=70%}
   
## Выполнение работы

4. Проверил текущее состояние переключателей SELinux для Apache с использованием команды `sestatus -bigrep httpd`.

   ![Состояния переключателей Apache](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/4.png){#fig:004 width=70%}

## Выполнение работы

5. Получил статистику по политике с помощью команды `seinfo` и определил множество пользователей, ролей и типов. 

   ![Статистика по политику безопастности Apache](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/5.png){#fig:005 width=70%}

## Выполнение работы

6. Определил тип файлов и поддиректорий в директории `/var/www` с помощью команды `ls -lZ /var/www`. 

   ![Типы файлов](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/6.png){#fig:006 width=70%}

7. Определил тип файлов в директории `/var/www/html` с помощью команды `ls -lZ /var/www/html`. Как видим папка пуста. 

   ![Типы файлов](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/7.png){#fig:007 width=70%}

8. Определил круг пользователей, которым разрешено создание файлов в директории `/var/www/html`. 

   ![Стандартная страница Apache](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/8.png){#fig:008 width=70%}

## Выполнение работы

9. Создал от имени суперпользователя файл `/var/www/html/test.html` с указанным содержанием. 

   ![Файл test.html](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/9.png){#fig:009 width=70%}

10. Проверил контекст созданного файла, внес контекст, присваиваемый по умолчанию новым файлам в директории `/var/www/html` 

    ![Контекст файла](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/10.png){#fig:010 width=70%}

## Выполнение работы

11. Обратился к файлу через веб-сервер, введя в браузере соответствующий адрес, и убедился, что файл был успешно отображён. 

    ![Отображение файла](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/11.png){#fig:011 width=70%}

12. Изучил справку `man httpd_selinux` и сопоставил контексты файлов для `httpd`. Проверил контекст файла с помощью команды `ls -Z /var/www/html/test.html`. 

    ![Контекст файла](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/12.png){#fig:012 width=70%}

## Выполнение работы

13. Изменил контекст файла `/var/www/html/test.html` на другой, к которому процессу httpd не должен иметь доступа, и проверил изменение контекста.

14. Попытался снова получить доступ к файлу через веб-сервер и убедился, что была выдана ошибка "Forbidden". 

    ![Ошибка доступа](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/13.png){#fig:013 width=70%}

## Выполнение работы

15. Проанализировал ситуацию и выяснил, что файл не был отображен, несмотря на права доступа, изучив логи веб-сервера и системные логи. 

    ![Логи веб-сервера](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/14.png){#fig:014 width=70%}

## Выполнение работы

16. Попытался запустить веб-сервер Apache на прослушивание TCP-порта 81 и выяснил, что возник сбой. Так как порт не является стандартным. 

    ![Ошибка соединения с сервером](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/15.png){#fig:015 width=70%}

## Выполнение работы

17. Проанализировал логи и выяснил причину сбоя при попытке изменения порта прослушивания. 

    ![Логи Apache](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/16.png){#fig:016 width=70%}

18. Проанализировал логи веб-сервера Apache и системные логи, определив, где появились новые записи.

## Выполнение работы

19. Выполнил команду `semanage port -a -t http_port_t -p tcp 81` и убедился, что порт 81 добавлен. 

    ![Добавления порта 81 в разрешенные](/Users/denis_seregin/study_2023-2024_infosec/labs/lab6/report/image/17.png){#fig:017 width=70%}

20. Попытался снова запустить веб-сервер Apache и убедился, что он запустился успешно.

## Возвращение в исходное состояние

21. Вернул контекст файла `/var/www/html/test.html` к исходному, предварительно изменив его на `samba_share_t`.

22. Изменил обратно конфигурационный файл Apache, вернув порт прослушивания к 80.

23. Удалил привязку http_port_t к порту 81.

24. Удалил файл `/var/www/html/test.html`.

# Вывод
В результате выполнения работы я развил свои навыки администрирования Linux, смог настроить SELinux, а также поработать с веб-сервисом Apache. 