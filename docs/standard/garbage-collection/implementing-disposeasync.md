---
title: Implementare un metodo DisposeAsync
description: ''
ms.date: 06/02/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: c4f541d5a4f5b5fd31b344a299789d86cd78424c
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84311014"
---
# <a name="implement-a-disposeasync-method"></a>Implementare un metodo DisposeAsync

L' <xref:System.IAsyncDisposable?displayProperty=nameWithType> interfaccia è stata introdotta come parte di C# 8,0. Il metodo viene implementato <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> quando è necessario eseguire la pulizia delle risorse, esattamente come si farebbe quando si [implementa un metodo Dispose](implementing-dispose.md). Una delle differenze principali, tuttavia, è che questa implementazione consente operazioni di pulizia asincrona. <xref:System.IAsyncDisposable.DisposeAsync>Restituisce un oggetto <xref:System.Threading.Tasks.ValueTask> che rappresenta l'operazione di eliminazione asincrona.

Generalmente, quando si implementa l' <xref:System.IAsyncDisposable> interfaccia, le classi implementano anche l' <xref:System.IDisposable> interfaccia. Un modello di implementazione valido dell' <xref:System.IAsyncDisposable> interfaccia deve essere preparato per l'eliminazione sincrona o asincrona. Tutte le linee guida per l'implementazione del modello Dispose si applicano all'implementazione asincrona. Questo articolo presuppone che si abbia già familiarità con l' [implementazione di un metodo Dispose](implementing-dispose.md).

## <a name="disposeasync-and-disposeasynccore"></a>DisposeAsync () e DisposeAsyncCore ()

L' <xref:System.IAsyncDisposable> interfaccia dichiara un singolo metodo senza parametri, <xref:System.IAsyncDisposable.DisposeAsync> . Qualsiasi classe non sealed deve avere un `DisposeAsyncCore()` metodo aggiuntivo che restituisca anche un <xref:System.Threading.Tasks.ValueTask> .

- `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> Implementazione senza parametri.
- Un `protected virtual ValueTask DisposeAsyncCore()` Metodo la cui firma è:

```csharp
protected virtual ValueTask DisposeAsyncCore()
{
}
```

Il `DisposeAsyncCore()` metodo è `virtual` in modo che le classi derivate possano definire una pulizia aggiuntiva nelle rispettive sostituzioni.

### <a name="the-disposeasync-method"></a>Metodo DisposeAsync ()

Il `public` `DisposeAsync()` metodo senza parametri viene chiamato in modo implicito in un' `await using` istruzione e il suo scopo è liberare le risorse non gestite, eseguire operazioni di pulizia generali e indicare che il finalizzatore, se presente, non è necessario eseguire. Liberare la memoria associata a un oggetto gestito è sempre il dominio del [Garbage Collector](index.md). Per questo motivo il metodo ha un'implementazione standard:

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of managed resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> Una differenza principale nel modello Dispose asincrono rispetto al modello Dispose è che la chiamata da <xref:System.IAsyncDisposable.DisposeAsync> al metodo di `Dispose(bool)` Overload viene fornita `false` come argomento. Quando si implementa il <xref:System.IDisposable.Dispose?displayProperty=nameWithType> metodo, tuttavia, `true` viene passato. Ciò consente di garantire l'equivalenza funzionale con il modello Dispose sincrono e garantisce inoltre che vengano richiamati i percorsi di codice del finalizzatore. In altre parole, il `DisposeAsyncCore()` metodo eliminerà le risorse gestite in modo asincrono, pertanto non è opportuno eliminarle anche in modo sincrono. Quindi, chiamare `Dispose(false)` anziché `Dispose(true)` .

## <a name="implement-the-async-dispose-pattern"></a>Implementare il modello Dispose asincrono

Tutte le classi non sealed devono essere considerate come una classe di base potenziale, perché potrebbero essere ereditate. Se si implementa il modello di Dispose asincrono per qualsiasi classe di base potenziale, è necessario fornire il `protected virtual ValueTask DisposeAsyncCore()` metodo. Di seguito è riportato un esempio di implementazione del modello Dispose asincrono che usa un oggetto <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> .

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

Nell'esempio precedente è stato usato <xref:System.Text.Json.Utf8JsonWriter> , per altre informazioni su `System.Text.Json` , vedere [eseguire la migrazione da Newtonsoft. JSON a System. Text. JSON](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).

## <a name="using-async-disposable"></a>Uso della funzionalità eliminabile asincrona

Per utilizzare correttamente un oggetto che implementa l' <xref:System.IAsyncDisposable> interfaccia, è possibile utilizzare le parole chiave [await](../../csharp/language-reference/operators/await.md)e [using](../../csharp/language-reference/keywords/using.md) insieme. Si consideri l'esempio seguente, `ExampleAsyncDisposable` in cui viene creata un'istanza della classe e quindi ne viene eseguito il wrapper in un' `await using` istruzione.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> Usare il <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> metodo di estensione dell' <xref:System.IAsyncDisposable> interfaccia per configurare il modo in cui viene eseguito il marshalling della continuazione dell'attività nel contesto o nell'utilità di pianificazione originale. Per altre informazioni su `ConfigureAwait` , vedere [domande frequenti su ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).

Per le situazioni in cui l'utilizzo di `ConfigureAwait` non è necessario, l' `await using` istruzione può essere semplificata come indicato di seguito:

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

Inoltre, può essere scritto per utilizzare l'ambito implicito di una [dichiarazione using](../../csharp/whats-new/csharp-8.md#using-declarations).

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a>Using in pila

Nelle situazioni in cui si creano e si usano più oggetti che implementano <xref:System.IAsyncDisposable> , è possibile che `using` le istruzioni di sovrapposizione in condizioni errate possano impedire chiamate a <xref:System.IAsyncDisposable.DisposeAsync> . Per evitare potenziali problemi, è consigliabile evitare lo stacking e seguire invece questo modello di esempio:

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a>Vedere anche

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
