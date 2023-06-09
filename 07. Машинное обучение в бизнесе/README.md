# Выбор района добычи нефти

## Цель:

Построить модель машинного обучения, которая поможет определить регион, где добыча принесёт наибольшую прибыль, для определения места бурения новой скважины

## Описание:

Добывающая компания «ГлавРосГосНефть». Нужно решить, где бурить новую скважину. 

Предоставлены пробы нефти в трёх регионах. Характеристики для каждой скважины в регионе уже известны.

Необходимо помтроить модель для определения региона, где добыча принесёт наибольшую прибыль.

Провести анализ возможной прибыли и рисков техникой Bootstrap.

## Выводы:
В ходе выполнения данного проекта были выполнены следующие действия и получены соответсвующие результаты:
1. Произведена загрузка и подготовка данных:
  - удалены ненужные данные для модели,
  - изучено расперделние будущего целевого признака.
2. Обучена и проверена модель для каждого региона:
  - Разбиение данных на обучающую и валидационную выборки в соотношении 75:25.
  - Обучение модели и получение предсказания на валидационной выборке.
  - Получены следующие данные для каждого региона:
    * 1-й регион средний запас сыря : 92.59, RMSE: 37.58,
    * 2-й регион средний запас сыря : 68.73, RMSE: 0.89,
    * 3-й регион средний запас сыря : 94.97, RMSE: 40.03.
3. Расчёт прибыли:
  - Произведен рассчет достаточного объём сырья для безубыточной разработки новой скважины, что составило 111 тыс. бар.
  - Создана функция для расчета максимальной прибыли по заданому количеству скважин 200.
  - Произведен рассчет максимально возможной прибыли:
    * 1-й регион 3.32 млрд,
    * 2-й регион 2.42 млрд,
    * 3-й регион 2,42 млрд.
4. Произведен расчет рисков и прибыли для каждого региона:
  - Была применена техника Bootstrap с 1000 выборок.
  - Произведен расчет средней прибыли, 95%-й доверительный интервал и риск убытков.
    * 1-й регион: средняя выручка 425 млн, есть риск убытков 6.0%, 95% довертильный интервал -102 млн - 947 млн.
    * 2-й регион: средняя выручка 515 млн, есть риск убытков 1.0%, 95% довертильный интервал 68 млн - 931 млн.
    * 3-й регион: средняя выручка 435 млн, есть риск убытков 6.4%, 95% довертильный интервал -128 млн - 969 млн.
5. Выбран 2-й регион, как регион с наибольшим средним значением прибыли и наименьшим риском понести убыток.

## Используемые библиотеки:
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
