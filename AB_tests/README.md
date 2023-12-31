# AB тест

Задача:
Необходимо проверить правильность проведения теста, включая отсутствие пересечения с конкурирующими тестами и отсутствие пользователей, участвующих в двух группах одновременно. 
Также следует убедиться в равномерном распределении пользователей по тестовым группам и правильности их формирования. 
Наконец, необходимо проанализировать результаты теста.

**Техническое задание**
-	Название теста: 'recommender_system_test';
-	группы: : А — контрольная, B — новая платёжная воронка;
-	дата запуска: 2020-12-07;
-	дата остановки набора новых пользователей : 2020-12-21;
-	дата остановки : 2021-01-04;
-	аудитория: 15% новых пользователей из региона EU;
-	назначение теста : тестирование изменений, связанных с внедрением улучшенной рекомендательной системы;
-	ожидаемое количество участников теста : 6000.
-	ожидаемый эффект : за 14 дней с момента регистрации пользователи покажут улучшение каждой метрики не менее, чем на 10%:

**У нас есть 4 таблицы с данными**

- ab_project_marketing_events.csv — календарь маркетинговых событий на 2020 год.
- final_ab_new_users.csv — пользователи, зарегистрировавшиеся с 7 по 21 декабря 2020 года.
- final_ab_events.csv — действия новых пользователей в период с 7 декабря 2020 по 4 января 2021 года.
- final_ab_participants.csv — таблица участников тестов.

**Общий вывод**

Результаты теста можно назвать неудовлетворительными, по ним нельзя сделать какие либо выводы, так как нарушены ключевые критерии проведения АБ-тестирования и результаты дают искажение.
-	Для проведения тестирования были некорректно собранны данные,за период с 7 по 23 декабря 2020 года, хотя окончание набора пользователей было запланировано на 21 декабря.
-	В данных присутствуют пользователи не только из региона EU, но и из других регионов.
-	Проведение теста было запланировано с 7 декабря 2020 по 4 января 2021 года. Мы располагаем данными долько до 30 декабря 2020. Не хватает данных за 5 дней.
-	Наш тест пересекается с маркетинговым событием Christmas&New Year Promo в течение 5 дней, что может давать серьезные искажения.
-	В наш тест попали пользователи из конкурирующего теста в количестве 1602 (25,22%)
-	Из всех зарегистрированных в обозначенные в ТЗ времененные рамки
    -	Логин ввели в группе А -72% , в группе В - 32%.
    -	Просмотрели страницу с продуктом в группе А- 65% , в группе В - 56% из всех кто залогинился.
    -	Зашли в корзину в группе А - 46% , в группе В - 49% (прирост 6.5 %)
    -	В группе А конверсия в покупку- 23%, в группе В - 9%
-	Увеличении конверсии на 10% не достигнуто ,в группе А конверсия в покупку- 23%, что значительно больше ,чем в группе В (всего 9%).


