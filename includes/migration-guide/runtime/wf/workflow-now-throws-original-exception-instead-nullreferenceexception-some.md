### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a>Przepływ pracy zgłasza teraz oryginalnego wyjątku zamiast obiektu NullReferenceException w niektórych przypadkach

|   |   |
|---|---|
|Szczegóły|W .NET Framework 4.6.2 i wcześniejszymi wersjami, gdy metoda wykonania działania przepływu pracy zgłasza wyjątek z <code>null</code> wartość <xref:System.Exception.Message> właściwości środowiska uruchomieniowego przepływu pracy System.Activities zgłasza <xref:System.NullReferenceException?displayProperty=name>, maskowania Oryginalny wyjątek. W programie .NET Framework 4.7 wcześniej maskowanego wyjątku.|
|Sugestia|Jeśli kod opiera się na obsłudze <xref:System.NullReferenceException?displayProperty=name>, zmień ją na przechwytywać wyjątki, które może być wyrzucanych z działania niestandardowe.|
|Zakres|Mały|
|Wersja|4.7|
|Typ|Środowisko uruchomieniowe|
|Dotyczy interfejsów API|<ul><li><xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|

