---
title: 'Informazioni sul chiamante (F #)'
description: Viene descritto come utilizzare attributi di argomenti informativi sul chiamante per ottenere informazioni sul chiamante da un metodo.
ms.date: 04/25/2017
ms.openlocfilehash: 0f2f4b16804d9156d234cc29d1f72ebe80a5b556
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44700898"
---
# <a name="caller-information"></a>Informazioni sul chiamante

Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo. È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante. Queste informazioni sono utili per la tracciatura, il debug e la creazione di strumenti diagnostici.

Per ottenere queste informazioni, utilizzare gli attributi applicati ai parametri facoltativi, a ognuno dei quali è associato un valore predefinito. Nella tabella seguente elenca gli attributi di informazioni sul chiamante definiti nel [CompilerServices](/dotnet/api/system.runtime.compilerservices) dello spazio dei nomi:

|Attributo|Descrizione|Tipo|
|---------|-----------|----|
|[CallerFilePath](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|Percorso completo del file di origine contenente il chiamante. Si tratta del percorso del file al momento della compilazione.|`String`
|[CallerLineNumber](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|Numero di riga nel file di origine in cui viene chiamato il metodo.|`Integer`|
|[CallerMemberName](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|Nome di una proprietà o di un metodo del chiamante. Vedere la sezione di nomi di membri più avanti in questo argomento.|`String`|

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come è possibile usare questi attributi per tracciare un chiamante.

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a>Note

Attributi informativi sul chiamante possono essere applicati solo a parametri facoltativi. È necessario fornire un valore esplicito per ciascun parametro facoltativo. Gli attributi di informazioni sul chiamante che il compilatore scrivere il valore appropriato per ciascun parametro facoltativo dotato di un attributo di informazioni sul chiamante.

I valori delle informazioni sul chiamante vengono generati come valori letterali in Intermediate Language (IL) in fase di compilazione. A differenza dei risultati del [StackTrace](/dotnet/api/system.diagnostics.stacktrace) proprietà per le eccezioni, i risultati non sono interessati da offuscamento.

È possibile fornire esplicitamente gli argomenti facoltativi per esaminare o nascondere le informazioni sul chiamante.

## <a name="member-names"></a>Nomi dei membri

È possibile usare la [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attributo per evitare di specificare il nome del membro come un `String` argomento al metodo chiamato. Utilizzando questa tecnica, si evita il problema che Refactoring di ridenominazione non cambia il `String` valori. Questo vantaggio è particolarmente utile per le attività seguenti:

* Utilizzo della tracciatura e delle routine di diagnostica.
* Implementa il [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interfaccia durante l'associazione dati. Questa interfaccia consente alla proprietà di un oggetto di notificare a un controllo associato la modifica della proprietà stessa in modo che il controllo possa visualizzare le informazioni aggiornate. Senza il [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attributo, è necessario specificare il nome della proprietà come valore letterale.

Il grafico seguente mostra il membro nomi che vengono restituiti quando si usa l'attributo CallerMemberName.

|Elemento in cui si verificano le chiamate|Nome del membro restituito|
|-------------------|------------------|
|Metodo, proprietà o evento|Nome del metodo, della proprietà o dell'evento da cui la chiamata ha avuto origine.|
|Costruttore|Stringa ".ctor"|
|Costruttore statico|Stringa ".cctor"|
|Distruttore|Stringa "Finalize"|
|Operatori o conversioni definiti dall'utente|Nome generato per il membro, ad esempio "op_Addition".|
|Costruttore dell'attributo|Nome del membro a cui viene applicato l'attributo. Se l'attributo è un qualsiasi elemento in un membro (ad esempio un parametro, un valore restituito o un parametro di tipo generico), il risultato è il nome del membro associato a tale elemento.|
|Nessun membro contenitore (ad esempio a livello di assembly o attributi applicati a tipi)|Valore predefinito del parametro facoltativo.|

## <a name="see-also"></a>Vedere anche

- [Attributi](attributes.md)  
- [Argomenti denominati](parameters-and-arguments.md#named-arguments)  
- [Parametri facoltativi](parameters-and-arguments.md#optional-parameters)  
