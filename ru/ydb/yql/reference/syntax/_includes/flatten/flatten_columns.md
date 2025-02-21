---
sourcePath: ru/ydb/yql/reference/yql-docs-core-2/syntax/_includes/flatten/flatten_columns.md
---
## FLATTEN COLUMNS {#flatten-columns}

Преобразует таблицу, в которой все столбцы должны являться структурами, в таблицу со столбцами, соответствующими каждому элементу каждой структуры из исходных столбцов.

Имена исходных столбцов-структур не используются и не возвращаются в результате. Имена элементов структур не должны повторяться в исходных столбцах.

**Пример**

```sql
SELECT x, y, z
FROM (
  SELECT
    AsStruct(
        1 AS x,
        "foo" AS y),
    AsStruct(
        false AS z)
) FLATTEN COLUMNS;
```
