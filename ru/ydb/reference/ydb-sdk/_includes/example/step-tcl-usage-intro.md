## Явное использование вызовов TCL Begin/Commit {#tcl-usage}

В большинстве случаев вместо явного использования [TCL](../../../../concepts/transactions.md) вызовов Begin и Commit лучше использовать параметры контроля транзакций в вызовах execute. Это позволит избежать лишних обращений к {{ ydb-short-name }} и эффективней выполнять запросы.
