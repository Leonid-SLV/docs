---
sourcePath: ru/ydb/yql/reference/yql-docs-core-2/builtins/_includes/basic/coalesce.md
---
## COALESCE {#coalesce}

Перебирает аргументы слева направо и возвращает первый найденный непустой аргумент. Чтобы результат получился гарантированно непустым (не [optional типа](../../../types/optional.md)), самый правый аргумент должен быть такого типа (зачастую используют литерал). При одном аргументе возвращает его без изменений.

Позволяет передавать потенциально пустые значения в функции, которые не умеют обрабатывать их самостоятельно.

Доступен краткий формат записи в виде оператора `??`, обладающего низким приоритетом (ниже булевых операций). Можно использовать алиас `NVL`.

**Примеры**
``` yql
SELECT COALESCE(
  maybe_empty_column,
  "it's empty!"
) FROM my_table;
```

``` yql
SELECT
  maybe_empty_column ?? "it's empty!"
FROM my_table;
```

``` yql
SELECT NVL(
  maybe_empty_column,
  "it's empty!"
) FROM my_table;
```

<span style="color: gray;">(все три примера выше эквивалентны)</span>