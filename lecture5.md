## Лекция № 6.
## Базы данных: какие они бывают и что такое реляционная алгебра 
## Лектор: Борчук Леонид


> База данных - материалы, систематизированные таким образом, чтобы из можно было обработать на ЭВМ. 
> БД - структурированные, постоянно хранимые, логически связанные данные

### Модели данных

> Модель != Схема

- иерархическая
- объектная 
- сетевая

### Эволюция БД 

- Hadoop
- NoSQL (MONGo)
- Объектные
- Реляционные
- Сетевые
- файловые

### Реляционные системы

- позволяют создавать новые БД и определять их схему на языке определения данных
- позволяет запрашивать данные на языке запросов
- поддерживает хранение больших массивов данных и защищает от их случайной потери
- предоставляет возможность многопользовательской одновременной работы

> СУБД - программы и языки для создания и использования БД.


Почему реляционные системы? 

- реляционная модель
- System R, INGRES 
- универсальная БД 
- оптимизация запросов 
- SQL

#### Реляционная модель

- данные представлены в виде отношений
- каждое отношение состоит из атрибутов
- каждый кортеж содержит по одному значению каждого из ? 

> System R - исследовательский проект IBM, 1970-е. 


> **INGRES**  - исследовательский проект Беркли (70-е), параллельно с System R.


> Группа АСМ SIGMOD - специализируется на БД. Проводит конференции с 75 года. Содержит 10к работа, 174к ссылок на научные работы. 


### SQL 

SQL - стандарт (SQL-92). 

Способ выполнения запроса определяется СУБД: пользователь лишь указывает, какие данные ему нужны.

### Реляционная подсистема

АБстракция - интерфейс RSS, реляционная машина, "движок" БД. 

Простейшие процедуры, которые реализуют операции манипуляции данными.


> К современным системам предъявляются требования не только функциональности, но и производительности. 

### Недостатки реляционных СУБД

- реляционная модель - не всегда удобно данные представлять в табличном виде (объекты)
- транзакции (теорема САР, Брюер), накладные расходы на обеспечение транзакций (журнал) 
- универсальная БД (накладные расходы)
- SQL (NoSQL)

### Альтернативы универсальным БД

- MySQL (можно обойтись без тразакций)
- Vertica (поколоночная)
- MongoDB (документо-ориентированная, горизонтальное масштабирование)
- Hadoop - каркая для построения своей системы

- - - - - 
### Литература:

* Сергей Кузнецов - Основы баз данных
* Кристофер Дейт - Введение в системы баз данных
* Томас Коннолли, Каролин Бегг - Базы данных. Проектирование, реализация, и сопровождение. 
* Гектор Гарсиа-Молина, Джеффри УЛьман, Дженнифер Уидом - Системы баз данных. 



- - - - 


## Часть 2. SQL, нормальная форма.

Создание БД:

* описание модели
* создание модели
* изучение модели
* работа с моделью


### Формальный подход

Три этапа:

- Концептуальный - описание предметной области
- Логический 
- Физический

### Принципы при создании модели

- адекватность (правильность)
- без избыточности
- простота (бритва Оккама)
- использование сложившихся приёмов

### ER - диаграмма 

Моделей множество, но наиболее популярной стала модель "сущность" - "связь".
Модель графическая: прямоугольники - элементы, линии - связи между ними.

Предложена в 1976 году. 

#### Нормальная форма

> Нормализация - восходящий подход к проектированию БД (сущность-связь - нисходящий), удобен для проверки свойств модели.
> Т.е. модель последовательно переводится из одного состояния в другое, эти состояния называются нормальными формами. 
> 
> Нормальная форма - строгое математическое определение, совокупность требований.


#### Аномалии 

> Аномалии возникают в том случае, когда наши знания о предметной области, оказываются по каким-то причинам невыразимыми в схеме БД или входящими в противоречие с ней. 


ДЗ - пописать SQL запросы. 