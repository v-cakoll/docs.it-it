---
title: Tipi restituiti async (C#)
ms.date: 04/14/2020
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
ms.openlocfilehash: 73a6e1924652c8635377547e2faddc864ac5540a
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389129"
---
# <a name="async-return-types-c"></a>Tipi restituiti async (C#)

I metodi asincroni possono avere i seguenti tipi restituiti:

- <xref:System.Threading.Tasks.Task%601>, per un metodo asincrono che restituisce un valore.
- <xref:System.Threading.Tasks.Task>, per un metodo asincrono che esegue un'operazione ma non restituisce alcun valore.
- `void` per un gestore eventi.
- A partire da C# 7.0, qualsiasi tipo con un metodo `GetAwaiter` accessibile. L'oggetto restituito dal metodo `GetAwaiter` deve implementare l'interfaccia <xref:System.Runtime.CompilerServices.ICriticalNotifyCompletion?displayProperty=nameWithType>.
- A partire dalla versione <xref:System.Collections.Generic.IAsyncEnumerable%601>8.0 di C, per un metodo asincrono che restituisce un *flusso asincrono.*

Per altre informazioni sulla funzionalità dei metodi asincroni, vedere [Asynchronous Programming with async and await (C#)](./index.md) (Programmazione asincrona con async e await (C#)).  
  
## <a name="tasktresult-return-type"></a>Tipo restituito  Task\<TResult\>  
Il <xref:System.Threading.Tasks.Task%601> tipo restituito viene utilizzato per un metodo asincrono che contiene un'istruzione [di restituzione](../../../language-reference/keywords/return.md) (C) in cui l'operando è `TResult`.  
  
Nell'esempio seguente il metodo asincrono `GetLeisureHours` contiene un'istruzione `return` che restituisce un valore intero. La dichiarazione del metodo deve quindi specificare un tipo restituito di `Task<int>`.  Il metodo asincrono <xref:System.Threading.Tasks.Task.FromResult%2A> è un segnaposto per un'operazione che restituisce una stringa.
  
:::code language="csharp" source="./snippets/async-returns1.cs" id="SnippetFirstExample":::

Quando `GetLeisureHours` viene chiamato da un'espressione await nel metodo `ShowTodaysInfo`, l'espressione recupera il valore intero (valore di `leisureHours`) archiviato nell'attività restituita dal metodo `GetLeisureHours`. Per altre informazioni sulle espressioni await, vedere [await](../../../language-reference/operators/await.md).  
  
È possibile comprendere `await` meglio come recuperare `Task<T>` il risultato `GetLeisureHours` da un `await`oggetto separando la chiamata a dall'applicazione di , come illustrato nel codice seguente. Una chiamata al metodo `GetLeisureHours` che non viene immediatamente attesa restituisce un tipo `Task<int>`, come ci si aspetterebbe dalla dichiarazione del metodo. Nell'esempio, l'attività viene assegnata alla variabile `integerTask`. Poiché `integerTask` è un <xref:System.Threading.Tasks.Task%601>, contiene una proprietà <xref:System.Threading.Tasks.Task%601.Result> di tipo `TResult`. In questo caso, `TResult` rappresenta un tipo Integer. Quando si applica `await` a `integerTask`, l'espressione await restituisce il contenuto della proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> di `integerTask`. Il valore viene assegnato alla variabile `ret`.  
  
> [!IMPORTANT]
> La proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> è una proprietà di blocco. Se si prova ad accedervi prima del completamento dell'attività, il thread attualmente attivo viene bloccato fino a quando l'attività non viene completata e il valore non è disponibile. Nella maggior parte dei casi, è consigliabile accedere al valore usando `await` invece di accedere direttamente alla proprietà. <br/> Nell'esempio precedente viene recuperato il valore della proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> per bloccare il thread principale in modo che il metodo `ShowTodaysInfo` possa completare l'esecuzione prima del termine dell'applicazione.  

:::code language="csharp" source="./snippets/async-returns1a.cs" id="SnippetSecondVersion":::

## <a name="task-return-type"></a>Tipo restituito Task  
I metodi asincroni che non contengono un'istruzione `return` o che contengono un'istruzione `return` che non restituisce un operando hanno in genere il tipo restituito <xref:System.Threading.Tasks.Task>. Questi metodi restituiscono `void` se eseguiti in modo sincrono. Se si usa un tipo restituito <xref:System.Threading.Tasks.Task> per un metodo asincrono, un metodo chiamante può usare un operatore `await` per sospendere il completamento del chiamante fino a quando il metodo asincrono chiamato non abbia terminato l'operazione.  
  
Nell'esempio seguente il metodo asincrono `WaitAndApologize` non contiene un'istruzione `return`, quindi il metodo restituisce un oggetto <xref:System.Threading.Tasks.Task>. La restituzione di un `Task` consente `WaitAndApologize` di attendere. Il <xref:System.Threading.Tasks.Task> tipo non include `Result` una proprietà perché non ha alcun valore restituito.  

:::code language="csharp" source="./snippets/async-returns2.cs" id="SnippetTaskReturn":::

L'attesa per `WaitAndApologize` viene impostata usando un'istruzione await invece di un'espressione await, in modo simile all'istruzione di chiamata per un metodo sincrono che restituisce void. L'applicazione di un operatore await in questo caso non produce un valore.  
  
Come nell'esempio di <xref:System.Threading.Tasks.Task%601> precedente, è possibile separare la chiamata a `WaitAndApologize` dall'applicazione di un operatore await, come illustrato dal codice seguente. Tuttavia, si noti che un tipo `Task` non ha una proprietà `Result` e che quando viene applicato un operatore await a un tipo `Task` non viene prodotto alcun valore.  
  
Il codice seguente separa la chiamata del metodo `WaitAndApologize` dall'attesa dell'attività restituita dal metodo.  

:::code language="csharp" source="./snippets/async-returns2a.cs" id="SnippetAwaitTask":::

## <a name="void-return-type"></a>Tipo restituito void

Usare il tipo restituito `void` nei gestori eventi asincroni, che richiedono un tipo restituito `void`. Per i metodi diversi dai gestori eventi che non restituiscono un valore, è invece necessario restituire <xref:System.Threading.Tasks.Task>, perché non è possibile impostare l'attesa per un metodo asincrono che restituisce `void`. Qualsiasi chiamante di tale metodo deve continuare fino al completamento senza attendere il completamento del metodo asincrono chiamato. Il chiamante deve essere indipendente da qualsiasi valore o eccezione generata dal metodo asincrono.  
  
Il chiamante di un metodo asincrono che restituisce void non può intercettare le eccezioni generate dal metodo e tali eccezioni non gestite potrebbero causare l'esito negativo dell'applicazione. Se un metodo <xref:System.Threading.Tasks.Task> che <xref:System.Threading.Tasks.Task%601> restituisce un'eccezione o genera un'eccezione, l'eccezione viene archiviata nell'attività restituita. L'eccezione viene generata nuovamente quando l'attività è attesa. Di conseguenza, verificare che qualsiasi metodo asincrono in grado di produrre un'eccezione abbia un tipo restituito <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> e che sia impostata l'attesa per le chiamate al metodo.  
  
Per altre informazioni su come intercettare le eccezioni nei metodi asincroni, vedere la sezione [Eccezioni nei metodi asincroni](../../../language-reference/keywords/try-catch.md#exceptions-in-async-methods) dell'articolo [try-catch.](../../../language-reference/keywords/try-catch.md)  
  
L'esempio seguente mostra il comportamento di un gestore dell'evento asincrono. Nel codice di esempio, un gestore eventi asincrono deve informare il thread principale quando termina. Il thread principale può attendere quindi che un gestore dell'evento asincrono venga completato prima di uscire dal programma.

:::code language="csharp" source="./snippets/async-returns3.cs":::

## <a name="generalized-async-return-types-and-valuetasktresult"></a>Tipi restituiti asincroni generalizzati e ValueTask\<TResult\>

A partire da C# 7.0, un metodo asincrono può restituire qualsiasi tipo con un metodo `GetAwaiter` accessibile.

Dato che <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> sono tipi riferimento, l'allocazione della memoria in percorsi critici per le prestazioni, in particolare quando le allocazioni si verificano in cicli ravvicinati, può influire negativamente sulle prestazioni. Il supporto dei tipi restituiti generalizzati implica la possibilità di restituire un tipo valore leggero anziché un tipo riferimento per evitare allocazioni di memoria aggiuntive.

.NET offre la struttura <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> come implementazione leggera di un valore generalizzato per la restituzione di attività. Per usare il tipo <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType>, è necessario aggiungere il pacchetto NuGet `System.Threading.Tasks.Extensions` al progetto. L'esempio seguente usa la struttura <xref:System.Threading.Tasks.ValueTask%601> per recuperare il valore di due tiri di dadi.
  
:::code language="csharp" source="./snippets/async-valuetask.cs":::

## <a name="async-streams-with-iasyncenumerablet"></a>Flussi asincroni con\<IAsyncEnumerable TAsync streams with IAsyncEnumerable T\>

A partire dalla versione 8.0 di C, un <xref:System.Collections.Generic.IAsyncEnumerable%601>metodo asincrono può restituire un *flusso asincrono,* rappresentato da . Un flusso asincrono fornisce un modo per enumerare gli elementi letti da un flusso quando gli elementi vengono generati in blocchi con chiamate asincrone ripetute. L'esempio seguente mostra un metodo asincrono che genera un flusso asincrono:The following example shows an async method that generates an async stream:

:::code language="csharp" source="./snippets/AsyncStreams.cs" id="SnippetGenerateAsyncStream":::

Nell'esempio precedente vengono lette le righe da una stringa in modo asincrono. Una volta letta ogni riga, il codice enumera ogni parola nella stringa. I chiamanti enumerano `await foreach` ogni parola utilizzando l'istruzione . Il metodo attende quando è necessario leggere in modo asincrono la riga successiva dalla stringa di origine.

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Procedura dettagliata: accesso al Web tramite async e await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Flusso di controllo nei programmi asincroni (c'è)Control Flow in Async Programs (C](./control-flow-in-async-programs.md)
- [async](../../../language-reference/keywords/async.md)
- [Attendono](../../../language-reference/operators/await.md)
