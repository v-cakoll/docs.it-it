---
title: 'Attributi riservati di C: rilevamento delle informazioni sul chiamante'
ms.date: 04/09/2020
description: Questi attributi indicano al compilatore di generare informazioni sul codice che chiama un membro. Utilizzare CallerFilePath, CallerLineNumber e CallerMemberName per fornire informazioni di traccia dettagliate
ms.openlocfilehash: ee061d4cae35bdcc0b89007e360e94fee8c5f87c
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389877"
---
# <a name="reserved-attributes-determine-caller-information"></a>Attributi riservati: determinare le informazioni sul chiamante

Utilizzando gli attributi info, si ottengono informazioni sul chiamante di un metodo. Ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del membro del chiamante. È possibile ottenere informazioni sul chiamante usando gli attributi applicati ai parametri facoltativi. Ogni parametro facoltativo specifica un valore predefinito. Nella tabella seguente sono elencati gli attributi di informazioni sul chiamante definiti nello spazio dei nomi <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:

|Attributo|Descrizione|Type|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Percorso completo del file di origine contenente il chiamante. Il percorso completo è il percorso in fase di compilazione.|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Numero di riga nel file di origine da cui viene chiamato il metodo.|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Nome di una proprietà o di un metodo del chiamante.|`String`|

Queste informazioni consentono di scrivere l'analisi, il debug e la creazione di strumenti di diagnostica. Nell'esempio seguente viene illustrato come utilizzare gli attributi di informazioni sul chiamante. Per ogni chiamata al metodo `TraceMessage`, le informazioni sul chiamante vengono sostituite come argomenti dei parametri facoltativi.

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [CallerMemberName] string memberName = "",
        [CallerFilePath] string sourceFilePath = "",
        [CallerLineNumber] int sourceLineNumber = 0)
{
    Trace.WriteLine("message: " + message);
    Trace.WriteLine("member name: " + memberName);
    Trace.WriteLine("source file path: " + sourceFilePath);
    Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

Specificare un valore predefinito esplicito per ogni parametro facoltativo. Non è possibile applicare gli attributi di informazioni del chiamante a parametri non specificati come facoltativi. Gli attributi info del chiamante non rendono un parametro facoltativo. ma influiscono sul valore predefinito passato quando l'argomento è omesso. I valori delle informazioni del chiamante vengono generati come valori letterali nel linguaggio intermedio (IL) in fase di compilazione. A differenza dei risultati della proprietà <xref:System.Exception.StackTrace%2A> per le eccezioni, i risultati non sono interessati da offuscamento. È possibile fornire esplicitamente gli argomenti facoltativi per esaminare o nascondere le informazioni sul chiamante.

### <a name="member-names"></a>Nomi dei membri

È possibile utilizzare l'attributo `CallerMemberName` per specificare il nome del membro come argomento `String` al metodo chiamato. Usando questa tecnica, si evita il problema per cui il **refactoring di ridenominazione** non modifica i valori `String`. Questo vantaggio è particolarmente utile per le attività seguenti:

- Utilizzo della tracciatura e delle routine di diagnostica.
- Implementazione dell'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> durante l'associazione dei dati. Questa interfaccia consente alla proprietà di un oggetto di notificare a un controllo associato la modifica della proprietà stessa in modo che il controllo possa visualizzare le informazioni aggiornate. Senza l'attributo `CallerMemberName`, è necessario specificare il nome della proprietà come valore letterale.

Nel grafico seguente vengono mostrati i nomi dei membri restituiti quando si utilizza l'attributo `CallerMemberName`.

|Le chiamate avvengono entro|Nome del membro restituito|
|-|-|
|Metodo, proprietà o evento|Nome del metodo, della proprietà o dell'evento da cui la chiamata ha avuto origine.|
|Costruttore|Stringa ".ctor"|
|Costruttore statico|Stringa ".cctor"|
|Distruttore|Stringa "Finalize"|
|Operatori o conversioni definiti dall'utente|Nome generato per il membro, ad esempio "op_Addition".|
|Costruttore dell'attributo|Nome del metodo o della proprietà cui viene applicato l'attributo. Se l'attributo è un qualsiasi elemento in un membro (ad esempio un parametro, un valore restituito o un parametro di tipo generico), il risultato è il nome del membro associato a tale elemento.|
|Nessun membro contenitore (ad esempio a livello di assembly o attributi applicati a tipi)|Valore predefinito del parametro facoltativo.|

## <a name="see-also"></a>Vedere anche

- [Argomenti denominati e facoltativi](../../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- <xref:System.Reflection>
- <xref:System.Attribute>
- [Attributi](../../../standard/attributes/index.md)
