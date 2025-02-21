# Работа с директориями

Создайте дерево из директорий:

```bash
{{ ydb-cli }} scheme mkdir my-directory
```

```bash
{{ ydb-cli }} scheme mkdir my-directory/sub-directory1
```

```bash
{{ ydb-cli }} scheme mkdir my-directory/sub-directory1/sub-directory1-1
```

```bash
{{ ydb-cli }} scheme mkdir my-directory/sub-directory2
```

Чтобы посмотреть рекурсивный листинг всех поддиректорий и объектов в них по указанному пути, воспользуйтесь опцией `-R` подкоманды `scheme ls`:

```bash
{{ ydb-cli }} scheme ls my-directory -lR
```

Результат:

```text
┌──────┬─────────────────────────┬──────┬─────────┬──────────┬─────────────────────────────────┐
| Type | Owner                   | Size | Created | Modified | Name                            |
├──────┼─────────────────────────┼──────┼─────────┼──────────┼─────────────────────────────────┤
| dir  | aje1ok849pfu9jvnamh0@as |      |         |          | sub-directory1                  |
| dir  | aje1ok849pfu9jvnamh0@as |      |         |          | sub-directory1/sub-directory1-1 |
| dir  | aje1ok849pfu9jvnamh0@as |      |         |          | sub-directory2                  |
└──────┴─────────────────────────┴──────┴─────────┴──────────┴─────────────────────────────────┘
```
