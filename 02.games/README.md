# Анализ продаж видеоигр. 
## Описание проекта

Вы работаете в интернет-магазине «Стримчик», который продаёт по всему миру компьютерные игры. Из открытых источников доступны исторические данные о продажах игр, оценки пользователей и экспертов, жанры и платформы (например, Xbox или PlayStation). Вам нужно выявить определяющие успешность игры закономерности. Это позволит сделать ставку на потенциально популярный продукт и спланировать рекламные кампании.
Перед вами данные до 2016 года. Представим, что сейчас декабрь 2016 г., и вы планируете кампанию на 2017-й. Нужно отработать принцип работы с данными. Неважно, прогнозируете ли вы продажи на 2017 год по данным 2016-го или же 2027-й — по данным 2026 года.
В наборе данных попадается аббревиатура ESRB (Entertainment Software Rating Board) — это ассоциация, определяющая возрастной рейтинг компьютерных игр. ESRB оценивает игровой контент и присваивает ему подходящую возрастную категорию, например, «Для взрослых», «Для детей младшего возраста» или «Для подростков».

## Цель исследования.  

Выявить факторы, определяющие успешность игры для последующего планирования рекламных кампаний.

## План исследования.
* Предобработка данных
  - Знакомство с данными, определение необходимых шагов
  - Работа с пропусками
  - Работа с типами данных
* Исследовательский анализ данных
* Составление портретов пользователей по регионам
* Проверка гипотез 
  - Средние пользовательские рейтинги платформ Xbox One и PC одинаковые
  - Средние пользовательские рейтинги жанров Action (англ. «действие», экшен-игры) и Sports (англ. «спортивные соревнования») разные.

### Описание данных

* Name — название игры
* Platform — платформа
* Year_of_Release — год выпуска
* Genre — жанр игры
* NA_sales — продажи в Северной Америке (миллионы проданных копий)
* EU_sales — продажи в Европе (миллионы проданных копий)
* JP_sales — продажи в Японии (миллионы проданных копий)
* Other_sales — продажи в других странах (миллионы проданных копий)
* Critic_Score — оценка критиков (максимум 100)
* User_Score — оценка пользователей (максимум 10)
* Rating — рейтинг от организации ESRB (англ. Entertainment Software Rating Board). Эта ассоциация определяет рейтинг компьютерных игр и присваивает им подходящую возрастную категорию.

## Общий вывод.
Был проведён анализ данных о продажах игр в разных регионах.  

### Предобработка данных.
- Определены столбцы с недостающими данными.
- Обработаны пропуски (часть данных дополнена исходя из данных датасета, часть данных осталась незаполненной)
- Скорректированы типы данных (где возможно)


Исследовательский анализ данных
Составление портретов пользователей по регионам
Проверка гипотез
Средние пользовательские рейтинги платформ Xbox One и PC одинаковые
Средние пользовательские рейтинги жанров Action (англ. «действие», экшен-игры) и Sports (англ. «спортивные соревнования») разные.

### Анализ данных.
#### Исследовательский анализ данных
- Изучены и обработаны все показатели, обнаружены следующие существенные для построения прогноза моменты:
  * Срок жизни платформы - 10 лет, за исключением ПК и мобильных платформ.  
  * Период анализа для построения прогноза - начиная с 2012.
  * На текущий момент актуальны три группы платформ:
    * "Живые мертвецы" (прошли пик популярности, продажи ненулевые, но к нулю активно стремятся) - PS3, XBOX360.
    * "Молодые" (выходят на пик популярности) - PS4, XBOX ONE.
    * Вечно "живые" - PC, 3DS. 
  При построении прогноза необходимо делать основной фокус на последние две группы.
  * Независимо от платформы, основная часть игр (75-ый квантиль) продаётся тиражом до 500 тыс копий. Это значение меняется от платформы к платформе.  
  При прогнозе продаж следует особое внимание уделить идентификации "выбросов"   
  * Между продажами и оценками критиков  для платформ Сони и Майкрософт есть умеренная корреляция. Это факторы, которые стоит принимать во внимание при построении прогноза, но не с большим весом, и только для соответствующих платформ.
  * Для платформ Нинтендо и ПК корреляция оценки критиков и продаж совсем незначительная.
  * Корреляция между отзывами пользователей и продажами игры - низкая для всех платформ. 
  * Топ-5 жанров по продажам:
    * Экшен
    * Спорт
    * РПГ
    * Шутеры
    * Прочие
  * Игры "прочих жанров" держатся стабильно год от году. 
  * РПГ и спорт конкурируют друг с другом за третье место в продажах,  шутеры и экшены - с отрывом на 1-2 месте. 
  * Продажи игр падают в целом, экшены упали в продажах сильнее прочих жанров.
  * С точки зрения продаж на одну игру самые интересные жанры - шутеры: средний шутер продастся в 1.8 раза лучше любой другой игры.


    
#### Составление портретов пользователей по регионам

- Изучены географические различия в популярности жанров и платформ, сделаны следующие выводы:
  * В северной Америке XBOX 360 популярнее чем любая прочая приставка и в своём поколении безоговорочно обыграл PS3.
  * В Европе больший процент людей играет на ПК, чем где-либо ещё.
  * В Японии у ПК-гейминга околонулевая популярность, в топе продаж игры для мобильных приставок Nintendo DS и 3DS.
  * В новом поколении PS4 обыгрывает XBOX даже в северной Америке.
  * Смерть консолей прошлого поколения наступила почти везде, за исключением PS3 в Японии. 
  * В северной Америке относительно прошлых периодов стали лучше продаваться RPG и намного хуже - гонки.
  * В Европе также теряют популярность, но существенно медленнее. Как и в США гонки уступили в популярности RPG.
  * Первые топ-4 жанра в Европе и Америке за последнее время идентичны.
  * В Японии популярны RPG и экшены, игры остальных жанров продаются сильно хуже.
  * Во всём мире значительная часть игр продаётся без рейтинга ESRB. 
  * Если раньше основная часть игр продавалась с рейтингом E/K-A, то сейчас в Европе и северной Америке основные "мани-мейкеры" - игры с рейтингом M. 
  * Картины за весь период в северной Америке и Европе очень похожи (Teen и Mature меняются местами в топ-5).  Картина за актуальный период идентична
  * В Японии игры без рейтинга были и остаются наиболее популярными.  
  
  
- Составлены актуальные портреты пользователей:  
  
  * ***Североамериканец***:
    * Скорее всего, ещё играет на XBOX 360, но будет обновляться. Скорее всего, на PS4.
    * Играет в экшены, шутеры, спорт.
    * Скорее всего, экшенам и шутерам, в которые он играет, присвоен рейтинг M.
  * ***Европеец***:
    * Уже поменял свою консоль на PS4 - это касается и "иксбоксеров", и "сонибоев".
    * Играет в те же экшены, шутеры, спорт.
    * Скорее всего, экшенам и шутерам, в которые он играет, присвоен рейтинг M.
  * ***Японец***:
    * Скорее всего, играет на 3DS - в дороге.
    * Играет в ролевые игры и экшены.
    * Скорее всего, игре, в которую он играет, не присвоен рейтинг.
    
#### Проверка гипотез  
##### Гипотеза 1. Средние пользовательские рейтинги платформ Xbox ONE и PC одинаковые.

Отвергнута в исторической перспективе, потверждена в актуальный период. Предлагаею опираться на последний вывод в связи с разным сроком жизни платформ.

##### Гипотеза 2. Средние пользовательские рейтинги жанров Action и Sports разные.

Отвергнута, средние пользовательские рейтинги игр этих жанров близки.
