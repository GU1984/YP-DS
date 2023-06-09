# Телеком

## Цель:

Построить модель прогнозирования оттока клинетов.

## Описание:
Оператор связи «Ниединогоразрыва.ком» хочет научиться прогнозировать отток клиентов. Если выяснится, что пользователь планирует уйти, ему будут предложены промокоды и специальные условия. Команда оператора собрала персональные данные о некоторых клиентах, информацию об их тарифах и договорах.

Информация о договорах актуальна на 1 февраля 2020.

## Выводы:

1. Подготовка данных для модели:
- Выделен целевого признак - расторгнут договор или нет. В качетве базы был взят признак 'end_time',
- Был создан новые признак - действие договра в днях,
- Неинформативные признаки (идентификатор пользователя и даты) и колиниарный признак total_charged удалены,
- Данные были разделены на обучающую и тестовую 75:25.
2. Были построены и обучены модели с соотвествующими результатами:
- Модель Линейной регресии: AUC-ROC = 0,75;
- Модель Случайного Леса: AUC-ROC = 0,82;
- Модель CatBoost: AUC-ROC = 0,86;
- Модель LGBM: AUC-ROC = 0,87;
3. Выводы по полученным результатам
- Наилучший результат показала модель LGBM, именно эту модель проверили на тестовой выборке.
4. Проверка лучшей модели на тестовой выборке
- Была проверена модель LGBM со следующимим параметрами: learning_rate=0.7, n_estimators=200, num_leaves=95.
- На тестовой выборке метрика AUC-ROC = 0,89.
5. Анализ лучшей модели:
- Влияние признаков:
 - Наиболее важными признаками оказались:
    * месячный платеж,
    * длительность пользования услугами в днях.
 - Влияние остальных параметров на порядок меньше.
- Составлена матрица ошибок: 
    * модель хорошо определяет отрицательный класс (не уйдет),
    * положительный класс (уйдет) опредляет хуже.
    
## Используемые библиотеки:
- CatBoost
- Pandas
- Matplotlib
- LightGBM
- Seaborn
- Scikit-learn    
