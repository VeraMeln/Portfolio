# Прогноз оттока клиентов банка

## Задача

Из «Бета-Банка» стали уходить клиенты. Каждый месяц. Немного, но заметно. Банковские маркетологи посчитали: сохранять текущих клиентов дешевле, чем привлекать новых.

Нужно спрогнозировать, уйдёт клиент из банка в ближайшее время или нет. Предоставлены исторические данные о поведении клиентов и расторжении договоров с банком.

Необходимо построить модель с предельно большим значением F1-меры. Нужно довести метрику до 0.59.

## Используемые библиотеки

pandas, numpy, matplotlib, sklearn

## Данные

- индекс строки в данных
- уникальный идентификатор клиента
- фамилия
- кредитный рейтинг
- страна проживания
- пол
- возраст
- сколько лет человек является клиентом банка
- баланс на счёте
- количество продуктов банка, используемых клиентом
- наличие кредитной карты
- активность клиента
- предполагаемая зарплата

Целевой признак

- Exited — факт ухода клиента

## Результаты

В ходе исследования задачи я **пробовала три модели**: 

- логистической регрессии, 
- дерева решений 
- и случайного леса. 

Подбирала гиперпараметры моделей на обучающей выборке и проверяла качество на валидационной. 

Для **борьбы с негативным влиянием дисбаланса классов** на качество модели изменила настройки гиперпараметра class_weight, увеличила в выборке число примеров более редкого класса и уменьшила число примеров более частого класса.

Для проверки качества модели вычисляла **оценки F1 и AUC-ROC**, а также строила **графики ROC-кривых**.

Самые **лучшие результаты** показала **модель случайного леса** со следующими значениями гиперпараметров:

- количество деревьев 20
- глубина 12
- class_weight со значением balanced

Увеличение в выборке числа примеров более редкого класса с помощью техники **upsampling способствует повышению качества модели**.

**Значения метрик** при обучении модели случайного леса с учетом всех результатов исследования **на тестовой выборке**:
- F1: 0.6209,
- AUC-ROC: 0.8522.