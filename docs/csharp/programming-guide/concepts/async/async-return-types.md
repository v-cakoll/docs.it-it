---
title: Tipi restituiti async (C#)
description: Informazioni sui tipi restituiti che i metodi asincroni possono avere in C# con esempi di codice per ogni tipo e risorse aggiuntive.
ms.date: 04/14/2020
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
ms.openlocfilehash: 954e449356819595a3a974a6dece5349e53ec88a
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925384"
---
# <a name="async-return-types-c"></a>Tipi restituiti async (C#)

I metodi asincroni possono avere i seguenti tipi restituiti:

- <xref:System.Threading.Tasks.Task%601>, per un metodo asincrono che restituisce un valore.
- <xref:System.Threading.Tasks.Task>, per un metodo asincrono che esegue un'operazione ma non restituisce alcun valore.
- `void` per un gestore eventi.
- A partire da C# 7.0, qualsiasi tipo con un metodo `GetAwaiter` accessibile. L'oggetto restituito dal metodo `GetAwaiter` deve implementare l'interfaccia <xref:System.Runtime.CompilerServices.ICriticalNotifyCompletion?displayProperty=nameWithType>.
- A partire da C# 8,0, <xref:System.Collections.Generic.IAsyncEnumerable%601> , per un metodo asincrono che restituisce un *flusso asincrono*.

Per altre informazioni sulla funzionalità dei metodi asincroni, vedere [Asynchronous Programming with async and await (C#)](./index.md) (Programmazione asincrona con async e await (C#)).  
  
## <a name="tasktresult-return-type"></a>\<TResult\>Tipo restituito dell'attività  
Il <xref:System.Threading.Tasks.Task%601> tipo restituito viene usato per un metodo asincrono che contiene un'istruzione [Return](../../../language-reference/keywords/return.md) (C#) in cui l'operando è `TResult` .  
  
Nell'esempio seguente il metodo asincrono `GetLeisureHours` contiene un'istruzione `return` che restituisce un valore intero. La dichiarazione del metodo deve quindi specificare un tipo restituito di `Task<int>`.  Il metodo asincrono <xref:System.Threading.Tasks.Task.FromResult%2A> è un segnaposto per un'operazione che restituisce una stringa.
  
:::code language="csharp" source="./snippets/async-return-types/async-returns1.cs" id="SnippetFirstExample":::

Quando `GetLeisureHours` viene chiamato da un'espressione await nel metodo `ShowTodaysInfo`, l'espressione recupera il valore intero (valore di `leisureHours`) archiviato nell'attività restituita dal metodo `GetLeisureHours`. Per altre informazioni sulle espressioni await, vedere [await](../../../language-reference/operators/await.md).  
  
È possibile comprendere meglio il modo in cui `await` Recupera il risultato da un oggetto `Task<T>` separando la chiamata a `GetLeisureHours` dall'applicazione di `await` , come illustrato nel codice seguente. Una chiamata al metodo `GetLeisureHours` che non viene immediatamente attesa restituisce un tipo `Task<int>`, come ci si aspetterebbe dalla dichiarazione del metodo. Nell'esempio, l'attività viene assegnata alla variabile `integerTask`. Poiché `integerTask` è un <xref:System.Threading.Tasks.Task%601>, contiene una proprietà <xref:System.Threading.Tasks.Task%601.Result> di tipo `TResult`. In questo caso, `TResult` rappresenta un tipo Integer. Quando si applica `await` a `integerTask`, l'espressione await restituisce il contenuto della proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> di `integerTask`. Il valore viene assegnato alla variabile `ret`.  
  
> [!IMPORTANT]
> La proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> è una proprietà di blocco. Se si prova ad accedervi prima del completamento dell'attività, il thread attualmente attivo viene bloccato fino a quando l'attività non viene completata e il valore non è disponibile. Nella maggior parte dei casi, è consigliabile accedere al valore usando `await` invece di accedere direttamente alla proprietà. <br/> Nell'esempio precedente viene recuperato il valore della proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> per bloccare il thread principale in modo che il metodo `ShowTodaysInfo` possa completare l'esecuzione prima del termine dell'applicazione.  

:::code language="csharp" source="./snippets/async-return-types/async-returns1a.cs" id="SnippetSecondVersion":::

## <a name="task-return-type"></a>Tipo restituito Task  
I metodi asincroni che non contengono un'istruzione `return` o che contengono un'istruzione `return` che non restituisce un operando hanno in genere il tipo restituito <xref:System.Threading.Tasks.Task>. Questi metodi restituiscono `void` se eseguiti in modo sincrono. Se si usa un tipo restituito <xref:System.Threading.Tasks.Task> per un metodo asincrono, un metodo chiamante può usare un operatore `await` per sospendere il completamento del chiamante fino a quando il metodo asincrono chiamato non abbia terminato l'operazione.  
  
Nell'esempio seguente il metodo asincrono `WaitAndApologize` non contiene un'istruzione `return`, quindi il metodo restituisce un oggetto <xref:System.Threading.Tasks.Task>. La restituzione di un oggetto `Task` consente `WaitAndApologize` a di essere atteso. Il <xref:System.Threading.Tasks.Task> tipo non include una `Result` proprietà perché non ha alcun valore restituito.  

:::code language="csharp" source="./snippets/async-return-types/async-returns2.cs" id="SnippetTaskReturn":::

L'attesa per `WaitAndApologize` viene impostata usando un'istruzione await invece di un'espressione await, in modo simile all'istruzione di chiamata per un metodo sincrono che restituisce void. L'applicazione di un operatore await in questo caso non produce un valore.  
  
Come nell'esempio di <xref:System.Threading.Tasks.Task%601> precedente, è possibile separare la chiamata a `WaitAndApologize` dall'applicazione di un operatore await, come illustrato dal codice seguente. Tuttavia, si noti che un tipo `Task` non ha una proprietà `Result` e che quando viene applicato un operatore await a un tipo `Task` non viene prodotto alcun valore.  
  
Il codice seguente separa la chiamata del metodo `WaitAndApologize` dall'attesa dell'attività restituita dal metodo.  

:::code language="csharp" source="./snippets/async-return-types/async-returns2a.cs" id="SnippetAwaitTask":::

## <a name="void-return-type"></a>Tipo restituito void

Usare il tipo restituito `void` nei gestori eventi asincroni, che richiedono un tipo restituito `void`. Per i metodi diversi dai gestori eventi che non restituiscono un valore, è invece necessario restituire <xref:System.Threading.Tasks.Task>, perché non è possibile impostare l'attesa per un metodo asincrono che restituisce `void`. Qualsiasi chiamante di un metodo di questo tipo deve continuare a completare senza attendere il completamento del metodo asincrono chiamato. Il chiamante deve essere indipendente dai valori o dalle eccezioni generate dal metodo asincrono.  
  
Il chiamante di un metodo asincrono che restituisce void non può intercettare le eccezioni generate dal metodo ed è probabile che le eccezioni non gestite provochino un errore dell'applicazione. Se un metodo che restituisce <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> genera un'eccezione, l'eccezione viene archiviata nell'attività restituita. L'eccezione viene generata nuovamente quando l'attività è in attesa. Di conseguenza, verificare che qualsiasi metodo asincrono in grado di produrre un'eccezione abbia un tipo restituito <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> e che sia impostata l'attesa per le chiamate al metodo.  
  
Per altre informazioni su come intercettare le eccezioni nei metodi asincroni, vedere la sezione [Exceptions in async methods](../../../language-reference/keywords/try-catch.md#exceptions-in-async-methods) dell'articolo [try-catch](../../../language-reference/keywords/try-catch.md) .  
  
L'esempio seguente mostra il comportamento di un gestore dell'evento asincrono. Nel codice di esempio, un gestore eventi asincrono deve consentire al thread principale di stabilire quando viene completato. Il thread principale può attendere quindi che un gestore dell'evento asincrono venga completato prima di uscire dal programma.

:::code language="csharp" source="./snippets/async-return-types/async-returns3.cs":::

## <a name="generalized-async-return-types-and-valuetasktresult"></a>Tipi restituiti asincroni generalizzati e ValueTask\<TResult\>

A partire da C# 7.0, un metodo asincrono può restituire qualsiasi tipo con un metodo `GetAwaiter` accessibile.

Dato che <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> sono tipi riferimento, l'allocazione della memoria in percorsi critici per le prestazioni, in particolare quando le allocazioni si verificano in cicli ravvicinati, può influire negativamente sulle prestazioni. Il supporto dei tipi restituiti generalizzati implica la possibilità di restituire un tipo valore leggero anziché un tipo riferimento per evitare allocazioni di memoria aggiuntive.

.NET offre la struttura <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType> come implementazione leggera di un valore generalizzato per la restituzione di attività. Per usare il tipo <xref:System.Threading.Tasks.ValueTask%601?displayProperty=nameWithType>, è necessario aggiungere il pacchetto NuGet `System.Threading.Tasks.Extensions` al progetto. L'esempio seguente usa la struttura <xref:System.Threading.Tasks.ValueTask%601> per recuperare il valore di due tiri di dadi.
  
:::code language="csharp" source="./snippets/async-return-types/async-valuetask.cs":::

## <a name="async-streams-with-iasyncenumerablet"></a>Flussi asincroni con IAsyncEnumerable\<T\>

A partire da C# 8,0, un metodo asincrono può restituire un *flusso asincrono*, rappresentato da <xref:System.Collections.Generic.IAsyncEnumerable%601> . Un flusso asincrono fornisce un modo per enumerare gli elementi letti da un flusso quando gli elementi vengono generati in blocchi con chiamate asincrone ripetute. Nell'esempio seguente viene illustrato un metodo asincrono che genera un flusso asincrono:

:::code language="csharp" source="./snippets/async-return-types/AsyncStreams.cs" id="SnippetGenerateAsyncStream":::

Nell'esempio precedente le righe vengono lette da una stringa in modo asincrono. Una volta letta ogni riga, il codice enumera ogni parola nella stringa. I chiamanti enumerano ogni parola utilizzando l' `await foreach` istruzione. Il metodo attende quando è necessario leggere in modo asincrono la riga successiva dalla stringa di origine.

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Procedura dettagliata: accesso al Web tramite async e await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Flusso di controllo nei programmi asincroni (C#)](./control-flow-in-async-programs.md)
- [Async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
