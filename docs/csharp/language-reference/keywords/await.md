---
title: await - Riferimenti per C#
ms.custom: seodec18
ms.date: 05/22/2017
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
ms.openlocfilehash: c80d6598540700fdb8559497f10c66726c384519
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239683"
---
# <a name="await-c-reference"></a>await (Riferimenti per C#)
L'operatore `await` viene applicato a un'attività in un metodo asincrono per inserire un punto di sospensione nell'esecuzione del metodo fino al completamento dell'attività di cui si è in attesa. L'attività rappresenta il lavoro attualmente in fase di esecuzione.  
  
È possibile usare `await` solo in un metodo asincrono modificato dalla parola chiave [async](../../../csharp/language-reference/keywords/async.md). Tale metodo, definito usando il modificatore `async` e contenente di solito una o più espressioni `await`, viene denominato *metodo asincrono*.  
  
> [!NOTE]
>  Le parole chiave `async` e `await` sono state introdotte in C# 5. Per un'introduzione alla programmazione asincrona, vedere [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md) (Programmazione asincrona con async e await).  
  
L'attività a cui si applica l'operatore `await` viene in genere restituita da una chiamata a un metodo che implementa il [modello asincrono basato su attività](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md). Sono inclusi i metodi che restituiscono oggetti <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> e `System.Threading.Tasks.ValueType<TResult>`.  

  
 Nell'esempio seguente il metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType> restituisce un oggetto `Task<byte[]>`. L'attività è una promessa di produrre la matrice di byte effettiva una volta completata l'attività. L'operatore <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> sospende l'esecuzione fino al completamento delle operazioni del metodo `await`. Nel frattempo, il controllo viene restituito al chiamante di `GetPageSizeAsync`. Al termine dell'esecuzione dell'attività, l'espressione `await` restituisce una matrice di byte.  

[!code-csharp[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await1.cs)]  

> [!IMPORTANT]
>  Per un esempio completo, vedere [Procedura dettagliata: Accesso al Web con Async e Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). È possibile scaricare l'esempio da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempi di codice per sviluppatori) del sito Web Microsoft. L'esempio è nel progetto AsyncWalkthrough_HttpClient.  
  
Come mostrato nell'esempio precedente, se `await` viene applicato al risultato di una chiamata a un metodo che restituisce un elemento `Task<TResult>`, il tipo dell'espressione `await` è `TResult`. Se `await` viene applicato al risultato di una chiamata a un metodo che restituisce un elemento `Task`, il tipo dell'espressione `await` è `void`. Nell'esempio che segue viene illustrata la differenza.  
  
```csharp  
// await keyword used with a method that returns a Task<TResult>.  
TResult result = await AsyncMethodThatReturnsTaskTResult();  
  
// await keyword used with a method that returns a Task.  
await AsyncMethodThatReturnsTask();  

// await keyword used with a method that returns a ValueTask<TResult>.
TResult result = await AsyncMethodThatReturnsValueTaskTResult();
```  
  
Un'espressione `await` non blocca il thread su cui è in esecuzione. Comporta invece la registrazione, tramite il compilatore, della parte restante del metodo asincrono come continuazione dell'attività di cui si è in attesa. Il controllo quindi viene restituito al chiamante del metodo asincrono. Al termine dell'attività, ne richiama la continuazione e l'esecuzione del metodo asincrono riprende da dove era stata interrotta.  
  
Un'espressione `await` può trovarsi solo nel corpo di un metodo che la contiene, di un'espressione lambda o di un metodo anonimo, che deve essere contrassegnato con un modificatore `async`. Il termine *await* funge da parola chiave solo in tale contesto. Altrove, viene interpretata come identificatore. All'interno del metodo, dell'espressione lambda o del metodo anonimo, un'espressione `await` non può trovarsi nel corpo di una funzione sincrona, in un'espressione di query, nel blocco di un'[istruzione lock](../../../csharp/language-reference/keywords/lock-statement.md) o in un contesto [non sicuro](../../../csharp/language-reference/keywords/unsafe.md).  
  
## <a name="exceptions"></a>Eccezioni  
La maggior parte dei metodi asincroni restituisce <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Le proprietà dell'attività restituita contengono informazioni sullo stato e sulla cronologia, ad esempio se l'attività è stata completata, se il metodo asincrono ha generato un'eccezione o è stato annullato e il risultato finale. L'operatore `await` accede a tali proprietà chiamando i metodi sull'oggetto restituito dal metodo `GetAwaiter`.  
  
Se si è in attesa di un metodo asincrono che restituisce un'attività che genera un'eccezione, l'operatore `await` genera di nuovo l'eccezione.  
  
Se si è in attesa di un metodo asincrono che restituisce un'attività che è stato annullato, tramite l'operatore `await` viene rigenerata un'eccezione <xref:System.OperationCanceledException>.  
  
Una singola attività in uno stato di errore può rispecchiare più eccezioni. Ad esempio, l'attività può essere il risultato di una chiamata a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Quando si attende tale attività, l'operazione await rigenera solo una delle eccezioni. Tuttavia, non è possibile prevedere quale delle eccezioni verrà rigenerata.  
  
Per esempi sulla gestione degli errori nei metodi asincroni, vedere [try-catch](../../../csharp/language-reference/keywords/try-catch.md).  
  
## <a name="example"></a>Esempio  
L'esempio seguente restituisce il numero totale di caratteri nelle pagine di cui gli URL vengono passati come argomenti della riga di comando. L'esempio chiama il metodo `GetPageLengthsAsync`, contrassegnato con la parola chiave `async`. Il metodo `GetPageLengthsAsync` usa a sua volta la parola chiave `await` per attendere le chiamate del metodo <xref:System.Net.Http.HttpClient.GetStringAsync%2A?displayProperty=nameWithType>.  

[!code-csharp[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await2.cs)]  

L'esempio precedente usa C# 7.1, che supporta il [metodo `async` `Main`](../../programming-guide/main-and-command-args/index.md). Poiché le versioni precedenti di C# non supportano i punti di ingresso dell'applicazione che restituiscono <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, non è possibile applicare il modificatore `async` al metodo `Main` e attendere la chiamata del metodo `GetPageLengthsAsync`. In tal caso, è possibile assicurarsi che il metodo `Main` resti in attesa del completamento dell'operazione asincrona recuperando il valore della proprietà <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>. Per le attività che non restituiscono un valore, è possibile chiamare il metodo <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>. Per informazioni su come selezionare la versione del linguaggio, vedere [Selezionare la versione del linguaggio C#](../configure-language-version.md).

## <a name="see-also"></a>Vedere anche  
- [Programmazione asincrona con async e await](../../../csharp/programming-guide/concepts/async/index.md)   
- [Procedura dettagliata: Accesso al Web con Async e Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
- [async](../../../csharp/language-reference/keywords/async.md)
