---
title: Implementazione del modello asincrono basato su attività
ms.date: 06/14/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: fab6bd41-91bd-44ad-86f9-d8319988aa78
ms.openlocfilehash: 6218aa1a7b813601e9b718abf862e20a7cbcd313
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73124308"
---
# <a name="implementing-the-task-based-asynchronous-pattern"></a>Implementazione del modello asincrono basato su attività
È possibile implementare il modello asincrono basato su attività (TAP) in i tre modi: con i compilatori C# e Visual Basic in Visual Studio, manualmente oppure con una combinazione dei primi due. Le sezioni seguenti illustrano in dettaglio ogni metodo. È possibile usare il modello TAP per implementare operazioni asincrone di calcolo e di I/O. La sezione [Carichi di lavoro](#workloads) illustra ogni tipo di operazione.

## <a name="generating-tap-methods"></a>Generazione di metodi TAP

### <a name="using-the-compilers"></a>Uso dei compilatori
A partire da .NET Framework 4.5, qualsiasi metodo con la parola chiave `async` (`Async` in Visual Basic) viene considerato un metodo asincrono e i compilatori C# e Visual Basic eseguono le trasformazioni necessarie per implementare il metodo in modo asincrono tramite TAP. Un metodo asincrono deve restituire un oggetto <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>. Nel secondo caso, il corpo della funzione deve restituire un oggetto `TResult` e il compilatore garantisce che il risultato sia reso disponibile tramite l'oggetto attività risultante. Allo stesso modo, viene effettuato il marshalling di qualsiasi eccezione gestita all'interno del corpo del metodo per l'attività di output, per far sì che l'attività risultante termini con lo stato <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType>. L'eccezione si verifica quando un <xref:System.OperationCanceledException> (o tipo derivato) non viene gestito, in qual caso l'attività risultante termina nello stato <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType>.

### <a name="generating-tap-methods-manually"></a>Generazione manuale di metodi TAP
È possibile implementare il modello TAP manualmente per un controllo migliore sull'implementazione. Il compilatore si basa sull'area di superficie esposta dallo spazio dei nomi <xref:System.Threading.Tasks?displayProperty=nameWithType> e i tipi di supporto nello spazio dei nomi <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>. Per implementare autonomamente il modello TAP, creare un oggetto <xref:System.Threading.Tasks.TaskCompletionSource%601>, eseguire l'operazione asincrona e, al completamento, chiamare il metodo <xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult%2A>, <xref:System.Threading.Tasks.TaskCompletionSource%601.SetException%2A> o <xref:System.Threading.Tasks.TaskCompletionSource%601.SetCanceled%2A> oppure la versione `Try` di uno di questi metodi. Quando si implementa un metodo TAP manualmente, è necessario completare l'attività risultante al completamento dell'operazione asincrona rappresentata. Ad esempio:

[!code-csharp[Conceptual.TAP_Patterns#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#1)]
[!code-vb[Conceptual.TAP_Patterns#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#1)]

### <a name="hybrid-approach"></a>Approccio ibrido
 Potrebbe essere utile implementare manualmente il modello TAP, ma delegare la logica di base per l'implementazione al compilatore. Ad esempio, è possibile usare l'approccio ibrido per verificare gli argomenti all'esterno di un metodo asincrono generato dal compilatore, in modo che le eccezioni possano aggirare il metodo chiamante diretto anziché essere esposte tramite l'oggetto <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>:

 [!code-csharp[Conceptual.TAP_Patterns#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#2)]
 [!code-vb[Conceptual.TAP_Patterns#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#2)]

 Un altro caso in cui tale delega è utile si verifica quando si implementa l'ottimizzazione fast-path e si vuole restituire un'attività nella cache.

## <a name="workloads"></a>Carichi di lavoro
È possibile implementare le operazioni asincrone di solo calcolo e associate ai I/O come metodi TAP. Tuttavia, quando i metodi TAP vengono esposti pubblicamente da una libreria, dovrebbero essere forniti solo per i carichi di lavoro che implicano operazioni associate a I/O (che possono anche implicare il calcolo, ma non devono essere puramente di calcolo). Se un metodo è di solo calcolo, deve essere esposto solo come implementazione sincrona. Il codice che lo utilizza può quindi scegliere se eseguire il wrapping di una chiamata di tale metodo sincrono in un'attività per l'offload del lavoro in un altro thread oppure per ottenere parallelismo. Se invece un metodo è di I/O, deve essere esposto solo come implementazione asincrona.

### <a name="compute-bound-tasks"></a>Attività di calcolo
La classe <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> è la soluzione ideale per la rappresentazione di operazioni con calcoli complessi. Per impostazione predefinita, consente di usufruire del supporto speciale all'interno della classe <xref:System.Threading.ThreadPool> per fornire un'esecuzione efficiente e fornisce anche un controllo significativo su quando, dove e come eseguire i calcoli asincroni.

È possibile generare attività di calcolo nei seguenti modi:

- In .NET Framework 4, usare il metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>, che accetta l'esecuzione asincrona di un delegato (di solito <xref:System.Action%601> o <xref:System.Func%601>). Se l'utente fornisce un delegato <xref:System.Action%601>, il metodo restituisce un oggetto <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> che rappresenta l'esecuzione asincrona di tale delegato. Se si fornisce un delegato <xref:System.Func%601>, il metodo restituisce un oggetto <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>. Gli overload del metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> accettano un token di annullamento (<xref:System.Threading.CancellationToken>), opzioni di creazione attività (<xref:System.Threading.Tasks.TaskCreationOptions>) e un'utilità di pianificazione delle attività (<xref:System.Threading.Tasks.TaskScheduler>), tutti i quali offrono un controllo granulare sulla pianificazione e l'esecuzione dell'attività. Un'istanza della factory destinata all'utilità di pianificazione dell'attività corrente è disponibile come proprietà statica (<xref:System.Threading.Tasks.Task.Factory%2A>) della classe <xref:System.Threading.Tasks.Task>; ad esempio: `Task.Factory.StartNew(…)`.

- In .NET Framework 4.5 e versioni successive inclusi .NET Core e .NET Standard, usare il metodo statico <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> come collegamento a <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>. È possibile usare <xref:System.Threading.Tasks.Task.Run%2A> per avviare facilmente un'attività di calcolo destinata al pool di thread. In .NET Framework 4.5 e versioni successive questo è il meccanismo preferenziale per l'avvio di un'attività di calcolo. Usare `StartNew` direttamente solo quando si vuole controllare l'attività in modo più accurato.

- Usare i costruttori del tipo `Task` o del metodo `Start` se si vuol generare e pianificare l'attività separatamente. I metodi pubblici devono restituire solo operazioni già avviate.

- Usare gli overload del metodo <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>. Questo metodo crea una nuova attività pianificata al completamento di un'altra attività. Alcuni degli overload <xref:System.Threading.Tasks.Task.ContinueWith%2A> accettano un token di annullamento, opzioni di continuazione e un'utilità di pianificazione delle attività per un miglior un controllo sulla pianificazione e l'esecuzione dell'attività di continuazione.

- Usare i metodi <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A?displayProperty=nameWithType>. Questi metodi creano una nuova attività pianificata al completamento di tutte o una qualsiasi delle attività di un set fornito. Questi metodi forniscono anche gli overload per controllare la pianificazione e l'esecuzione di queste attività.

Nelle operazioni di calcolo, il sistema può impedire l'esecuzione di un'operazione pianificata se riceve una richiesta di annullamento prima dell'avvio dell'esecuzione dell'attività. In tal caso, se si fornisce un token di annullamento (oggetto <xref:System.Threading.CancellationToken>), è possibile passare tale token al codice asincrono che monitora il token. È anche possibile fornire il token a uno dei metodi indicati in precedenza, ad esempio `StartNew` o `Run` in modo che il runtime `Task` possa monitorare anche il token.

Si consideri ad esempio un metodo asincrono che esegue il rendering di un'immagine. Il corpo dell'attività può eseguire il polling del token di annullamento in modo che il codice esca anticipatamente se arriva una richiesta di annullamento durante il rendering. Inoltre, se arriva la richiesta di annullamento prima dell'inizio del rendering, sarà opportuno evitare l'operazione di rendering:

[!code-csharp[Conceptual.TAP_Patterns#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#3)]
[!code-vb[Conceptual.TAP_Patterns#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#3)]

Le attività di calcolo terminano in uno stato <xref:System.Threading.Tasks.TaskStatus.Canceled> se almeno una delle condizioni seguenti si verifica:

- Una richiesta di annullamento arriva tramite l'oggetto <xref:System.Threading.CancellationToken>, fornito come argomento al metodo di creazione, (ad esempio `StartNew` o `Run`) prima che l'attività passi allo stato <xref:System.Threading.Tasks.TaskStatus.Running>.

- Un'eccezione <xref:System.OperationCanceledException> non viene gestita nel corpo di tale attività, tale eccezione contiene lo stesso oggetto <xref:System.Threading.CancellationToken> passato all'attività e il token indica che viene richiesto l'annullamento.

Se un'altra eccezione non viene gestita nel corpo dell'attività, l'attività termina nello stato <xref:System.Threading.Tasks.TaskStatus.Faulted> e tutti i tentativi di attesa dell'attività o di accesso al risultato causano la generazione di un'eccezione.

### <a name="io-bound-tasks"></a>Attività di I/O
Per creare un'attività che non deve essere supportata direttamente da un thread per l'intera esecuzione, usare il tipo <xref:System.Threading.Tasks.TaskCompletionSource%601>. Questo tipo espone una proprietà <xref:System.Threading.Tasks.TaskCompletionSource%601.Task%2A> che restituisce un'istanza di <xref:System.Threading.Tasks.Task%601> associata. Il ciclo di vita di questa attività viene controllato con i metodi <xref:System.Threading.Tasks.TaskCompletionSource%601> come <xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult%2A>, <xref:System.Threading.Tasks.TaskCompletionSource%601.SetException%2A>, <xref:System.Threading.Tasks.TaskCompletionSource%601.SetCanceled%2A> e relative varianti `TrySet`.

Si supponga di voler creare un'attività che verrà completata dopo un periodo di tempo specificato. Ad esempio, è possibile ritardare un'attività nell'interfaccia utente. La classe <xref:System.Threading.Timer?displayProperty=nameWithType> consente già di richiamare in modo asincrono un delegato dopo un determinato periodo di tempo e usando <xref:System.Threading.Tasks.TaskCompletionSource%601> è possibile inserire un oggetto <xref:System.Threading.Tasks.Task%601> all'inizio del timer, ad esempio:

[!code-csharp[Conceptual.TAP_Patterns#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#4)]
[!code-vb[Conceptual.TAP_Patterns#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#4)]

A partire da .NET Framework 4.5, il metodo <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> viene specificato a questo scopo e può essere usato, ad esempio, in un altro metodo asincrono per implementare un ciclo asincrono di polling:

[!code-csharp[Conceptual.TAP_Patterns#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#5)]
[!code-vb[Conceptual.TAP_Patterns#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#5)]

La classe <xref:System.Threading.Tasks.TaskCompletionSource%601> non ha una controparte non generica. Tuttavia, <xref:System.Threading.Tasks.Task%601> deriva da <xref:System.Threading.Tasks.Task>, quindi è possibile usare l'oggetto generico <xref:System.Threading.Tasks.TaskCompletionSource%601> per i metodi associati a I/O che restituiscono semplicemente un'attività. A questo scopo, è possibile usare un database di origine con oggetto `TResult` fittizio (<xref:System.Boolean> è una scelta ottimale predefinita, ma se si teme che l'utente di <xref:System.Threading.Tasks.Task> ne esegua il downcast in <xref:System.Threading.Tasks.Task%601>, è possibile usare un tipo privato `TResult`). Ad esempio, il metodo `Delay` nell'esempio precedente restituisce l'ora corrente con l'offset risultante (`Task<DateTimeOffset>`). Se tale valore non è necessario, il metodo potrebbe invece essere codificato come segue (notare la modifica del tipo restituito e la modifica dell'argomento in <xref:System.Threading.Tasks.TaskCompletionSource%601.TrySetResult%2A>):

[!code-csharp[Conceptual.TAP_Patterns#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#6)]
[!code-vb[Conceptual.TAP_Patterns#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#6)]

### <a name="mixed-compute-bound-and-io-bound-tasks"></a>Attività miste di calcolo e di I/O
I metodi asincroni non sono limitati solo a operazioni associate a calcolo o I/O, ma possono rappresentare una combinazione di entrambe. Infatti, più operazioni asincrone vengono combinate spesso in operazioni miste di dimensioni maggiori. In un esempio precedente, tramite il metodo `RenderAsync` era stata effettuata un'operazione complessa a livello di calcolo per eseguire il rendering di un'immagine basata su un input `imageData`. Questi `imageData` possono provenire da un servizio Web a cui si accede in modo asincrono:

[!code-csharp[Conceptual.TAP_Patterns#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap_patterns/cs/patterns1.cs#7)]
[!code-vb[Conceptual.TAP_Patterns#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap_patterns/vb/patterns1.vb#7)]

In questo esempio viene illustrato come un unico token di annullamento può essere multithreading con più operazioni asincrone. Per altre informazioni, vedere la sezione relativa all'annullamento in [Utilizzo del modello asincrono basato su attività](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).

## <a name="see-also"></a>Vedere anche

- [Modello asincrono basato su attività (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)
- [Consuming the Task-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)
- [Interoperabilità con altri tipi e modelli asincroni](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
