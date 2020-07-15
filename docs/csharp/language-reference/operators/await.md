---
title: Operatore await - Riferimenti per C#
ms.date: 07/13/2020
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
ms.openlocfilehash: 76c6b24c1cd061585c7a6964d30bc81cc5fc5975
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308845"
---
# <a name="await-operator-c-reference"></a>Operatore await (Riferimenti per C#)

L'operatore `await` sospende la valutazione del metodo [async](../keywords/async.md) contenitore fino al completamento dell'operazione asincrona rappresentata dal rispettivo operando. Quando l'operazione asincrona viene completata, l'operatore `await` restituisce il risultato dell'operazione, se disponibile. Quando l' `await` operatore viene applicato all'operando che rappresenta un'operazione già completata, restituisce immediatamente il risultato dell'operazione senza sospensione del metodo contenitore. L'operatore `await` non blocca il thread che valuta il metodo async. Quando l' `await` operatore sospende il metodo asincrono di inclusione, il controllo torna al chiamante del metodo.

Nell'esempio seguente il metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType> restituisce l'istanza `Task<byte[]>`, che rappresenta un'operazione asincrona che produce una matrice di byte quando viene completata. Fino al completamento dell'operazione, l'operatore `await` sospende il metodo `DownloadDocsMainPageAsync`. Quando `DownloadDocsMainPageAsync` viene sospeso, il controllo viene restituito al metodo `Main`, che è il chiamante di `DownloadDocsMainPageAsync`. Il metodo `Main` viene eseguito fino a quando non è necessario il risultato dell'operazione asincrona eseguita dal metodo `DownloadDocsMainPageAsync`. Quando <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> ottiene tutti i byte, viene valutato il resto del metodo `DownloadDocsMainPageAsync`. Successivamente, viene valutato il resto del metodo `Main`.

[!code-csharp[await example](snippets/AwaitOperator.cs)]

Nell'esempio precedente viene usato [il `Main` metodo asincrono](../../programming-guide/main-and-command-args/index.md), che è possibile a partire da C# 7,1. Per altre informazioni, vedere la sezione [Operatore await nel metodo Main](#await-operator-in-the-main-method).

> [!NOTE]
> Per un'introduzione alla programmazione asincrona, vedere [Programmazione asincrona con async e await](../../programming-guide/concepts/async/index.md). La programmazione asincrona con `async` e `await` segue il [modello asincrono basato su attività](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

È possibile usare l'operatore `await` solo in un metodo, in un'[espressione lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) o in un [metodo anonimo](delegate-operator.md) modificato dalla parola chiave [async](../keywords/async.md). All'interno di un metodo asincrono, non è possibile usare l' `await` operatore nel corpo di una funzione sincrona, all'interno del blocco di un' [istruzione lock](../keywords/lock-statement.md)e in un contesto [unsafe](../keywords/unsafe.md) .

L'operando dell'operatore `await` è in genere di uno dei tipi .NET seguenti: <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> o <xref:System.Threading.Tasks.ValueTask%601>. Qualsiasi espressione awaitable, tuttavia, può essere l'operando dell'operatore `await`. Per altre informazioni, vedere la sezione [Espressioni awaitable](~/_csharplang/spec/expressions.md#awaitable-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

Il tipo di espressione `await t` è `TResult` se il tipo di espressione `t` è <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.ValueTask%601>. Se il tipo di `t` è <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.ValueTask>, il tipo di `await t` è `void`. In entrambi i casi, se `t` genera un'eccezione, `await t` genera nuovamente l'eccezione. Per altre informazioni sulla gestione delle eccezioni, vedere la sezione [Eccezioni nei metodi asincroni](../keywords/try-catch.md#exceptions-in-async-methods) dell'articolo [Istruzione try-catch](../keywords/try-catch.md).

Le `async` `await` parole chiave e sono disponibili in C# 5 e versioni successive.

## <a name="asynchronous-streams-and-disposables"></a>Flussi asincroni e disposable

A partire da C# 8,0, è possibile usare flussi asincroni e disposable.

L'istruzione viene utilizzata `await foreach` per utilizzare un flusso di dati asincrono. Per ulteriori informazioni, vedere l'articolo dell' [ `foreach` istruzione](../keywords/foreach-in.md) e la sezione relativa ai [flussi asincroni](../../whats-new/csharp-8.md#asynchronous-streams) dell'articolo [novità in C# 8,0](../../whats-new/csharp-8.md) .

Usare l' `await using` istruzione per lavorare con un oggetto eliminabile in modo asincrono, ovvero un oggetto di un tipo che implementa un' <xref:System.IAsyncDisposable> interfaccia. Per ulteriori informazioni, vedere la sezione [using Async Disposable](../../../standard/garbage-collection/implementing-disposeasync.md#using-async-disposable) dell'articolo [implementare un metodo DisposeAsync](../../../standard/garbage-collection/implementing-disposeasync.md) .

## <a name="await-operator-in-the-main-method"></a>Operatore await nel metodo Main

A partire da C# 7,1, il [ `Main` Metodo](../../programming-guide/main-and-command-args/index.md), che è il punto di ingresso dell'applicazione, può restituire `Task` o `Task<int>` , consentendo che sia asincrono, in modo da poter usare l' `await` operatore nel corpo. Nelle versioni di C# precedenti, per garantire che il metodo `Main` attenda il completamento di un'operazione asincrona, è possibile recuperare il valore della proprietà <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> dell'istanza di <xref:System.Threading.Tasks.Task%601> restituita dal metodo asincrono corrispondente. Per le operazioni asincrone che non producono un valore, è possibile chiamare il metodo <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>. Per informazioni su come selezionare la versione della lingua, vedere [controllo delle versioni del linguaggio C#](../configure-language-version.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni await](~/_csharplang/spec/expressions.md#await-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Async](../keywords/async.md)
- [Modello di programmazione asincrona attività](../../programming-guide/concepts/async/task-asynchronous-programming-model.md)
- [Programmazione asincrona](../../async.md)
- [La programmazione asincrona in dettaglio](../../../standard/async-in-depth.md)
- [Procedura dettagliata: accesso al Web tramite Async e await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Esercitazione: generare e utilizzare flussi asincroni con C# 8,0 e .NET Core 3,0](../../tutorials/generate-consume-asynchronous-stream.md)
