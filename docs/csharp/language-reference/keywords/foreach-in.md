---
title: Istruzione foreach in C#
ms.date: 07/22/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 4af431d29e538c1516efeaad3008eaa3b2229ece
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104236"
---
# <a name="foreach-in-c-reference"></a>foreach, in (Riferimenti per C#)

L' `foreach` istruzione esegue un'istruzione o un blocco di istruzioni per ogni elemento in un'istanza del tipo che implementa l' <xref:System.Collections.IEnumerable?displayProperty=nameWithType> <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaccia o, come illustrato nell'esempio seguente:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

L' `foreach` istruzione non è limitata a tali tipi. È possibile usarlo con un'istanza di qualsiasi tipo che soddisfi le condizioni seguenti:

- un tipo ha il metodo pubblico senza parametri il `GetEnumerator` cui tipo restituito è una classe, uno struct o un tipo di interfaccia,
- il tipo restituito del metodo `GetEnumerator` include la proprietà `Current` pubblica e il metodo `MoveNext` pubblico senza parametri con tipo restituito <xref:System.Boolean>.

Nell'esempio seguente viene utilizzata l' `foreach` istruzione con un'istanza del <xref:System.Span%601?displayProperty=nameWithType> tipo, che non implementa alcuna interfaccia:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

A partire da C# 7,3, se la proprietà dell'enumeratore `Current` restituisce un [valore restituito di riferimento](ref.md#reference-return-values) ( `ref T` dove `T` è il tipo di un elemento della raccolta), è possibile dichiarare una variabile di iterazione con il `ref` `ref readonly` modificatore o, come illustrato nell'esempio seguente:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

A partire da C# 8,0, è possibile usare l' `await foreach` istruzione per utilizzare un flusso asincrono di dati, ovvero il tipo di raccolta che implementa l' <xref:System.Collections.Generic.IAsyncEnumerable%601> interfaccia. Ogni iterazione del ciclo può essere sospesa mentre l'elemento successivo viene recuperato in modo asincrono. Nell'esempio seguente viene illustrato come utilizzare l' `await foreach` istruzione:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

Per impostazione predefinita, gli elementi del flusso vengono elaborati nel contesto acquisito. Se si desidera disabilitare l'acquisizione del contesto, utilizzare il <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> metodo di estensione. Per ulteriori informazioni sui contesti di sincronizzazione e sull'acquisizione del contesto corrente, vedere [utilizzo del modello asincrono basato su attività](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md). Per ulteriori informazioni sui flussi asincroni, vedere la sezione relativa ai [flussi asincroni](../../whats-new/csharp-8.md#asynchronous-streams) nell'articolo [novità di C# 8,0](../../whats-new/csharp-8.md) .

In un punto qualsiasi all'interno del blocco dell'istruzione `foreach` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md). È anche possibile uscire `foreach` da un ciclo tramite le istruzioni [goto](goto.md), [return](return.md)o [throw](throw.md) .

Se l'istruzione `foreach` viene applicata a `null`, viene generata una <xref:System.NullReferenceException>. Se la raccolta di origine dell' `foreach` istruzione è vuota, il corpo del `foreach` ciclo non viene eseguito e ignorato.

## <a name="type-of-an-iteration-variable"></a>Tipo di una variabile di iterazione

È possibile usare la `var` parola chiave per consentire al compilatore di dedurre il tipo di una variabile di iterazione nell' `foreach` istruzione, come illustrato nel codice seguente:

```csharp
foreach (var item in collection) { }
```

È anche possibile specificare in modo esplicito il tipo di una variabile di iterazione, come illustrato nel codice seguente:

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

Nel form precedente, il tipo `T` di un elemento della raccolta deve essere convertibile in modo implicito o esplicito nel tipo `V` di una variabile di iterazione. Se una conversione esplicita da `T` a `V` non riesce in fase di esecuzione, l' `foreach` istruzione genera un'eccezione <xref:System.InvalidCastException> . Se, ad esempio, `T` è un tipo di classe non sealed, `V` può essere qualsiasi tipo di interfaccia, anche quello che `T` non implementa. In fase di esecuzione, il tipo di un elemento della raccolta può essere quello che deriva da `T` e implementa effettivamente `V` . In caso contrario, <xref:System.InvalidCastException> viene generata un'eccezione.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [L'istruzione foreach](~/_csharplang/spec/statements.md#the-foreach-statement) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Parole chiave di C#](index.md)
- [Utilizzo di foreach con matrici](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [Istruzione for](for.md)
