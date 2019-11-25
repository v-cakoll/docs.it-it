---
title: Operatore await - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/08/2019
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
ms.openlocfilehash: 36cb4a5def6b75281edbe878d89af0c18ab226ec
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140649"
---
# <a name="await-operator-c-reference"></a>Operatore await (Riferimenti per C#)

L'operatore `await` sospende la valutazione del metodo [async](../keywords/async.md) contenitore fino al completamento dell'operazione asincrona rappresentata dal rispettivo operando. Quando l'operazione asincrona viene completata, l'operatore `await` restituisce il risultato dell'operazione, se disponibile. Quando l'operatore `await` viene applicato all'operando che rappresenta l'operazione già completata, restituisce il risultato dell'operazione immediatamente, senza sospensione del metodo contenitore. L'operatore `await` non blocca il thread che valuta il metodo async. When the `await` operator suspends the enclosing async method, the control returns to the caller of the method.

Nell'esempio seguente il metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType> restituisce l'istanza `Task<byte[]>`, che rappresenta un'operazione asincrona che produce una matrice di byte quando viene completata. Fino al completamento dell'operazione, l'operatore `await` sospende il metodo `DownloadDocsMainPageAsync`. Quando `DownloadDocsMainPageAsync` viene sospeso, il controllo viene restituito al metodo `Main`, che è il chiamante di `DownloadDocsMainPageAsync`. Il metodo `Main` viene eseguito fino a quando non è necessario il risultato dell'operazione asincrona eseguita dal metodo `DownloadDocsMainPageAsync`. Quando <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> ottiene tutti i byte, viene valutato il resto del metodo `DownloadDocsMainPageAsync`. Successivamente, viene valutato il resto del metodo `Main`.

[!code-csharp[await example](~/samples/csharp/language-reference/operators/AwaitOperator.cs)]

The preceding example uses the [async `Main` method](../../programming-guide/main-and-command-args/index.md), which is possible beginning with C# 7.1. Per altre informazioni, vedere la sezione [Operatore await nel metodo Main](#await-operator-in-the-main-method).

> [!NOTE]
> Per un'introduzione alla programmazione asincrona, vedere [Programmazione asincrona con async e await](../../programming-guide/concepts/async/index.md). La programmazione asincrona con `async` e `await` segue il [modello asincrono basato su attività](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

È possibile usare l'operatore `await` solo in un metodo, in un'[espressione lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) o in un [metodo anonimo](delegate-operator.md) modificato dalla parola chiave [async](../keywords/async.md). All'interno di un metodo asincrono, non è possibile usare l'operatore `await` nel corpo di una funzione sincrona, all'interno del blocco di un'[istruzione lock](../keywords/lock-statement.md) e in un contesto [unsafe](../keywords/unsafe.md).

L'operando dell'operatore `await` è in genere di uno dei tipi .NET seguenti: <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> o <xref:System.Threading.Tasks.ValueTask%601>. Qualsiasi espressione awaitable, tuttavia, può essere l'operando dell'operatore `await`. Per altre informazioni, vedere la sezione [Espressioni awaitable](~/_csharplang/spec/expressions.md#awaitable-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

Beginning with C# 8.0, you can use the `await foreach` statement to consume an asynchronous stream of data. For more information, see the [Asynchronous streams](../../whats-new/csharp-8.md#asynchronous-streams) section of the [What's new in C# 8.0](../../whats-new/csharp-8.md) article.

Il tipo di espressione `await t` è `TResult` se il tipo di espressione `t` è <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.ValueTask%601>. Se il tipo di `t` è <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.ValueTask>, il tipo di `await t` è `void`. In entrambi i casi, se `t` genera un'eccezione, `await t` genera nuovamente l'eccezione. Per altre informazioni sulla gestione delle eccezioni, vedere la sezione [Eccezioni nei metodi asincroni](../keywords/try-catch.md#exceptions-in-async-methods) dell'articolo [Istruzione try-catch](../keywords/try-catch.md).

The `async` and `await` keywords are available in C# 5 and later.

## <a name="await-operator-in-the-main-method"></a>Operatore await nel metodo Main

Beginning with C# 7.1, the [`Main` method](../../programming-guide/main-and-command-args/index.md), which is the application entry point, can return `Task` or `Task<int>`, enabling it to be async so you can use the `await` operator in its body. Nelle versioni di C# precedenti, per garantire che il metodo `Main` attenda il completamento di un'operazione asincrona, è possibile recuperare il valore della proprietà <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> dell'istanza di <xref:System.Threading.Tasks.Task%601> restituita dal metodo asincrono corrispondente. Per le operazioni asincrone che non producono un valore, è possibile chiamare il metodo <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>. For information about how to select the language version, see [C# language versioning](../configure-language-version.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni await](~/_csharplang/spec/expressions.md#await-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [async](../keywords/async.md)
- [Modello di programmazione asincrona attività](../../programming-guide/concepts/async/task-asynchronous-programming-model.md)
- [Programmazione asincrona](../../async.md)
- [La programmazione asincrona in dettaglio](../../../standard/async-in-depth.md)
- [Procedura dettagliata: accesso al Web con async e await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Tutorial: Generate and consume async streams using C# 8.0 and .NET Core 3.0](../../tutorials/generate-consume-asynchronous-stream.md)
