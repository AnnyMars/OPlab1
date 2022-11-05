﻿**Лабораторная работа №1**

![](img/Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.001.png)
# **Основное задание**
Спроектировать и разработать систему авторизации пользователей на протоколе HTTP.

Система должна обладать следующим функционалом:

- Функциональность входа и выхода
- Пароли должны хранится в хешированном виде


## **1. Описание пользовательских сценариев работы**

`     `Возможности:

- Регистрация 
- Вход/выход

После авторизации пользователю открываются следующие возможности:

1. Выход из аккаунта

Если пользователь был ранее авторизован на сайте, у него есть cookie с токеном, и токен совпадает с токеном в БД, то при обновлении страницы, закрытия вкладки, закрытия браузера, он останется на главной странице.

После того как срок годности cookie закончится, при обновлении главной страницы, будет произведен автоматический выход из аккаунта. Пользователь будет перенаправлен на страницу входа.

1. ## **Описание API сервера и хореографии**
![](img/Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.002.png)Пример запросов, когда пользователь впервые заходит на страницу index.php,

а после регистрируется:

![](img/Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.003.jpeg)

Пример запросов, когда пользователь заходит на страницу авторизации, вводит неверное имя пользователя, а после вводит верные данные и входит в аккаунт:

![](img/Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.004.jpeg)







1. ## **Описание структуры базы данных**
Хранение данных производится с помощью JSON файла. Каждый объект содержит в себе login пользователя, хэш пароля и токен.

Пример:

![](img/Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.005.png)
1. ## **Описание алгоритмов**
![](img/Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.002.png)Алгоритм страницы регистрации

![](img/Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.006.png)

![](img/Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.007.png)![](Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.002.png)Алгоритм страницы авторизации:





# **Значимые фрагменты кода**
Проверка данных из формы регистрации и запись данных в БД:

![](img/Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.008.png)

Проверка введенных данных, обновления токена при авторизации:

![](img/Aspose.Words.b4c1f453-2915-42f3-8f89-01383e7c9142.009.png)




