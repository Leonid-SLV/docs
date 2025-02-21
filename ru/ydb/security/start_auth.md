---
title: Управление доступом в Yandex Database
description: "Управление доступом в сервисе по созданию и управлению базами данных Yandex Database. Чтобы разрешить доступ к ресурсам сервиса YDB (базы данных и их пользователи), назначьте пользователю нужные роли из приведенного списка."
---

# Управление доступом в {{ ydb-name }}


Пользователь {{ yandex-cloud }} может выполнять только те операции над ресурсами, которые разрешены назначенными ему ролями. Пока у пользователя нет никаких ролей, почти все операции ему запрещены.

Чтобы разрешить доступ к ресурсам сервиса {{ ydb-short-name }} (базы данных и их пользователи), назначьте пользователю нужные роли из приведенного ниже списка. На данный момент роль может быть назначена только на родительский ресурс (каталог или облако), роли которого наследуются вложенными ресурсами.

{% note info %}

Подробнее о наследовании ролей читайте в разделе [{#T}](../../resource-manager/concepts/resources-hierarchy.md#access-rights-inheritance) документации сервиса {{ resmgr-full-name }}.

{% endnote %}

## Назначение ролей {#grant-roles}

Чтобы назначить пользователю роль:

{% include [grant-role-console](../../_includes/grant-role-console.md) %}

## Роли {#roles}

Ниже перечислены все роли, которые учитываются при проверке прав доступа в сервисе {{ ydb-short-name }}.

{% include [cloud-roles](../../_includes/cloud-roles.md) %}

### {{ roles-ydb-viewer }}

Пользователь с ролью `{{ roles-ydb-viewer }}` может выполнять следующие действия:

* устанавливать соединения c БД;
* просматривать список схемных объектов (таблиц, индексов и каталогов);
* просматривать описание схемных объектов (таблиц, индексов и каталогов);
* просматривать информацию о БД;
* выполнять запросы на чтение данных.

Также пользователю с данной ролью доступно получение списка каталогов в облаке и списка ресурсов в каталоге облака.

Все полномочия роли `{{ roles-ydb-viewer }}` включены в состав роли `{{ roles-viewer }}`.

### {{ roles-ydb-editor }}

Пользователь с ролью `{{ roles-ydb-editor }}` может выполнять следующие действия:

* управлять БД, например создать БД или изменить ее параметры;
* создавать, изменять и удалять объекты схемы в БД (таблицы, индексы и каталоги);
* выполнять запросы на запись данных.

Помимо этого роль `{{ roles-ydb-editor }}` включает в себя все разрешения роли `{{ roles-viewer }}`.

Все полномочия роли `{{ roles-ydb-editor }}` включены в состав роли `{{ roles-editor }}`.

### {{ roles-ydb-admin }}

Состав полномочий роли `{{ roles-ydb-admin }}` идентичен составу полномочий роли `{{ roles-ydb-editor }}`.

### {{ roles-viewer }}

Пользователь с ролью `{{ roles-viewer }}` может просматривать информацию о ресурсах, например посмотреть список хостов или получить информацию о кластере БД.

### {{ roles-editor }}

Пользователь с ролью `{{ roles-editor }}` может управлять любыми ресурсами, например создать кластер БД, создать или удалить хост в кластере.

Помимо этого роль `{{ roles-editor }}` включает в себя все разрешения роли `{{ roles-viewer }}`.

### {{ roles-admin }}

Пользователь с ролью `{{ roles-admin }}` может управлять правами доступа к ресурсам, например разрешить другим пользователям создавать кластеры БД или просматривать информацию о них.

Помимо этого роль `{{ roles-admin }}` включает в себя все разрешения роли `{{ roles-editor }}`.
