# Анализ данных сайта Stackoverflow

## Задача
В вашем распоряжении данные пользователей сайта Stackoverflow. Необходимо подключиться к базе данных с помощью SQLAlchemy и написать несколько SQL-запросов в Jupyter Notebook. 

Задача — провести анализ поведения пользователей сайта Stackoverflow в первые полгода после его появления.

## Используемые библиотеки
pandas, sqlalchemy, matplotlib, seaborn

## Результаты

Был **проведен анализ данных пользователей сайта Stackoverflow** за первые полгода его работы.

В данных присутствуют **аномалии**: 

- у некоторых пользователей первый **пост опубликован до их регистрации на сайте**

- правила Stackoverflow позволяют **разным пользователям иметь одинаковые отображаемые имена**, это требует аккуратности при подсчете пользовательской статистики.

**Анализ поведения пользователей**.

**Динамика просмотров** в первый год работы сайта. В первый месяц (июль) работы сайта количество просмотров самое маленькое. Дальше количество просмотров растет и достигает максимума в третьем месяце работы сайта (сентябрь). Затем происходит спад просмотров, что говорит о том, что пользователи стали привыкать к имеющемуся функционалу и посещать сайт только при возникновении необходимости.

**Количество публикаций** с сентября по декабрь 2008 года постепенно уменьшается.

**Возврат пользователей на сайт**. Для подсчета Retention Rate пользователей разбили на когорты по месяцу первой публикации. Retention Rate снижается по месяцам в каждой когорте. Кроме того, процент возврата во втором месяце самый высокий в первой когорте и последовательно снижается в каждой следующей.
