---
title: Informazioni sul chiamante
description: Viene descritto come usare gli attributi degli argomenti delle informazioni sul chiamante per ottenere informazioni sul chiamante da un metodo.
ms.date: 11/04/2019
ms.openlocfilehash: d995b37149277b7c7d1b6217ee484d3c90a7f8b3
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976803"
---
# <a name="caller-information"></a>Informazioni sul chiamante

Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo. È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante. Queste informazioni sono utili per la tracciatura, il debug e la creazione di strumenti diagnostici.

Per ottenere queste informazioni, utilizzare gli attributi applicati ai parametri facoltativi, a ognuno dei quali è associato un valore predefinito. La tabella seguente elenca gli attributi delle informazioni sul chiamante definiti nello spazio dei nomi [System. Runtime. CompilerServices](/dotnet/api/system.runtime.compilerservices) :

|Attributo|Descrizione|Digitare|
|---------|-----------|----|
|[CallerFilePath](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|Percorso completo del file di origine contenente il chiamante. Si tratta del percorso del file al momento della compilazione.|`String`
|[CallerLineNumber](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|Numero di riga nel file di origine in cui viene chiamato il metodo.|`Integer`|
|[CallerMemberName](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|Nome di una proprietà o di un metodo del chiamante. Vedere la sezione nomi dei membri più avanti in questo argomento.|`String`|

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come è possibile utilizzare questi attributi per tracciare un chiamante.

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member _.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        Trace.WriteLine(sprintf "Member name: %s" memberName)
        Trace.WriteLine(sprintf "Source file path: %s" path)
        Trace.WriteLine(sprintf "Source line number: %d" line)
```

## <a name="remarks"></a>Note

Gli attributi delle informazioni sul chiamante possono essere applicati solo ai parametri facoltativi. Gli attributi delle informazioni sul chiamante fanno sì che il compilatore scriva il valore appropriato per ogni parametro facoltativo decorato con un attributo info del chiamante.

I valori delle informazioni sul chiamante vengono generati come valori letterali in Intermediate Language (IL) in fase di compilazione. A differenza dei risultati della proprietà [StackTrace](/dotnet/api/system.diagnostics.stacktrace) per le eccezioni, i risultati non sono interessati dall'offuscamento.

È possibile fornire esplicitamente gli argomenti facoltativi per esaminare o nascondere le informazioni sul chiamante.

## <a name="member-names"></a>Nomi dei membri

È possibile usare l'attributo [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) per evitare di specificare il nome del membro come argomento `String` per il metodo chiamato. Utilizzando questa tecnica, si evita il problema che il refactoring di ridenominazione non modifica i valori di `String`. Questo vantaggio è particolarmente utile per le attività seguenti:

- Utilizzo della tracciatura e delle routine di diagnostica.
- Implementazione dell'interfaccia [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) durante l'associazione dei dati. Questa interfaccia consente alla proprietà di un oggetto di notificare a un controllo associato la modifica della proprietà stessa in modo che il controllo possa visualizzare le informazioni aggiornate. Senza l'attributo [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) , è necessario specificare il nome della proprietà come valore letterale.

Nel grafico seguente vengono illustrati i nomi dei membri restituiti quando si utilizza l'attributo CallerMemberName.

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
