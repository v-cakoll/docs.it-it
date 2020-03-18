---
title: Concatenamento di attività tramite attività di continuazione
ms.date: 02/11/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, continuations
ms.assetid: 0b45e9a2-de28-46ce-8212-1817280ed42d
ms.openlocfilehash: 7de8c4e44e1866e3df36c666c9ecc210dc6a7d83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159364"
---
# <a name="chaining-tasks-by-using-continuation-tasks"></a>Concatenamento di attività tramite attività di continuazione
Nella programmazione asincrona è comune che, dopo il completamento, un'operazione asincrona chiami una seconda operazione e passi i dati a tale operazione. Tradizionalmente le continuazioni venivano eseguite tramite metodi di callback. In Task Parallel Library la stessa funzionalità viene resa possibile dalle *attività di continuazione*. Un'attivazione di continuazione, chiamata anche semplicemente continuazione, è un'attività asincrona richiamata da un'altra attività, denominata *attività precedente*, al termine di quest'ultima.  
  
 Le continuazioni sono relativamente facili da usare, ma sono comunque potenti e flessibili. Ad esempio, è possibile:  
  
- Passare dati dall'attività precedente alla continuazione.  
  
- Specificare le condizioni esatte in cui la continuazione verrà richiamata o non richiamata.  
  
- Annullare una continuazione prima del suo avvio o cooperativamente durante la sua esecuzione.  
  
- Fornire suggerimenti sul modo in cui pianificare la continuazione.  
  
- Richiamare più continuazioni dalla stessa attività precedente.  
  
- Richiamare una continuazione al termine di tutte o una delle attività precedenti.  
  
- Concatenare continuazioni una dopo l'altra a qualsiasi lunghezza arbitraria.  
  
- Usare una continuazione per gestire le eccezioni generate dall'attività precedente.  
  
## <a name="about-continuations"></a>Informazioni sulle continuazioni  
 Una continuazione è un'attività creata nello stato <xref:System.Threading.Tasks.TaskStatus.WaitingForActivation> . Questa attività viene automaticamente attivata al termine della o delle attività precedenti. Se si chiama <xref:System.Threading.Tasks.Task.Start%2A?displayProperty=nameWithType> in una continuazione nel codice utente, viene generata un'eccezione <xref:System.InvalidOperationException?displayProperty=nameWithType> .  
  
 Una continuazione è essa stessa un oggetto <xref:System.Threading.Tasks.Task> e non blocca il thread su cui viene avviata. Chiamare il metodo <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> per bloccare il thread fino al termine dell'attività di continuazione.  
  
## <a name="creating-a-continuation-for-a-single-antecedent"></a>Creazione di una continuazione per una singola attività precedente  
 Per creare una continuazione che viene eseguita una volta completata l'attività precedente, chiamare il metodo <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> . L'esempio seguente mostra il modello di base. Per chiarezza, viene omessa la gestione delle eccezioni. Viene eseguita un'attività precedente, `taskA`, che restituisce un oggetto <xref:System.DayOfWeek> che indica il nome del giorno corrente della settimana. Al termine dell'attività precedente, all'attività di continuazione `continuation` viene passata l'attività precedente e viene visualizzata una stringa che ne include i risultati.

> [!NOTE]
> Gli esempi C# in questo articolo usano il modificatore `async` nel metodo `Main`. Questa funzionalità è disponibile in C# 7.1 e versioni successive. Le versioni [`CS5001`](../../csharp/misc/cs5001.md) precedenti generano durante la compilazione di questo codice di esempio. È necessario impostare la versione del linguaggio C# su 7.1 o versione successiva. Per istruzioni, vedere l'articolo sulla [configurazione della versione del linguaggio](../../csharp/language-reference/configure-language-version.md).
  
 [!code-csharp[TPL_Continuations#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/simple1.cs#1)]
 [!code-vb[TPL_Continuations#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/simple1.vb#1)]  
  
## <a name="creating-a-continuation-for-multiple-antecedents"></a>Creazione di una continuazione per più attività precedenti  
 È anche possibile creare una continuazione che verrà eseguita al termine di una o tutte le attività di un gruppo di attività. Per eseguire una continuazione al termine di tutte le attività precedenti, chiamare il metodo statico (`Shared` in Visual Basic) <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> o il metodo <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> dell'istanza. Per eseguire una continuazione al termine delle attività precedenti, chiamare il metodo statico (`Shared` in Visual Basic) <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> o il metodo <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A?displayProperty=nameWithType> dell'istanza.  
  
 Si noti che le chiamate agli overload <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> non bloccano il thread chiamante.  Tuttavia, in genere si eseguono chiamate a tutti gli elementi ad eccezione dei metodi <xref:System.Threading.Tasks.Task.WhenAll%28System.Collections.Generic.IEnumerable%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> e  <xref:System.Threading.Tasks.Task.WhenAll%28System.Threading.Tasks.Task%5B%5D%29?displayProperty=nameWithType> per recuperare la proprietà  <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> restituita, che blocca il thread chiamante.  
  
 Nell'esempio seguente viene chiamato il metodo <xref:System.Threading.Tasks.Task.WhenAll%28System.Collections.Generic.IEnumerable%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> per creare un'attività di continuazione che riflette il risultato delle 10 attività precedenti. Ogni attività precedente eleva al quadrato un valore di indice compreso tra uno e 10. Se le attività precedenti vengono completate correttamente (ovvero la relativa proprietà <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> è <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType>), la proprietà <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> della continuazione è una matrice dei valori <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> restituiti da ogni attività precedente. L'esempio somma tali valori per calcolare la somma dei quadrati per tutti i numeri compresi tra uno e 10.  
  
 [!code-csharp[TPL_Continuations#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/whenall1.cs#5)]
 [!code-vb[TPL_Continuations#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/whenall1.vb#5)]  
  
## <a name="continuation-options"></a>Opzioni per le continuazioni  
 Quando si crea un continuazione ad attività singola, è possibile usare un overload <xref:System.Threading.Tasks.Task.ContinueWith%2A> che accetta un valore di enumerazione <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> per specificare le condizioni in cui viene avviata la continuazione. Ad esempio, è possibile specificare che la continuazione venga eseguita solo se l'attività precedente viene completata correttamente o se viene completata con uno stato di errore. Se la condizione non è true quando l'attività precedente è pronta per chiamare la continuazione, questa passa direttamente allo stato <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> e successivamente non può più essere avviata.  
  
 Alcuni metodi di continuazione multiattività, come gli overload del metodo <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> , includono anche un parametro <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> . Tuttavia, è valido solo un subset di tutti i membri dell'enumerazione <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> . È possibile specificare valori <xref:System.Threading.Tasks.TaskContinuationOptions?displayProperty=nameWithType> per cui esistono controparti nell'enumerazione <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=nameWithType> , come <xref:System.Threading.Tasks.TaskContinuationOptions.AttachedToParent?displayProperty=nameWithType>, <xref:System.Threading.Tasks.TaskContinuationOptions.LongRunning?displayProperty=nameWithType>e <xref:System.Threading.Tasks.TaskContinuationOptions.PreferFairness?displayProperty=nameWithType>. Se si specifica una qualsiasi delle opzioni `NotOn` o `OnlyOn` con una continuazione multiattività, viene generata un'eccezione <xref:System.ArgumentOutOfRangeException> in fase di esecuzione.  
  
 Per altre informazioni sulle opzioni per la continuazione delle attività, vedere l'argomento <xref:System.Threading.Tasks.TaskContinuationOptions> .  
  
## <a name="passing-data-to-a-continuation"></a>Passaggio di dati a una continuazione  
 Il metodo <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> passa come argomento un riferimento all'attività precedente al delegato dell'utente della continuazione. Se l'attività precedente è un oggetto <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> e l'attività è stata eseguita fino al suo completamento, la continuazione può accedere alla proprietà <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> dell'attività.  
  
 La proprietà <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> è bloccata fino al completamento dell'attività. Tuttavia, se l'attività è stata annullata o è in errore, il tentativo di accedere alla proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> genera un'eccezione <xref:System.AggregateException> . È possibile evitare questo problema usando l'opzione <xref:System.Threading.Tasks.TaskContinuationOptions.OnlyOnRanToCompletion> , come mostrato nell'esempio seguente.  
  
 [!code-csharp[TPL_Continuations#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/result1.cs#2)]
 [!code-vb[TPL_Continuations#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/result1.vb#2)]  
  
 Se si vuole che la continuazione venga eseguita anche se l'attività precedente non è stata eseguita fino al completamento, è necessario proteggersi dall'eccezione. Un approccio consiste nel testare la proprietà <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> dell'attività precedente e nel tentare di accedere alla proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> solo se lo stato è diverso da <xref:System.Threading.Tasks.TaskStatus.Faulted> o <xref:System.Threading.Tasks.TaskStatus.Canceled>. È anche possibile esaminare la proprietà <xref:System.Threading.Tasks.Task.Exception%2A> dell'attività precedente. Per altre informazioni, vedere [Gestione delle eccezioni](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md). Nell'esempio seguente viene modificato l'esempio precedente in modo da accedere alla proprietà <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> dell'attività precedente solo se lo stato è <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType>.  
  
 [!code-csharp[TPL_Continuations#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/result2.cs#7)]
 [!code-vb[TPL_Continuations#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/result2.vb#7)]  
  
## <a name="canceling-a-continuation"></a>Annullamento di una continuazione  
 La proprietà <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=nameWithType> di una continuazione è impostata su <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> nelle situazioni seguenti:  
  
- Genera un'eccezione <xref:System.OperationCanceledException> in risposta a una richiesta di annullamento. Come per qualsiasi attività, se l'eccezione contiene lo stesso token passato alla continuazione, viene considerato un acknowledgement di annullamento cooperativo.  
  
- Alla continuazione viene passato un oggetto <xref:System.Threading.CancellationToken?displayProperty=nameWithType> la cui proprietà <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> è `true`. In questo caso, la continuazione non viene avviata e passa allo stato <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> .  
  
- La continuazione non viene mai eseguita perché la condizione impostata dal relativo argomento <xref:System.Threading.Tasks.TaskContinuationOptions> non è stata soddisfatta. Ad esempio, se un'attività precedente passa a uno stato <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> , la relativa continuazione a cui è stata passata l'opzione <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnFaulted?displayProperty=nameWithType> non verrà eseguita, ma passerà allo stato <xref:System.Threading.Tasks.TaskStatus.Canceled> .  
  
 Se un'attività e la relativa continuazione rappresentano due parti della stessa operazione logica, è possibile passare lo stesso token di annullamento a entrambe le attività, come mostrato nell'esempio seguente. L'esempio è costituito da un'attività precedente che genera un elenco di numeri interi divisibili per 33, che viene passato alla continuazione. La continuazione visualizza a sua volta l'elenco. L'attività precedente e la continuazione vengono entrambe sospese regolarmente per intervalli casuali. Inoltre, viene usato un oggetto <xref:System.Threading.Timer?displayProperty=nameWithType> per eseguire il metodo `Elapsed` dopo un intervallo di timeout di cinque secondi. Questo esempio chiama il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType>, che fa sì che l'attività attualmente in esecuzione chiami il metodo <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A?displayProperty=nameWithType>. Il fatto che il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> venga chiamato durante l'esecuzione dell'attività precedente o della sua continuazione dipende dalla durata delle pause generate casualmente. Se l'attività precedente viene annullata, la continuazione non verrà avviata. Se l'attività precedente non viene annullata, il token può comunque essere usato per annullare la continuazione.  
  
 [!code-csharp[TPL_Continuations#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/cancellation1.cs#3)]
 [!code-vb[TPL_Continuations#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/cancellation1.vb#3)]  
  
 È anche possibile impedire l'esecuzione di una continuazione se la relativa attività precedente viene annullata senza fornire alla continuazione un token di annullamento, specificando l'opzione <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnCanceled?displayProperty=nameWithType> quando si crea la continuazione. Di seguito è riportato un esempio semplice.  
  
 [!code-csharp[TPL_Continuations#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/cancellation2.cs#8)]
 [!code-vb[TPL_Continuations#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/cancellation2.vb#8)]  
  
 Dopo che una continuazione passa allo stato <xref:System.Threading.Tasks.TaskStatus.Canceled> , può influire sulle continuazioni successive, a seconda degli oggetti <xref:System.Threading.Tasks.TaskContinuationOptions> specificati per tali continuazioni.  
  
 Le continuazioni eliminate non verranno avviate.  
  
## <a name="continuations-and-child-tasks"></a>Continuazioni e attività figlio  
 Una continuazione non viene eseguita fino al completamento dell'attività precedente e di tutte le attività figlio collegate. La continuazione non attende il completamento delle attività figlio scollegate. I due esempi seguenti mostrano attività figlio collegate e scollegate da un'attività precedente che crea una continuazione. Nell'esempio seguente la continuazione viene eseguita solo dopo il completamento di tutte le attività figlio e se l'esempio viene eseguito più volte, produce lo stesso output ogni volta. Nell'esempio viene avviata l'attività precedente chiamando il metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>, perché per impostazione predefinita il metodo <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> crea un'attività padre la cui opzione di creazione di attività predefinita è <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>.  
  
 [!code-csharp[TPL_Continuations#9](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/attached1.cs#9)]
 [!code-vb[TPL_Continuations#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/attached1.vb#9)]  
  
 Se le attività figlio sono scollegate dall'attività precedente, tuttavia, la continuazione viene eseguita non appena termina l'attività precedente, indipendentemente dallo stato delle attività figlio. Di conseguenza, se l'esempio precedente viene eseguito più volte, può produrre output variabile che dipende dal modo in cui il l'utilità di pianificazione delle attività ha gestito ogni singola attività figlio.  
  
 [!code-csharp[TPL_Continuations#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/detached1.cs#10)]
 [!code-vb[TPL_Continuations#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/detached1.vb#10)]  
  
 Lo stato finale dell'attività precedente dipende dallo stato finale di tutte le attività figlio scollegate. Lo stato delle attività figlio scollegate non influisce sull'attività padre. Per altre informazioni, vedere [Attività figlio connesse e disconnesse](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md).  
  
## <a name="associating-state-with-continuations"></a>Associazione dello stato alle continuazioni  
 È possibile associare uno stato arbitrario a una continuazione di attività. Il metodo <xref:System.Threading.Tasks.Task.ContinueWith%2A> fornisce versioni di overload, ciascuna delle quali può accettare un valore <xref:System.Object> che rappresenta lo stato della continuazione. Successivamente, è possibile accedere a questo oggetto stato usando la proprietà <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType> . Questo oggetto stato è `null` se non si specifica un valore.  
  
 Lo stato della continuazione è utile quando si converte codice esistente che usa il [modello di programmazione asincrono (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) per usare TPL. Nel modello APM l'oggetto stato viene specificato in genere nel metodo **Begin**_Metodo_. In seguito è possibile accedere a tale stato usando la proprietà <xref:System.IAsyncResult.AsyncState%2A?displayProperty=nameWithType>. Tramite il metodo <xref:System.Threading.Tasks.Task.ContinueWith%2A> è possibile mantenere questo stato quando si converte il codice che usa il modello APM per usare TPL.  
  
 Lo stato della continuazione può essere utile anche quando si usano oggetti <xref:System.Threading.Tasks.Task> nel debugger di Visual Studio. Ad esempio, nella finestra **Attività in parallelo** la colonna **Attività** mostra la rappresentazione di stringa dell'oggetto stato per ogni attività. Per altre informazioni sulla finestra **Attività in parallelo**, vedere [Uso della finestra Attività](/visualstudio/debugger/using-the-tasks-window).  
  
 L'esempio seguente mostra come usare lo stato della continuazione. Viene creata una catena di attività di continuazione. Ogni attività indica la data e l'ora correnti, tramite un oggetto <xref:System.DateTime> , per il parametro `state` del metodo <xref:System.Threading.Tasks.Task.ContinueWith%2A> . Ogni oggetto <xref:System.DateTime> rappresenta la data e l'ora in cui è stata creata l'attività di continuazione. Ogni attività produce come risultato un secondo oggetto <xref:System.DateTime> che rappresenta la data e l'ora di fine dell'attività. Al termine di tutte le attività, questo esempio visualizza la data e l'ora di creazione e la data e l'ora di fine di ogni attività di continuazione.  
  
 [!code-csharp[TPL_ContinuationState#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuationstate/cs/continuationstate.cs#1)]
 [!code-vb[TPL_ContinuationState#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuationstate/vb/continuationstate.vb#1)]  
  
## <a name="handling-exceptions-thrown-from-continuations"></a>Gestione delle eccezioni generate dalle continuazioni  
 Una relazione tra attività precedenti e attività di continuazione non è una relazione padre-figlio. Le eccezioni generate dalle continuazioni non vengono propagate all'attività precedente. Di conseguenza, gestire le eccezioni generate dalle continuazioni allo stesso modo in cui si gestisce qualsiasi altra attività, nel modo seguente:  
  
- È possibile usare il metodo <xref:System.Threading.Tasks.Task.Wait%2A>, <xref:System.Threading.Tasks.Task.WaitAll%2A>o <xref:System.Threading.Tasks.Task.WaitAny%2A> , o la controparte generica, per restare in attesa della continuazione. È possibile attendere un'attività precedente e la sua continuazione nella stessa istruzione `try`, come mostrato nell'esempio seguente.  
  
     [!code-csharp[TPL_Continuations#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/exception1.cs#6)]
     [!code-vb[TPL_Continuations#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception1.vb#6)]  
  
- È possibile usare una seconda continuazione per osservare la proprietà <xref:System.Threading.Tasks.Task.Exception%2A> della prima continuazione. Nell'esempio seguente un'attività tenta di leggere da un file inesistente. La continuazione visualizza quindi informazioni sull'eccezione nell'attività precedente.  
  
     [!code-csharp[TPL_Continuations#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/exception2.cs#4)]
     [!code-vb[TPL_Continuations#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception2.vb#4)]  
  
     Poiché è stata usata l'opzione <xref:System.Threading.Tasks.TaskContinuationOptions.OnlyOnFaulted?displayProperty=nameWithType> , la continuazione viene eseguita solo se si verifica un'eccezione nell'attività precedente e di conseguenza può presupporre che la proprietà <xref:System.Threading.Tasks.Task.Exception%2A> dell'attività precedente non è `null`. Se la continuazione viene eseguita sia se viene generata un'eccezione nell'attività precedente sia in caso contrario, deve verificare se la proprietà <xref:System.Threading.Tasks.Task.Exception%2A> dell'attività precedente è non `null` prima di tentare di gestire l'eccezione, come mostra il frammento di codice seguente.  
  
     [!code-csharp[TPL_Continuations#11](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_continuations/cs/exception2.cs#11)]
     [!code-vb[TPL_Continuations#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_continuations/vb/exception2.vb#11)]  
  
     Per altre informazioni, vedere [Gestione delle eccezioni](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).  
  
- Se la continuazione è un'attività figlio collegata creata usando l'opzione <xref:System.Threading.Tasks.TaskContinuationOptions.AttachedToParent?displayProperty=nameWithType> , le eccezioni verranno propagate dall'attività padre di nuovo al thread di chiamata, come nel caso di qualsiasi altra attività figlio collegata. Per altre informazioni, vedere [Attività figlio connesse e disconnesse](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md).  
  
## <a name="see-also"></a>Vedere anche

- [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
