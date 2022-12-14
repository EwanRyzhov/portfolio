# Работа с временными рядами
Цель работы — построить модель, которая сможет спрогнозировать спрос на такси. Модель должна показать на тестовой выборке метрику RMSE не более 48 — то есть ошибаться не более, чем на 48 заказов в час. Исходные данные (файл 'taxi.csv') хранят данные о заказах такси за каждые 10 минут. Дополнительных признаков (например, о проблемах в работе аэропорта) данные не содержат.
### Стек проекта:
`python`, `numpy`, `seaborn`, `pyplot`, `sklearn`, `statsmodels`, `catboost`
### Результаты проекта:

Данные были ресемлированы с часовым интервалом. После этого были изучены имеющийся тренд и сезонность. Было отмечено, что спрос на услуги такси постепенно растет. "Сезонность" внутри суток — было отмечено, что спрос растет ближе к ночи — когда прекращает работу общественный транспорт, а также в начале и конце рабочего дня (около 8 и 18 часов).

Для прогнозирования данных нами были созданы календарные признаки (день, день недели), скользящее среднее и отстающие значения — для точности прогнозирования мы взяли значения за предыдущие 24 часа (т.е. сутки).

При обучении лучшие результаты дала модель RandomForestRegressor — адекватность ее работы и была проверена на тестовой выборке.
