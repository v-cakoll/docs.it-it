---
title: Programmazione asincrona basata su attività - .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallelism, task
ms.assetid: 458b5e69-5210-45e5-bc44-3888f86abd6f
ms.openlocfilehash: 188a80459fec021dc934597ea2f77ac7b4471b2d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84285287"
---
# <a name="task-based-asynchronous-programming"></a>Programmazione asincrona basata su attività

La libreria Task Parallel Library (TPL) si basa sul concetto di *attività*, che rappresenta un'operazione asincrona. Per certi versi, un'attività è analoga a un thread o a un elemento di lavoro <xref:System.Threading.ThreadPool>, ma a un livello più generale di astrazione. L'espressione *parallelismo delle attività* fa riferimento a una o più attività indipendenti eseguite contemporaneamente. Le attività forniscono due vantaggi principali:

- Utilizzo più efficiente e scalabile delle risorse di sistema.

     Ai fini del funzionamento, le attività vengono accodate a <xref:System.Threading.ThreadPool>, che è stato migliorato con algoritmi che determinano e modificano il numero di thread e che ottimizzano la velocità effettiva grazie al bilanciamento del carico. In questo modo le attività diventano relativamente leggere ed è possibile crearne molte in modo da ottenere un parallelismo accurato.

- Maggior controllo a livello di codice rispetto a quello ottenibile usando un thread o un elemento di lavoro.

     Le attività e il framework in cui esse sono inserite forniscono un ampio set di API che supportano varie funzionalità tra cui attesa, annullamento, continuazioni, gestione affidabile delle eccezioni, stato dettagliato e pianificazione personalizzata.

Per entrambi questi motivi, in .NET Framework TPL rappresenta l'API preferita per la scrittura di codice multithreading, asincrono e parallelo.

## <a name="creating-and-running-tasks-implicitly"></a>Creazione ed esecuzione implicite di attività

Il metodo <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> rappresenta un modo pratico per eseguire simultaneamente un numero qualsiasi di istruzioni arbitrarie. Basta passare un delegato <xref:System.Action> per ogni elemento di lavoro. Il modo più semplice per creare questi delegati è usare le espressioni lambda. L'espressione lambda può chiamare un metodo denominato o fornire il codice inline. Nell'esempio seguente viene mostrata una chiamata a <xref:System.Threading.Tasks.Parallel.Invoke%2A> di base che crea e avvia due attività in esecuzione simultanea. La prima attività è rappresentata da un'espressione lambda che chiama un metodo denominato `DoSomeWork` e la seconda attività è rappresentata da un'espressione lambda che chiama un metodo denominato `DoSomeOtherWork`.

> [!NOTE]
> Questa documentazione usa espressioni lambda per definire delegati in TPL. Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md).

[!code-csharp[TPL#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#21)]
[!code-vb[TPL#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#21)]

> [!NOTE]
> Il numero di istanze <xref:System.Threading.Tasks.Task> create automaticamente da <xref:System.Threading.Tasks.Parallel.Invoke%2A> non è necessariamente uguale al numero dei delegati forniti. La libreria TPL può applicare varie ottimizzazioni, specialmente nel caso di un numero elevato di delegati.

Per altre informazioni, vedere [Procedura: utilizzare Parallel.Invoke per eseguire operazioni in parallelo](how-to-use-parallel-invoke-to-execute-parallel-operations.md).

Per ottenere un controllo maggiore sull'esecuzione delle attività o per restituire un valore dall'attività, è necessario utilizzare in modo più esplicito gli oggetti <xref:System.Threading.Tasks.Task>.

## <a name="creating-and-running-tasks-explicitly"></a>Creazione ed esecuzione esplicite di attività

Un'attività che non restituisce un valore è rappresentata dalla classe <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>. Un'attività che restituisce un valore viene rappresentata dalla classe <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> che eredita da <xref:System.Threading.Tasks.Task>. L'oggetto attività gestisce i dettagli dell'infrastruttura e fornisce metodi e proprietà accessibili dal thread chiamante per tutta la durata dell'attività. Ad esempio, è possibile accedere in qualsiasi momento alla proprietà <xref:System.Threading.Tasks.Task.Status%2A> di un'attività per determinare se è stata avviata, eseguita fino al completamento o annullata oppure se ha generato un'eccezione. Lo stato è rappresentato da un'enumerazione <xref:System.Threading.Tasks.TaskStatus>.

Quando si crea un'attività si assegna ad essa un delegato dell'utente che incapsula il codice che verrà eseguito dall'attività. Il delegato può essere espresso come un delegato denominato, un metodo anonimo o un'espressione lambda. Le espressioni lambda possono contenere una chiamata a un metodo denominato, come mostrato nell'esempio seguente. Si noti che l'esempio include una chiamata al metodo <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> per garantire che l'attività venga completata prima che termini l'applicazione in modalità console.

[!code-csharp[TPL_TaskIntro#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/lambda1.cs#1)]
[!code-vb[TPL_TaskIntro#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/lambda1.vb#1)]

È anche possibile usare i metodi <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> per creare e avviare un'attività in un'unica operazione. Per gestire l'attività, i metodi <xref:System.Threading.Tasks.Task.Run%2A> utilizzano l'utilità di pianificazione delle attività predefinita, indipendentemente dall'utilità di pianificazione associata al thread corrente. I metodi <xref:System.Threading.Tasks.Task.Run%2A> rappresentano il modo preferito per creare e avviare le attività nei casi in cui non occorre un maggiore controllo sulla creazione e la pianificazione di attività.

[!code-csharp[TPL_TaskIntro#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/run1.cs#2)]
[!code-vb[TPL_TaskIntro#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/run1.vb#2)]

È anche possibile usare il metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> per creare e avviare un'attività in un'unica operazione. Usare questo metodo quando non occorre separare la creazione e la pianificazione ed è necessario avvalersi di opzioni aggiuntive di creazione delle attività o usare un'utilità di pianificazione specifica oppure quando si deve passare uno stato aggiuntivo all'attività che è possibile recuperare tramite la proprietà <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType>, come illustrato nell'esempio seguente.

[!code-csharp[TPL_TaskIntro#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/asyncstate.cs#23)]
[!code-vb[TPL_TaskIntro#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/asyncstate.vb#23)]

<xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> espongono ciascuna una proprietà statica <xref:System.Threading.Tasks.Task.Factory%2A> che restituisce un'istanza predefinita per <xref:System.Threading.Tasks.TaskFactory>, in modo che si possa chiamare il metodo come `Task.Factory.StartNew()`. Nell'esempio seguente, inoltre, poiché le attività sono di tipo <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>, ognuna di esse presenta una proprietà <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> pubblica che contiene il risultato del calcolo. Le attività vengono eseguite in modo asincrono e possono essere completate in qualsiasi ordine. Se si accede alla proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> prima che il calcolo venga completato, la proprietà blocca il thread chiamante finché il valore non è disponibile.

[!code-csharp[TPL_TaskIntro#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/result1.cs#4)]
[!code-vb[TPL_TaskIntro#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/result1.vb#4)]

Per altre informazioni, vedere [Procedura: Restituire un valore da un'attività](how-to-return-a-value-from-a-task.md).

Quando si usa un'espressione lambda per creare un delegato, si avrà accesso a tutte le variabili visibili in quel punto del codice sorgente. Tuttavia, in alcuni casi, in particolare all'interno dei cicli, un'espressione lambda non acquisisce la variabile come previsto. Acquisisce solo il valore finale, non il valore mentre viene modificato dopo ogni iterazione. Nell'esempio che segue viene illustrato il problema. Passa un contatore di cicli a un'espressione lambda che crea un'istanza di un oggetto `CustomData` e usa il contatore di cicli come identificatore dell'oggetto. Come indica l'output dell'esempio, ogni oggetto `CustomData` dispone di un identificatore identico.

[!code-csharp[TPL_TaskIntro#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/iteration1b.cs#22)]
[!code-vb[TPL_TaskIntro#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/iteration1b.vb#22)]

È possibile accedere al valore in ogni iterazione fornendo un oggetto stato a un'attività mediante il relativo costruttore. Nell'esempio seguente viene modificato l'esempio precedente usando il contatore di cicli durante la creazione dell'oggetto `CustomData`, che, a sua volta, viene passato all'espressione lambda.  Come indicato dall'output dell'esempio, ogni oggetto `CustomData` dispone ora di un identificatore univoco in base al valore del contatore di cicli al momento della creazione di un'istanza dell'oggetto.

[!code-csharp[TPL_TaskIntro#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/iteration1a.cs#21)]
[!code-vb[TPL_TaskIntro#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/iteration1a.vb#21)]

Questo stato viene passato come argomento al delegato dell'attività ed è accessibile dall'oggetto attività tramite la proprietà <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType>.  L'esempio seguente è una variante dell'esempio precedente Usa la proprietà <xref:System.Threading.Tasks.Task.AsyncState%2A> per visualizzare informazioni sugli oggetti `CustomData` passati all'espressione lambda.

[!code-csharp[TPL_TaskIntro#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/asyncstate.cs#23)]
[!code-vb[TPL_TaskIntro#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/asyncstate.vb#23)]

## <a name="task-id"></a>ID attività

Ogni attività riceve un ID di tipo Integer con cui viene identificata in modo univoco in un dominio applicazione e a cui è possibile accedere tramite la proprietà <xref:System.Threading.Tasks.Task.Id%2A?displayProperty=nameWithType>. Questo ID è utile per visualizzare informazioni sull'attività nelle finestre **Stack in parallelo** e **Attività in parallelo** del debugger di Visual Studio. L'ID viene creato in modo differito, ovvero solo quando viene richiesto. Pertanto, un'attività può presentare un ID diverso ogni volta che viene eseguito il programma. Per altre informazioni su come visualizzare gli ID attività nel debugger, vedere [Uso della finestra Attività](/visualstudio/debugger/using-the-tasks-window) e [Utilizzo della finestra Stack in parallelo](/visualstudio/debugger/using-the-parallel-stacks-window).

## <a name="task-creation-options"></a>Opzioni di creazione delle attività

La maggior parte delle API che creano attività genera overload che accettano un parametro <xref:System.Threading.Tasks.TaskCreationOptions>. Quando si specifica una di queste opzioni si indica all'utilità di pianificazione il modo in cui pianificare l'attività nel pool di thread. Nella tabella seguente sono elencate le varie opzioni di creazione delle attività.

|Valore del parametro <xref:System.Threading.Tasks.TaskCreationOptions>|Descrizione|
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|
|<xref:System.Threading.Tasks.TaskCreationOptions.None>|Valore predefinito quando non si specificano opzioni. L'utilità di pianificazione usa le proprie regole euristiche predefinite per pianificare l'attività.|
|<xref:System.Threading.Tasks.TaskCreationOptions.PreferFairness>|Specifica che l'attività deve essere pianificata in modo che le attività create prima abbiano più possibilità di essere eseguite prima delle attività create in un secondo momento.|
|<xref:System.Threading.Tasks.TaskCreationOptions.LongRunning>|Specifica che l'attività rappresenta un'operazione di lunga durata.|
|<xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>|Specifica che un'attività deve essere creata come figlio collegato dell'attività corrente, se esistente. Per altre informazioni, vedere [Attività figlio connesse e disconnesse](attached-and-detached-child-tasks.md).|
|<xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach>|Specifica che se per un'attività interna è specificata l'opzione `AttachedToParent`, tale attività non diventerà un'attività figlio collegata.|
|<xref:System.Threading.Tasks.TaskCreationOptions.HideScheduler>|Specifica che l'utilità di pianificazione delle attività create chiamando metodi come <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Task%601.ContinueWith%2A?displayProperty=nameWithType> dall'interno di una particolare attività è l'utilità di pianificazione predefinita anziché l'utilità di pianificazione in cui questa attività è in esecuzione.|

Le opzioni possono essere combinate usando un'operazione **OR** bit per bit. Nell'esempio seguente viene illustrata un'attività che presenta le opzioni <xref:System.Threading.Tasks.TaskCreationOptions.LongRunning> e <xref:System.Threading.Tasks.TaskContinuationOptions.PreferFairness>.

[!code-csharp[TPL_TaskIntro#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#03)]
[!code-vb[TPL_TaskIntro#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#03)]

## <a name="tasks-threads-and-culture"></a>Attività, thread e impostazioni cultura

Ogni thread dispone di impostazioni cultura nonché di impostazioni cultura dell'interfaccia utente associate e definite rispettivamente dalle proprietà <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> e <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>. Le impostazioni cultura di un thread vengono usate in operazioni quali formattazione, analisi, ordinamento e confronto di stringhe. Le impostazioni cultura dell'interfaccia utente di un thread vengono usate per la ricerca delle risorse. In genere, a meno che non sia possibile specificare delle impostazioni cultura predefinite per tutti i thread in un dominio applicazione usando le proprietà <xref:System.Globalization.CultureInfo.DefaultThreadCurrentCulture%2A?displayProperty=nameWithType> e <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=nameWithType>, le impostazioni cultura e le impostazioni cultura dell'interfaccia utente predefinite per un thread vengono definite dalle impostazioni cultura del sistema. Se si impostano le impostazioni cultura di un thread in modo esplicito e si avvia un nuovo thread, quest'ultimo non eredita le impostazioni cultura del thread chiamante, al contrario, le relative impostazioni cultura vengono definite da quelle del sistema. Il modello di programmazione basato su attività per le applicazioni destinate alle versioni di .NET Framework precedenti a .NET Framework 4.6 è conforme a questa prassi.

> [!IMPORTANT]
> Si noti che le impostazioni cultura del thread chiamante come parte del contesto di un'attività si applicano alle applicazioni che hanno come *destinazione* .NET Framework 4.6, non applicazioni che vengono *eseguite* in .NET Framework 4.6. È possibile usare una versione specifica di .NET Framework come destinazione quando si crea il progetto in Visual Studio selezionando la versione nell'elenco a discesa nella parte superiore della finestra di dialogo **Nuovo progetto** oppure, esternamente a Visual Studio, è possibile usare l'attributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute>. Per applicazioni destinate a versioni di .NET Framework precedenti a .NET Framework 4.6, o non destinate a una versione specifica di .NET Framework, le impostazioni cultura di un'attività continuano a essere determinate dalle impostazioni cultura del thread in cui sono in esecuzione.

A partire dalle applicazioni destinate a .NET Framework 4.6, le impostazioni cultura del thread chiamante vengono ereditate da ogni attività, anche se l'attività viene eseguita in modo asincrono in un pool di thread.

Nell'esempio seguente viene illustrato questo concetto. Viene usato l'attributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute> per indicare .NET Framework 4.6 come destinazione e vengono modificate le impostazioni cultura correnti dell'applicazione in francese (Francia) o, se francese (Francia) corrisponde già alle impostazioni cultura correnti, inglese (Stati Uniti). Viene quindi richiamato un delegato denominato `formatDelegate` che restituisce alcuni numeri formattati come valori di valuta nelle nuove impostazioni cultura. Si noti che, sia che il delegato venga eseguito come attività in modo sincrono o asincrono, esso restituirà il risultato previsto perché le impostazioni cultura del thread chiamante vengono ereditate dall'attività asincrona.

[!code-csharp[System.Globalization.CultureInfo.Class.Async#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.globalization.cultureinfo.class.async/cs/asyncculture1.cs#5)]
[!code-vb[System.Globalization.CultureInfo.Class.Async#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.globalization.cultureinfo.class.async/vb/asyncculture1.vb#5)]

Se si usa Visual Studio, è possibile omettere l'attributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute> e selezionare invece .NET Framework 4.6 come destinazione quando si crea il progetto nella finestra di dialogo **Nuovo progetto**.

Per ottenere un output che rifletta il comportamento delle app che hanno come destinazione versioni di .NET Framework precedenti a .NET Framework 4.6, rimuovere l'attributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute> dal codice sorgente. L'output rifletterà le convenzioni di formattazione delle impostazioni cultura di sistema predefinite e non di quelle del thread chiamante.

Per altre informazioni sulle attività asincrone e sulle impostazioni cultura, vedere la sezione dedicata alle impostazioni cultura e alle operazioni asincrone basate sulle attività nell'argomento dedicato alla classe <xref:System.Globalization.CultureInfo>.

## <a name="creating-task-continuations"></a>Creazione delle continuazioni di attività

I metodi <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task%601.ContinueWith%2A?displayProperty=nameWithType> consentono di specificare un'attività da avviare al termine dell'*attività precedente*. Al delegato dell'attività di continuazione viene passato un riferimento all'attività precedente in modo da poter esaminare lo stato dell'attività precedente e, recuperando il valore della proprietà <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>, usare l'output dell'attività precedente come input per la continuazione.

Nell'esempio seguente l'attività `getData` viene avviata da una chiamata al metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%60%601%28System.Func%7B%60%600%7D%29?displayProperty=nameWithType>. L'attività `processData` viene avviata automaticamente quando termina `getData` e `displayData` viene avviata quando termina `processData`. `getData` produce una matrice di tipo Integer accessibile da parte dell'attività `processData` tramite la proprietà `getData` dell'attività <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>. L'attività `processData` elabora la matrice e restituisce un risultato il cui tipo è dedotto dal tipo restituito dell'espressione lambda passata al metodo <xref:System.Threading.Tasks.Task%601.ContinueWith%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%600%7D%2C%60%600%7D%29?displayProperty=nameWithType>. L'attività `displayData` viene eseguita automaticamente quando termina `processData` e l'oggetto <xref:System.Tuple%603> restituito dall'espressione lambda `processData` è accessibile da parte dell'attività `displayData` tramite la proprietà `processData` dell'attività <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>. L'attività `displayData` accetta i risultati dell'attività `processData` e produce un risultato il cui tipo viene dedotto in modo simile e che viene reso disponibile al programma nella proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>.

[!code-csharp[TPL_TaskIntro#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/continuations1.cs#5)]
[!code-vb[TPL_TaskIntro#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/continuations1.vb#5)]

Poiché <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> è un metodo di istanza, è possibile concatenare le chiamate al metodo anziché creare un'istanza di un oggetto <xref:System.Threading.Tasks.Task%601> per ogni attività precedente. Dal punto di vista funzionale, il seguente esempio è identico al precedente, eccetto per il fatto che unisce in una catena le chiamate al metodo <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>. Si noti che l'oggetto <xref:System.Threading.Tasks.Task%601> restituito dalla catena di chiamate al metodo è l'attività di continuazione finale.

[!code-csharp[TPL_TaskIntro#24](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/continuations2.cs#24)]
[!code-vb[TPL_TaskIntro#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/continuations2.vb#24)]

I metodi <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A> e <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> consentono di continuare da più attività.

Per altre informazioni, vedere [Concatenamento di attività tramite attività di continuazione](chaining-tasks-by-using-continuation-tasks.md).

## <a name="creating-detached-child-tasks"></a>Creazione di attività figlio scollegate

Quando il codice utente in esecuzione in un'attività crea una nuova attività e non specifica l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>, la nuova attività non viene sincronizzata con l'attività padre in alcun modo particolare. Questo tipo di attività non sincronizzata è definito *attività annidata scollegata* o *attività figlio scollegata*. Nell'esempio seguente viene mostrata un'attività che crea un'unica attività figlio scollegata.

[!code-csharp[TPL_TaskIntro#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#07)]
[!code-vb[TPL_TaskIntro#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#07)]

Si noti che l'attività padre non attende il completamento dell'attività figlio scollegata.

## <a name="creating-child-tasks"></a>Creazione di attività figlio

Quando il codice utente in esecuzione in un'attività crea un'attività con l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>, la nuova attività è detta *attività figlio collegata* dell'attività padre. È possibile usare l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> per esprimere il parallelismo fra attività strutturato, poiché l'attività padre attende in modo implicito il completamento di tutte le attività figlio collegate. Nell'esempio seguente viene mostrata un'attività padre che crea dieci attività figlio collegate. Si noti che anche se nell'esempio viene chiamato il metodo <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> per attendere il completamento dell'attività padre, non si deve esplicitamente attendere il completamento delle attività figlio collegate.

[!code-csharp[TPL_TaskIntro#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/child1.cs#8)]
[!code-vb[TPL_TaskIntro#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/child1.vb#8)]

Un'attività padre può usare l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> per impedire che altre attività vengano collegate all'attività padre. Per altre informazioni, vedere [Attività figlio connesse e disconnesse](attached-and-detached-child-tasks.md).

## <a name="waiting-for-tasks-to-finish"></a>Attesa del completamento delle attività

I tipi <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> forniscono vari overload dei metodi <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> che consentono di attendere il completamento di un'attività. Sono inoltre disponibili overload dei metodi statici <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> che consentono di attendere il completamento di alcune o di tutte le attività di una matrice.

L'attesa del completamento di un'attività è in genere dovuta a uno dei motivi seguenti:

- Il thread principale dipende dal risultato finale calcolato da un'attività.

- È necessario gestire le eccezioni eventualmente generate dall'attività.

- L'applicazione può terminare prima del completamento di tutte le attività. Ad esempio, le applicazioni di console termineranno dopo l'esecuzione di tutto il codice sincrono in `Main` (il punto di ingresso dell'applicazione).

Nell'esempio seguente viene mostrato il modello di base che non prevede la gestione delle eccezioni.

[!code-csharp[TPL_TaskIntro#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#06)]
[!code-vb[TPL_TaskIntro#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#06)]

Per un esempio che illustra la gestione delle eccezioni, vedere [Gestione delle eccezioni](exception-handling-task-parallel-library.md).

Alcuni overload consentono di specificare un timeout mentre altri accettano un oggetto <xref:System.Threading.CancellationToken> aggiuntivo come parametro di input, in modo che l'attesa stessa possa essere annullata a livello di codice o in risposta a un input dell'utente.

Quando si resta in attesa di un'attività, si attendono in modo implicito tutti i figli di tale attività creati tramite l'opzione <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType>. L'oggetto <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> restituisce immediatamente un valore se l'attività è già stata completata. Qualsiasi eccezione generata da un'attività verrà generata da un metodo <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, anche se il metodo <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> è stato chiamato dopo il completamento dell'attività.

## <a name="composing-tasks"></a>Composizione di attività

Le classi <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> forniscono numerosi metodi che possono agevolare la composizione di più attività per l'implementazione di modelli comuni e usare meglio le funzionalità di linguaggio asincrone fornite da C#, Visual Basic e F#. In questa sezione vengono descritti i metodi <xref:System.Threading.Tasks.Task.WhenAll%2A>, <xref:System.Threading.Tasks.Task.WhenAny%2A>, <xref:System.Threading.Tasks.Task.Delay%2A> e <xref:System.Threading.Tasks.Task.FromResult%2A>.

### <a name="taskwhenall"></a>Task.WhenAll

Il metodo <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> attende in modo asincrono che terminino più oggetti <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Fornisce le versioni di overload che consentono di attendere i set di attività non uniformi. Ad esempio, è possibile attendere il completamento di più oggetti <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> da una chiamata al metodo.

### <a name="taskwhenany"></a>Task.WhenAny

Il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> attende in modo asincrono che termini uno degli oggetti <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Come nel metodo <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>, questo metodo fornisce le versioni di overload che consentono di attendere i set di attività non uniformi. Il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> è particolarmente utile nei seguenti scenari.

- Operazioni ridondanti. Si consideri un algoritmo o un'operazione eseguibile in molti modi. È possibile usare il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> per selezionare l'operazione che termina per prima e quindi annullare le operazioni rimanenti.

- Operazioni interfogliate. È possibile avviare più operazioni, le quali devono tutte essere completate e usare il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> per elaborare i risultati al termine di ogni operazione. Al termine di un'operazione, è possibile avviare una o più attività aggiuntive.

- Operazioni con limitazione. È possibile usare il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> per estendere lo scenario precedente limitando il numero di operazioni simultanee.

- Operazioni scadute. È possibile usare il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A> per scegliere tra una o più attività e un'attività che termina dopo un periodo specifico, ad esempio un'attività restituita dal metodo <xref:System.Threading.Tasks.Task.Delay%2A>. Il metodo <xref:System.Threading.Tasks.Task.Delay%2A> è descritto nella sezione che segue.

### <a name="taskdelay"></a>Task.Delay

Il metodo <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> produce un oggetto <xref:System.Threading.Tasks.Task> che viene completato allo scadere del tempo specificato. È possibile usare questo metodo per creare cicli che occasionalmente eseguono il polling dei dati, introducono timeout, ritardano la gestione dell'input utente per un tempo predeterminato e così via.

### <a name="tasktfromresult"></a>Task(T).FromResult

Tramite il metodo <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType>, è possibile creare un oggetto <xref:System.Threading.Tasks.Task%601> contenente un risultato precedentemente calcolato. Questo metodo è utile quando si esegue un'operazione asincrona che restituisce un oggetto <xref:System.Threading.Tasks.Task%601> e il risultato di tale oggetto <xref:System.Threading.Tasks.Task%601> è già calcolato. Per un esempio che usa <xref:System.Threading.Tasks.Task.FromResult%2A> per recuperare i risultati delle operazioni di download asincrone contenuti in una cache, vedere [Procedura: Creare attività precalcolate](how-to-create-pre-computed-tasks.md).

## <a name="handling-exceptions-in-tasks"></a>Gestione delle eccezioni nelle attività

Quando un'attività genera una o più eccezioni, il sistema esegue il wrapping di queste ultime in un'eccezione <xref:System.AggregateException>. Tale eccezione viene ripropagata al thread che si unisce all'attività, ovvero in genere il thread che resta in attesa del completamento dell'attività o che accede alla proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>. Questo comportamento serve a imporre i criteri di .NET Framework secondo cui tutte le eccezioni non gestite devono comportare per impostazione predefinita la terminazione del processo. Il codice che effettua la chiamata può gestire le eccezioni usando uno qualsiasi degli elementi seguenti in un blocco `try`/`catch`:

- Metodo <xref:System.Threading.Tasks.Task.Wait%2A>

- Metodo <xref:System.Threading.Tasks.Task.WaitAll%2A>

- Metodo <xref:System.Threading.Tasks.Task.WaitAny%2A>

- Proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>

Anche il thread di unione può gestire le eccezioni. A tale scopo, deve accedere alla proprietà <xref:System.Threading.Tasks.Task.Exception%2A> prima che l'attività venga raccolta nel Garbage Collector. L'accesso a questa proprietà impedisce all'eccezione non gestita di attivare il comportamento di propagazione delle eccezioni che termina il processo quando l'oggetto viene finalizzato.

Per ulteriori informazioni sulle eccezioni e sulle attività, vedere [Gestione delle eccezioni](exception-handling-task-parallel-library.md).

## <a name="canceling-tasks"></a>Annullamento delle attività

La classe <xref:System.Threading.Tasks.Task> supporta l'annullamento cooperativo ed è completamente integrata con le classi <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> e <xref:System.Threading.CancellationToken?displayProperty=nameWithType>, che sono state introdotte in .NET Framework 4. Molti dei costruttori nella classe <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> accettano un oggetto <xref:System.Threading.CancellationToken> come parametro di input. Molti degli overload <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> e <xref:System.Threading.Tasks.Task.Run%2A> includono anche un parametro <xref:System.Threading.CancellationToken>.

È possibile creare il token e inviare la richiesta di annullamento in un secondo momento tramite la classe <xref:System.Threading.CancellationTokenSource>. Passare il token a <xref:System.Threading.Tasks.Task> come argomento. Inoltre, fare riferimento allo stesso token nel delegato dell'utente, che esegue le operazioni necessarie per rispondere a una richiesta di annullamento.

Per altre informazioni, vedere [Annullamento delle attività](task-cancellation.md) e [Procedura: Annullare un'attività e i relativi figli](how-to-cancel-a-task-and-its-children.md).

## <a name="the-taskfactory-class"></a>Classe TaskFactory

La classe <xref:System.Threading.Tasks.TaskFactory> fornisce metodi statici che incapsulano alcuni modelli comuni per la creazione e l'avvio di attività e di attività di continuazione.

- Il modello più comune è <xref:System.Threading.Tasks.TaskFactory.StartNew%2A>, che crea e avvia un'attività in un'unica istruzione.

- Quando si creano attività di continuazione da più attività precedenti, usare il metodo <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A> o <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> oppure i relativi equivalenti nella classe <xref:System.Threading.Tasks.Task%601>. Per altre informazioni, vedere [Concatenamento di attività tramite attività di continuazione](chaining-tasks-by-using-continuation-tasks.md).

- Per incapsulare i metodi `BeginX` ed `EndX` del modello di programmazione asincrono in un'istanza di <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, utilizzare i metodi <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A>. Per altre informazioni, vedere [Task Parallel Library e programmazione asincrona .NET Framework tradizionale](tpl-and-traditional-async-programming.md).

L'oggetto <xref:System.Threading.Tasks.TaskFactory> predefinito è accessibile come proprietà statica della classe <xref:System.Threading.Tasks.Task> o della classe <xref:System.Threading.Tasks.Task%601>. È anche possibile creare direttamente un'istanza di <xref:System.Threading.Tasks.TaskFactory> e specificare varie opzioni che includono un oggetto <xref:System.Threading.CancellationToken>, un'opzione <xref:System.Threading.Tasks.TaskCreationOptions>, un'opzione <xref:System.Threading.Tasks.TaskContinuationOptions> o un oggetto <xref:System.Threading.Tasks.TaskScheduler>. Tutte le opzioni specificate quando si crea la factory delle attività verranno applicate a tutte le attività create da tale factory, tranne nel caso in cui l'oggetto <xref:System.Threading.Tasks.Task> venga creato tramite l'enumerazione <xref:System.Threading.Tasks.TaskCreationOptions>. In tal caso, le opzioni dell'attività eseguono l'override di quelle della factory delle attività.

## <a name="tasks-without-delegates"></a>Attività senza delegati

In alcuni casi è necessario usare un oggetto <xref:System.Threading.Tasks.Task> per incapsulare un'operazione asincrona eseguita da un componente esterno anziché dal delegato dell'utente. Se l'operazione si basa sul modello Begin/End del modello di programmazione asincrona, è possibile usare i metodi <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A>. In caso contrario, è possibile usare l'oggetto <xref:System.Threading.Tasks.TaskCompletionSource%601> per eseguire il wrapping dell'operazione in un'attività e in questo modo ottenere alcuni dei vantaggi della programmabilità di <xref:System.Threading.Tasks.Task>, ad esempio il supporto per la propagazione delle eccezioni e le continuazioni. Per altre informazioni, vedere <xref:System.Threading.Tasks.TaskCompletionSource%601>.

## <a name="custom-schedulers"></a>Utilità di pianificazione personalizzate

Per la maggior parte degli sviluppatori di applicazioni o librerie non occorre determinare il processore in cui è in esecuzione l'attività né come quest'ultima sincronizza il proprio lavoro con le altre attività o come viene pianificata in <xref:System.Threading.ThreadPool?displayProperty=nameWithType>. Tali sviluppatori richiedono soltanto che l'attività venga eseguita con la maggiore efficienza possibile nel computer host. Se si richiede un controllo più accurato sui dettagli di pianificazione, la libreria Task Parallel Library (TPL) consente di configurare alcune impostazioni nell'utilità di pianificazione delle attività predefinita. Inoltre, tale libreria consente persino di fornire un'utilità di pianificazione personalizzata. Per altre informazioni, vedere <xref:System.Threading.Tasks.TaskScheduler>.

## <a name="related-data-structures"></a>Strutture di dati correlate

La libreria TPL presenta vari nuovi tipi pubblici che risultano utili sia negli scenari in parallelo sia in quelli sequenziali. Fra questi sono incluse varie classi di raccolte thread-safe, veloci e scalabili nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType> nonché molti nuovi tipi di sincronizzazione, ad esempio <xref:System.Threading.Semaphore?displayProperty=nameWithType> e <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> che sono più efficienti dei relativi predecessori per tipi specifici di carichi di lavoro. Altri nuovi tipi di .NET Framework 4, ad esempio <xref:System.Threading.Barrier?displayProperty=nameWithType> e <xref:System.Threading.SpinLock?displayProperty=nameWithType>, forniscono funzionalità non disponibili nelle versioni precedenti. Per ulteriori informazioni, vedere [Strutture di dati per la programmazione in parallelo](data-structures-for-parallel-programming.md).

## <a name="custom-task-types"></a>Tipi di attività personalizzati

È consigliabile non ereditare da <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>. È invece consigliabile usare la proprietà <xref:System.Threading.Tasks.Task.AsyncState%2A> per associare i dati o lo stato aggiuntivi a un oggetto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. È anche possibile usare i metodi di estensione per estendere la funzionalità delle classi <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601>. Per altre informazioni sui metodi di estensione, vedere [Metodi di estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md) e [Metodi di estensione](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).

Se è necessario ereditare da <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> , non è possibile usare o <xref:System.Threading.Tasks.Task.Run%2A> le <xref:System.Threading.Tasks.TaskFactory?displayProperty=nameWithType> classi, o <xref:System.Threading.Tasks.TaskFactory%601?displayProperty=nameWithType> <xref:System.Threading.Tasks.TaskCompletionSource%601?displayProperty=nameWithType> per creare istanze del tipo di attività personalizzato perché questi meccanismi creano solo <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601> oggetti e. Non è inoltre possibile utilizzare i meccanismi di continuazione dell'attività forniti da <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601><xref:System.Threading.Tasks.TaskFactory> e <xref:System.Threading.Tasks.TaskFactory%601> per creare istanze del tipo di attività personalizzato poiché anche questi meccanismi creano solo oggetti <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601>.

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-|-|
|[Concatenamento di attività tramite attività di continuazione](chaining-tasks-by-using-continuation-tasks.md)|Viene descritto il funzionamento delle continuazioni.|
|[Attività figlio connesse e disconnesse](attached-and-detached-child-tasks.md)|Viene descritta la differenza tra attività figlio collegate e scollegate.|
|[Annullamento delle attività](task-cancellation.md)|Viene descritto il supporto dell'annullamento, incorporato nell'oggetto <xref:System.Threading.Tasks.Task>.|
|[Gestione delle eccezioni](exception-handling-task-parallel-library.md)|Viene descritto come vengono gestite le eccezioni su thread simultanei.|
|[Procedura: utilizzare Parallel. Invoke per eseguire operazioni in parallelo](how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Viene descritto come usare <xref:System.Threading.Tasks.Parallel.Invoke%2A>.|
|[Procedura: Restituire un valore da un'attività](how-to-return-a-value-from-a-task.md)|Viene descritto come restituire valori dalle attività.|
|[Procedura: Annullare un'attività e i relativi figli](how-to-cancel-a-task-and-its-children.md)|Viene descritto come annullare le attività.|
|[Procedura: creare attività precalcolate](how-to-create-pre-computed-tasks.md)|Viene descritto come utilizzare il metodo <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> per recuperare i risultati delle operazioni di download asincrone contenuti in una cache.|
|[Procedura: Attraversare un albero binario con attività parallele](how-to-traverse-a-binary-tree-with-parallel-tasks.md)|Viene descritto come usare le attività per attraversare un albero binario.|
|[Procedura: Annullare il wrapping di un'attività annidata](how-to-unwrap-a-nested-task.md)|Viene illustrato come usare il metodo di estensione <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>.|
|[Parallelismo dei dati](data-parallelism-task-parallel-library.md)|Viene descritto come utilizzare <xref:System.Threading.Tasks.Parallel.For%2A> e <xref:System.Threading.Tasks.Parallel.ForEach%2A> per creare cicli paralleli su dati.|
|[Programmazione parallela](index.md)|Nodo di livello principale per la programmazione parallela di .NET Framework.|

## <a name="see-also"></a>Vedere anche

- [Programmazione parallela](index.md)
- [Esempi per la programmazione parallela con .NET Core & .NET Standard](/samples/browse/?products=dotnet-core%2Cdotnet-standard&term=parallel)
