# Домашнее задание по теме "Системы Управления Базами Данных"
###
### Задание 1. СУБД
### Кейс
### Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для каждой предметной области.
###
### Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?
### Я не очень понял где какие СУБД используются, в интернете как-то смутно раскрывается эта тема, если никогда не работал с СУБД, очень сложно вообще судить об их применении.
### 1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.
### Чёткую структуру и целостность гарагтируют реляционные СУБД, в которых прослеживается четкая взаимосвязь между элементами
###
### 1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы?
###
### 1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.
### Лучше использовать также реляционные СУБД. Они гибкие и обеспечивают большую скорость раблоты с данными
### 1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?
###
### 1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.
### Складывается впречатление, что везде используются реляционные СУБД. Они простые в использовании, в анализе, гибкие, понятные. 
###
### 1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это реализовать?
###
### 1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по 
### маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.
### Реляционные СУБД PostgreSQL.
### 1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД логистов?
###
### 1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?
###
### Приведите ответ в свободной форме.
###
### Задание 2. Транзакции
### 2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.
### Ответ
### 1. Пользователь вводит номер своего телефона и сумму пополнения на сайте оператора или в мобильном приложении.
### 2. Оператор получает информацию, отправляет запрос в банк для подтверждения данной суммы на счете пользователя.
### 3. Если сумма доступна, банк отправляет запрос на подтверждение транзакции на телефон пользователя.
### 4. Пользователь подтверждает транзакцию, введя специальный код, отправленный банком.
### 5. Банк прееводит сумму оператору.
### 6. Оператор пополняет баланс пользователя.
###
### Задание 3. SQL vs NoSQL
### 3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.
### 1. Сформированность: MySQL - хорошо известная база данных, то есть она обладает крупным коммьюнити, широкими возможностями 
### тестирования и стабильностью
### 2. Совместимость: MySQL доступна на всех основных платформах, включая Linux, Windows, Mac, BSD и Solaris. Также у нее есть 
### адаптеры для таких языков, как Node.js, Ruby, C#, C++, Java, Perl, Python и PHP, то есть эта система не ограничена языком 
### запросов SQL
### 3. Экономичность: Система является открытой и бесплатной
### 4. Воспроизводимость: Базу данных MySQL можно использовать на разных узлах, что позволяет снизить нагрузку и повысить 
### масштабируемость и доступность приложения
### 5. Разделение данных: Несмотря на то что эту процедуру можно проводить на не всех SQL БД, серверы MySQL позволяют это сделать. Это не только экономично, но и может быть полезно для приложения.

### Задание 4. Кластеры
### Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.
###
### На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?
###
### Приведите ответ в свободной форме.
###  
###  В большинстве случаев SQL БД можно масштабировать вертикально, то есть можно проводить увеличение нагрузки на каждом отдельном сервере, повышая мощности ЦП, ОЗУ, твердотельного диска. А вот NoSQL БД можно масштабировать горизонтально. Это значит, что нагрузка распределяется благодаря разделению данных или добавлению большего количества серверов. Это как если бы вы добавляли больше  этажей к зданию либо добавляли больше зданий к району. В последнем варианте система может получиться более крупной и мощной. Именно поэтому для крупных или часто меняющихся БД обычно выбирают NoSQL. Наверно исходя из этого в нашем случае нужно использовать NoSQL БД 
###  