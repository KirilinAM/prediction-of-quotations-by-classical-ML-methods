# prediction-of-quotations-by-classical-ML-methods
## Цели и задачи
- Собрать франкенштейна из данных включающих информацию об акциях их свечи и новости с сайта MOEX
- Использовать для обучения xgbooster, для выяснения будут ли акции расти или падать
- Проверить гипотез:
    1. Рынок приспосабливается к стратегиям. Иными словами, чем дальше период на котором обучалась модель от цели предсказания, тем ниже точность предсказания.
    2. Внешние данны важны. Иными словами, предсказания котировок с ипользованием внешних текстов получаются точнее, чем без них.
## Результаты
- Точность получившихся моделей мала и не превышает 0.75
- Нет строгого падения точности при увеличении времени между тренировочным и тестовым множеством.
- Самыми значимыми для предсказания фичами являются:
    1. SECID.
    2. Значения свечей за последний и первый дни периода .
    3. Некоторые элементы текстового вектора.
## Выводы
- Гипотеза 1 о приспосаблении к стратегиям отвергается.
- Гипотеза 2 о влиянии внешних данных не отвергается, хоть и нельзя утверждать точно в силу слабой точности моделей.
- Возможно использование деревьев не как основы а как корректора над другими методами типа ARIMA будет более результативной.
## Источник данных
- Акции, а так же свечи, были получены с помощью https://github.com/algotrading-py/TAHOMETR-TRADER/tree/main
- Текст, он же новости MOEX, получен с помощью API MOEX в `text collection.ipynb`
