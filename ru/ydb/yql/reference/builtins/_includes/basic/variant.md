---
sourcePath: ru/ydb/yql/reference/yql-docs-core-2/builtins/_includes/basic/variant.md
---
## Variant, AsVariant {#variant}

`Variant()` создает значение варианта над кортежем или структурой.

Аргументы:

* Значение
* Строка с именем поля или индексом кортежа
* Тип варианта

**Пример**
``` yql
$var_type = Variant<foo: Int32, bar: Bool>;

SELECT
   Variant(6, "foo", $var_type) as Variant1Value,
   Variant(false, "bar", $var_type) as Variant2Value;
```

`AsVariant()` создает значение [варианта над структурой](../../../types/containers.md) с одним полем. Это значение может быть неявно преобразовано к любому варианту над структурой, в которой совпадает для этого имени поля тип данных и могут быть дополнительные поля с другими именами.

Аргументы:

* Значение
* Строка с именем поля

**Пример**
``` yql
SELECT
   AsVariant(6, "foo") as VariantValue
```

