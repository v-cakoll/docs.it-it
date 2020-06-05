---
title: Istruzione foreach in C#
ms.date: 06/03/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 1645a246c9feee2a92c0d4e4bbeda47f0afde7d9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401888"
---
# <a name="foreach-in-c-reference"></a>foreach, in (Riferimenti per C#)

L'istruzione `foreach` esegue un'istruzione o un blocco di istruzioni per ogni elemento in un'istanza del tipo che implementa l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. L' `foreach` istruzione non è limitata a tali tipi e può essere applicata a un'istanza di qualsiasi tipo che soddisfi le condizioni seguenti:

- include il metodo `GetEnumerator` pubblico senza parametri con tipo restituito classe, struct o interfaccia,
- il tipo restituito del metodo `GetEnumerator` include la proprietà `Current` pubblica e il metodo `MoveNext` pubblico senza parametri con tipo restituito <xref:System.Boolean>.

Nella maggior parte degli usi, `foreach` scorre un' `IEnumerable<T>` espressione in cui ogni elemento è di tipo `T` . Tuttavia, gli elementi possono essere di qualsiasi tipo con una conversione implicita o esplicita dal tipo della `Current` Proprietà. Se la `Current` proprietà restituisce `SomeType` , il tipo degli elementi può essere:

- Qualsiasi classe di base di `SomeType` .
- Qualsiasi interfaccia implementata da `SomeType` .

Inoltre, se `SomeType` è un oggetto `class` o `interface` e Not `sealed` , il tipo di elementi può includere:

- Qualsiasi tipo derivato da `SomeType` .
- Qualsiasi interfaccia arbitraria. Qualsiasi interfaccia è consentita perché qualsiasi interfaccia può essere implementata da una classe derivata da o da implementare `SomeType` .

È possibile dichiarare la variabile di iterazione usando qualsiasi tipo corrispondente alle regole precedenti. Se la conversione da `SomeType` al tipo della variabile di iterazione richiede un cast esplicito, tale operazione può generare un'operazione <xref:System.InvalidCastException> quando la conversione non riesce.

A partire da C# 7,3, se la proprietà dell'enumeratore `Current` restituisce un [valore restituito di riferimento](ref.md#reference-return-values) ( `ref T` dove `T` è il tipo dell'elemento dell'insieme), è possibile dichiarare la variabile di iterazione con il `ref` `ref readonly` modificatore o.

A partire da C# 8,0, l' `await` operatore può essere applicato all' `foreach` istruzione quando il tipo di raccolta implementa l' <xref:System.Collections.Generic.IAsyncEnumerable%601> interfaccia. Ogni iterazione del ciclo può essere sospesa mentre l'elemento successivo viene recuperato in modo asincrono. Per impostazione predefinita, gli elementi del flusso vengono elaborati nel contesto acquisito. Se si desidera disabilitare l'acquisizione del contesto, utilizzare il <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> metodo di estensione. Per ulteriori informazioni sui contesti di sincronizzazione e sull'acquisizione del contesto corrente, vedere l'articolo sull' [utilizzo del modello asincrono basato su attività](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).

In un punto qualsiasi all'interno del blocco dell'istruzione `foreach` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md). È anche possibile uscire `foreach` da un ciclo tramite le istruzioni [goto](goto.md), [return](return.md)o [throw](throw.md) .

Se l'istruzione `foreach` viene applicata a `null`, viene generata una <xref:System.NullReferenceException>. Se la raccolta di origine dell' `foreach` istruzione è vuota, il corpo del `foreach` ciclo non viene eseguito e ignorato.

## <a name="examples"></a>Esempi

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

L'esempio seguente mostra l'utilizzo dell'istruzione `foreach` con un'istanza del tipo <xref:System.Collections.Generic.List%601> che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

L'esempio successivo usa l'istruzione `foreach` con un'istanza del tipo <xref:System.Span%601?displayProperty=nameWithType>, che non implementa alcuna interfaccia:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

L'esempio seguente usa una variabile di iterazione `ref` per impostare il valore di ogni elemento in una matrice di stackalloc. La versione `ref readonly` esegue l'iterazione della raccolta per stampare tutti i valori. La dichiarazione `readonly` usa una dichiarazione di variabile locale implicita. Le dichiarazioni di variabili implicite possono essere usate con le dichiarazioni `ref` o `ref readonly`, così come le dichiarazioni di variabili tipizzate.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

Nell'esempio seguente viene usato `await foreach` per eseguire l'iterazione di una raccolta che genera ogni elemento in modo asincrono:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach"  :::

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [L'istruzione foreach](~/_csharplang/spec/statements.md#the-foreach-statement) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Utilizzo di foreach con matrici](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [Istruzione for](for.md)
