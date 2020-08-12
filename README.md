# Заметки про базы данных

## Транзакции (на примере JPA) 

#### Вопросы
1. Понятие и свойства транзакицй;
2. Управление транзакциями в JPA;
3. Уровни изоляций транзакий;
4. Стратегии блокировки;
5. Бизнес-трнзакции.

### Понятие и свойства транзакицй

**Транзакция** - это ограниченный набор действий, с явно определенными начальной и завершающей операцией, который либо выполняется целиком, либо не выполняется вовсе.

**Свойства транзакций (ACID)**: 
1. Atomicity (атомарность) - в контексте набора действий выполняются либо все действия, либо ни одного;
2. Consistency (согласованность) - системные ресурсы должны пребывать в целостном и не противоречивом состоянии, транзакция не должна ничего испортить;
3. Isolation (изолированность) - до момента фиксаций одной транзакции, данные не должны быть доступны другим для изменения;
4. Durability (устойчивость) - результат выполнения транзакции не должен быть утрачен ни при каких обстоятельствах. То есть, транзакция завершилась - данные изменились и никак иначе.


Эти свойства могут настраиваться. Чаще всего настраивается Isolation. 

**Анамалии транзакций**. Настраиваются изменением уровня изоляции. 
1. Потерянные изменеия - при отсутствии уровня изоляции
