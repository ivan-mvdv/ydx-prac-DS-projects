# Отток клиентов
Из «Бета-Банка» стали уходить клиенты. Каждый месяц. Немного, но заметно. Банковские маркетологи посчитали: сохранять текущих клиентов дешевле, чем привлекать новых.

Нужно спрогнозировать, уйдёт клиент из банка в ближайшее время или нет. Вам предоставлены исторические данные о поведении клиентов и расторжении договоров с банком. 

Постройте модель с предельно большим значением *F1*-меры. Чтобы сдать проект успешно, нужно довести метрику до 0.59. Проверьте *F1*-меру на тестовой выборке самостоятельно.

Дополнительно измеряйте *AUC-ROC*, сравнивайте её значение с *F1*-мерой.

Источник данных: [https://www.kaggle.com/barelydedicated/bank-customer-churn-modeling](https://www.kaggle.com/barelydedicated/bank-customer-churn-modeling)

**План исследования:**  
* Ознакомиться с данными
* Осуществить предобработку данных
* Разбить данные на выборки (Обучающая, валидационная, тестовая)
* Оценить эффективность разных моделей на несбалансированной выборке
* Сбалансировать выборку различными способами (апсэмплинг, даунсэмплинг, изменение порогового значения)
* Подбор оптимальной модели (метод, гиперпараметры)
* Проверить модель с наилучшими гиперпараметрами на тестовой выборке

## Общий вывод:
* Была проведена предобработка данных: заполнение пропусков, изменение типов данных, OHE-преобразование, стандартизация.
* Данные были оценены и разбиты на выборки со стратификацией по целевому признаку.
* Были построены предиктивные модели разных видов с подбором оптимальных гиперпараметров на несбалансированной выборке.
* Были оценены различные способы борьбы с дисбалансом с помощью моделей разных видов с подбором оптимальных параметров
* Наилучшие комбинации методов моделирования и подходов к дисбалансу были проверены на тестовой выборке.  
Определен  подход - применять модель случайного леса:
  * с 45 эстиматорами
  * c наибольшей глубиной дерева = 10
  * обучениe на уменьшенной выборке
  * скоректированный порог чувствительности = 0.56.
  
* Метрики наилучшей модели: 
  * Precision = 0,544
  * Recall = 0,671
  * Accuracy = 0,819
  * F1-score = 0,601
  * AUC-ROC = 0,839