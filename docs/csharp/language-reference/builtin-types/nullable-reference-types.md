---
title: Tipi di riferimento nullable - Riferimenti in C
description: Informazioni sui tipi di riferimento nullable di C'è e su come usarli
ms.date: 04/06/2020
ms.openlocfilehash: cb61b162b06faa51faabbcdd91e55618cdeaca73
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102697"
---
# <a name="nullable-reference-types-c-reference"></a>Tipi di riferimento nullable (riferimenti per C

> [!NOTE]
> In questo articolo vengono illustrati i tipi di riferimento nullable. È inoltre possibile dichiarare [tipi di valore nullable](nullable-value-types.md).

I tipi di riferimento nullable sono disponibili a partire da C .NET 8.0, nel codice che ha acconsentito esplicitamente a un contesto di *windows.* I tipi di riferimento nullable, gli avvisi di analisi statica null e l'operatore di [perdono null](../operators/null-forgiving.md) sono funzionalità di linguaggio facoltative. Tutti sono disattivati per impostazione predefinita. Un *contesto nullable* viene controllato a livello di progetto usando le impostazioni di compilazione o nel codice usando i pragma.

 In un contesto di riconoscere i valori Null:In a nullable aware context:

- Una variabile di `T` un tipo di riferimento deve essere inizializzata con non `null`null e non può mai essere assegnata un valore che può essere .
- Una variabile di `T?` un tipo di `null` riferimento `null`può essere inizializzata `null` con o assegnata , ma deve essere verificata prima di dereferenziare.
- Una `m` variabile `T?` di tipo viene considerata non null quando si applica l'operatore di perdono null, come in `m!`.

Le distinzioni tra un tipo `T` di riferimento non `T?` nullable e un tipo di riferimento nullable vengono applicate dall'interpretazione del compilatore delle regole precedenti. Una variabile `T` di tipo e `T?` una variabile di tipo sono rappresentate dallo stesso tipo .NET. Nell'esempio seguente viene dichiarata una stringa non nullable e una stringa nullable, quindi viene utilizzato l'operatore di supporto null per assegnare un valore a una stringa non nullable:The following example declares a non-nullable string and a nullable string, and then uses the null-forgiving operator to assign a value to a non-nullable string:

:::code language="csharp" source="snippets/NullableReferenceTypes.cs" id="SnippetCoreSyntax":::

Le `notNull` variabili `nullable` e sono <xref:System.String> entrambe rappresentate dal tipo. Poiché i tipi non nullable e nullable sono entrambi archiviati come lo stesso tipo, esistono diverse posizioni in cui non è consentito l'utilizzo di un tipo di riferimento nullable. In generale, un tipo di riferimento nullable non può essere utilizzato come classe base o interfaccia implementata. Un tipo di riferimento nullable non può essere utilizzato in alcuna espressione di test di tipo o creazione di oggetti. Un tipo di riferimento nullable non può essere il tipo di un'espressione di accesso ai membri. Gli esempi seguenti illustrano questi costrutti:The following examples show these constructs:

```csharp
public MyClass : System.Object? // not allowed
{
}

var nullEmpty = System.String?.Empty; // Not allowed
var maybeObject = new object?(); // Not allowed
try
{
    if (thing is string? nullableString) // not allowed
        Console.WriteLine(nullableString);
} catch (Exception? e) // Not Allowed
{
    Console.WriteLine("error");
}
```

## <a name="nullable-references-and-static-analysis"></a>Riferimenti nullable e analisi statica

Negli esempi della sezione precedente viene illustrata la natura dei tipi di riferimento nullable. I tipi di riferimento nullable non sono nuovi tipi di classe, ma piuttosto annotazioni sui tipi di riferimento esistenti. Il compilatore utilizza tali annotazioni per individuare potenziali errori di riferimento null nel codice. Non esiste alcuna differenza di runtime tra un tipo di riferimento non nullable e un tipo di riferimento nullable. Il compilatore non aggiunge alcun controllo di runtime per i tipi di riferimento non nullable. I vantaggi sono nell'analisi in fase di compilazione. Il compilatore genera avvisi che consentono di individuare e correggere potenziali errori null nel codice. Dichiarare la finalità e il compilatore avvisa quando il codice viola tale finalità.

In un contesto abilitato per i valori Null, il compilatore esegue l'analisi statica su variabili di qualsiasi tipo di riferimento, sia nullable che non nullable. Il compilatore tiene traccia dello stato null di ogni variabile di riferimento come *non null* o *forse null.* Lo stato predefinito di un riferimento non nullable non è *null.* Lo stato predefinito di un riferimento nullable è *forse null*.

I tipi di riferimento non nullable devono essere sempre sicuri per dereferenziare perché il relativo stato null non è *null*. Per applicare tale regola, il compilatore genera avvisi se un tipo di riferimento non nullable non viene inizializzato su un valore non null. Le variabili locali devono essere assegnate nel punto in cui vengono dichiarate. Ogni costruttore deve assegnare ogni campo, nel corpo, un costruttore chiamato o utilizzando un inizializzatore di campo. Il compilatore genera avvisi se un riferimento non nullable viene assegnato a un riferimento il cui stato è *forse null*. Tuttavia, poiché un riferimento non nullable non è *null*, non viene generato alcun avviso quando tali variabili vengono dereferenziati.

I tipi di riferimento nullable `null`possono essere inizializzati o assegnati a . Pertanto, l'analisi statica deve determinare che una variabile non è *null* prima che venga dereferenziata. Se viene determinato che un riferimento nullable è *diverso da null*, non può essere assegnato a una variabile di riferimento non nullable. La classe seguente mostra esempi di questi avvisi:The following class shows examples of these warnings:

:::code language="csharp" source="snippets/NullableReferenceTypes.cs" id="SnippetClassWithNullable":::

Il frammento di codice seguente mostra dove il compilatore genera avvisi quando si usa questa classe:The following snippet shows where the compiler emits warnings when using this class:

:::code language="csharp" source="snippets/NullableReferenceTypes.cs" id="SnippetLocalWarnings":::

Negli esempi precedenti viene illustrata l'analisi statica del compilatore per determinare lo stato null delle variabili di riferimento. Il compilatore applica le regole di linguaggio per i controlli null e le assegnazioni per informare l'analisi.  Il compilatore non è in grado di formulare ipotesi sulla semantica di metodi o proprietà. Se si chiamano metodi che eseguono controlli null, il compilatore non può conoscere tali metodi influiscono sullo stato null di una variabile. Esistono diversi attributi che è possibile aggiungere alle API per informare il compilatore sulla semantica degli argomenti e dei valori restituiti. Questi attributi sono stati applicati a molte API comuni nelle librerie .NET Core.These attributes have been applied to many common APIs in the .NET Core libraries. Ad esempio, <xref:System.String.IsNullOrEmpty%2A> è stato aggiornato e il compilatore interpreta correttamente tale metodo come un controllo null. Per ulteriori informazioni sugli attributi che si applicano all'analisi statica dello stato Null, vedere l'articolo sugli [attributi nullable](../attributes/nullable-analysis.md).

## <a name="setting-the-nullable-context"></a>Impostazione del contesto nullableSetting the nullable context

Esistono due modi per controllare il contesto nullable. A livello di progetto, `<Nullable>enable</Nullable>` è possibile aggiungere l'impostazione del progetto. In un singolo file di origine `#nullable enable` in C, è possibile aggiungere il pragma per abilitare il contesto nullable. Vedere l'articolo sull'impostazione di [una strategia nullable](../../nullable-migration-strategies.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere le seguenti proposte per la specifica del [linguaggio C:](~/_csharplang/spec/introduction.md)

- [Tipi riferimento nullable](~/_csharplang/proposals/csharp-8.0/nullable-reference-types.md)
- [Specifica dei tipi di riferimento nullable Draft nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Tipi valore nullable](nullable-value-types.md)
