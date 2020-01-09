---
title: Operatore await - Riferimenti per C#
ms.date: 11/08/2019
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
ms.openlocfilehash: 6dc058f3850e30d8c424d4372c47b127c7d361b6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712741"
---
# <a name="await-operator-c-reference"></a>Operatore await (Riferimenti per C#)

L'operatore `await` sospende la valutazione del metodo [async](../keywords/async.md) contenitore fino al completamento dell'operazione asincrona rappresentata dal rispettivo operando. Quando l'operazione asincrona viene completata, l'operatore `await` restituisce il risultato dell'operazione, se disponibile. Quando l'operatore `await` viene applicato all'operando che rappresenta l'operazione già completata, restituisce il risultato dell'operazione immediatamente, senza sospensione del metodo contenitore. L'operatore `await` non blocca il thread che valuta il metodo async. Quando l'operatore `await` sospende il metodo asincrono di inclusione, il controllo torna al chiamante del metodo.

Nell'esempio seguente il metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType> restituisce l'istanza `Task<byte[]>`, che rappresenta un'operazione asincrona che produce una matrice di byte quando viene completata. Fino al completamento dell'operazione, l'operatore `await` sospende il metodo `DownloadDocsMainPageAsync`. Quando `DownloadDocsMainPageAsync` viene sospeso, il controllo viene restituito al metodo `Main`, che è il chiamante di `DownloadDocsMainPageAsync`. Il metodo `Main` viene eseguito fino a quando non è necessario il risultato dell'operazione asincrona eseguita dal metodo `DownloadDocsMainPageAsync`. Quando <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> ottiene tutti i byte, viene valutato il resto del metodo `DownloadDocsMainPageAsync`. Successivamente, viene valutato il resto del metodo `Main`.

[!code-csharp[await example](~/samples/csharp/language-reference/operators/AwaitOperator.cs)]

Nell'esempio precedente viene usato il [metodo async `Main`](../../programming-guide/main-and-command-args/index.md), che è possibile a C# partire da 7,1. Per altre informazioni, vedere la sezione [Operatore await nel metodo Main](#await-operator-in-the-main-method).

> [!NOTE]
> Per un'introduzione alla programmazione asincrona, vedere [Programmazione asincrona con async e await](../../programming-guide/concepts/async/index.md). La programmazione asincrona con `async` e `await` segue il [modello asincrono basato su attività](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

È possibile usare l'operatore `await` solo in un metodo, in un'[espressione lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) o in un [metodo anonimo](delegate-operator.md) modificato dalla parola chiave [async](../keywords/async.md). All'interno di un metodo asincrono, non è possibile usare l'operatore `await` nel corpo di una funzione sincrona, all'interno del blocco di un'[istruzione lock](../keywords/lock-statement.md) e in un contesto [unsafe](../keywords/unsafe.md).

L'operando dell'operatore `await` è in genere di uno dei tipi .NET seguenti: <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> o <xref:System.Threading.Tasks.ValueTask%601>. Qualsiasi espressione awaitable, tuttavia, può essere l'operando dell'operatore `await`. Per altre informazioni, vedere la sezione [Espressioni awaitable](~/_csharplang/spec/expressions.md#awaitable-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

A partire C# da 8,0, è possibile usare l'istruzione `await foreach` per utilizzare un flusso di dati asincrono. Per ulteriori informazioni, vedere la sezione relativa ai [flussi asincroni](../../whats-new/csharp-8.md#asynchronous-streams) dell'articolo [novità in C# 8,0](../../whats-new/csharp-8.md) .

Il tipo di espressione `await t` è `TResult` se il tipo di espressione `t` è <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.ValueTask%601>. Se il tipo di `t` è <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.ValueTask>, il tipo di `await t` è `void`. In entrambi i casi, se `t` genera un'eccezione, `await t` genera nuovamente l'eccezione. Per altre informazioni sulla gestione delle eccezioni, vedere la sezione [Eccezioni nei metodi asincroni](../keywords/try-catch.md#exceptions-in-async-methods) dell'articolo [Istruzione try-catch](../keywords/try-catch.md).

Le parole chiave `async` e `await` sono disponibili C# in 5 e versioni successive.

## <a name="await-operator-in-the-main-method"></a>Operatore await nel metodo Main

A partire C# da 7,1, il [Metodo`Main`](../../programming-guide/main-and-command-args/index.md), che è il punto di ingresso dell'applicazione, può restituire `Task` o `Task<int>`, in modo che sia asincrono per poter usare l'operatore `await` nel corpo. Nelle versioni di C# precedenti, per garantire che il metodo `Main` attenda il completamento di un'operazione asincrona, è possibile recuperare il valore della proprietà <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> dell'istanza di <xref:System.Threading.Tasks.Task%601> restituita dal metodo asincrono corrispondente. Per le operazioni asincrone che non producono un valore, è possibile chiamare il metodo <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>. Per informazioni su come selezionare la versione della lingua, vedere [ C# controllo delle versioni della lingua](../configure-language-version.md).

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
- [Esercitazione: generare e utilizzare flussi asincroni utilizzando C# 8,0 e .net core 3,0](../../tutorials/generate-consume-asynchronous-stream.md)
