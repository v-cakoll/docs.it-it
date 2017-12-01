---
title: Introduzione a PLINQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, introduction to
ms.assetid: eaa720d8-8999-4eb7-8df5-3c19ca61cad0
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: db9c3e16d4a8073fbce636f37490f719dbd93e4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-plinq"></a>Introduzione a PLINQ
## <a name="what-is-a-parallel-query"></a>Che cos'è una query parallela?  
 LINQ (Language-Integrated Query), introdotto in [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)],  È dotato di un modello unificato per l'esecuzione di qualsiasi query <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> origine dati in modo indipendente dai tipi. LINQ to Objects è il nome per le query LINQ che vengono eseguite le raccolte in memoria, ad esempio <xref:System.Collections.Generic.List%601> e matrici. Questo articolo presuppone che si abbia già una conoscenza delle nozioni di base di LINQ. Per altre informazioni, vedere [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).  
  
 Parallel LINQ (PLINQ) è un'implementazione in parallelo del modello LINQ. Una query PLINQ è molto simile a una query LINQ to Objects non parallela. PLINQ (query), come sequenziale [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)] query, operano su qualsiasi in memoria <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601> dati di origine e dispone di esecuzione, il che significa che non iniziano l'esecuzione fino a quando non viene enumerata la query posticipata. La differenza principale consiste nel fatto che PLINQ tenta di sfruttare al massimo tutti i processori del sistema. A tale scopo esegue il partizionamento dell'origine dati in segmenti e quindi esegue la query su ogni segmento in thread di lavoro distinti e in parallelo su più processori. In molti casi, l'esecuzione parallela rende notevolmente più rapida l'esecuzione della query.  
  
 Tramite l'esecuzione parallela, PLINQ può garantire miglioramenti significativi delle prestazioni rispetto al codice legacy per determinati tipi di query, spesso semplicemente aggiungendo il <xref:System.Linq.ParallelEnumerable.AsParallel%2A> operazione all'origine dati di query. Tuttavia, il parallelismo può introdurre complessità intrinseche e non tutte le operazioni di query presentano un'esecuzione più veloce in PLINQ. Di fatto, per determinate query la parallelizzazione comporta un'esecuzione più lenta. È pertanto necessario comprendere il modo in cui alcuni aspetti, ad esempio l'ordinamento, influiscono sulle query parallele. Per altre informazioni, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
> [!NOTE]
>  Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ. Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 La parte rimanente di questo articolo offre una panoramica delle classi PLINQ principali e descrive come creare query PLINQ. Ogni sezione contiene collegamenti a informazioni dettagliate ed esempi di codice.  
  
## <a name="the-parallelenumerable-class"></a>Classe ParallelEnumerable  
 La <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType> classe espone quasi tutte le funzionalità di PLINQ.  E il resto del <xref:System.Linq?displayProperty=nameWithType> tipi dello spazio dei nomi vengono compilati in assembly System.Core.dll. In Visual Studio i progetti C# e Visual Basic predefiniti fanno riferimento all'assembly e importano lo spazio dei nomi.  
  
 <xref:System.Linq.ParallelEnumerable>include le implementazioni di tutti gli operatori query standard che supporta LINQ to Objects, anche se non tenta di parallelizzare ognuno di essi. Se non si ha familiarità con [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)], vedere [Introduzione a LINQ](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e).  
  
 Oltre agli operatori di query standard, la <xref:System.Linq.ParallelEnumerable> classe contiene un set di metodi che attivano i comportamenti specifici dell'esecuzione parallela. Questi metodi specifici di PLINQ sono elencati nella tabella seguente.  
  
|Operatore ParallelEnumerable|Descrizione|  
|---------------------------------|-----------------|  
|<xref:System.Linq.ParallelEnumerable.AsParallel%2A>|Punto di ingresso di PLINQ. Specifica che la parte rimanente della query deve essere parallelizzata, se è possibile.|  
|<xref:System.Linq.ParallelEnumerable.AsSequential%2A>|Specifica che la parte rimanente della query deve essere eseguita in sequenza, come una query LINQ non parallela.|  
|<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>|Specifica che PLINQ deve conservare l'ordine della sequenza di origine per la parte rimanente della query oppure fino a quando l'ordine non viene modificato, ad esempio tramite la clausola orderby (Order By in Vlsual Basic).|  
|<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>|Specifica che non è necessario che PLINQ conservi l'ordine della sequenza di origine per la parte rimanente della query.|  
|<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>|Specifica che PLINQ deve monitorare periodicamente lo stato del token di annullamento specificato e, se richiesto, annullare l'esecuzione.|  
|<xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>|Specifica il numero massimo di processori che PLINQ deve usare per parallelizzare la query.|  
|<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>|Offre un suggerimento su come PLINQ deve unire, se possibile, i risultati paralleli in un'unica sequenza nel thread in uso.|  
|<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>|Specifica se PLINQ deve parallelizzare la query anche quando il comportamento predefinito ne prevede l'esecuzione sequenziale.|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Metodo di enumerazione multithreading che, a differenza dell'iterazione sui risultati della query, consente ai risultati di essere elaborati in parallelo senza prima essere uniti nel thread in uso.|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>eseguire l'overload|Overload esclusivo di PLINQ che consente l'aggregazione intermedia su partizioni di thread locali e che offre una funzione di aggregazione finale per combinare i risultati di tutte le partizioni.|  
  
## <a name="the-opt-in-model"></a>Modello basato su scelta esplicita  
 Quando si scrive una query, di partecipare a PLINQ richiamando il <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> il metodo di estensione nell'origine dati, come illustrato nell'esempio seguente.  
  
 [!code-csharp[PLINQ#1](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#1)]
 [!code-vb[PLINQ#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#1)]  
  
 Il <xref:System.Linq.ParallelEnumerable.AsParallel%2A> metodo di estensione associa gli operatori di query successive, in questo caso, `where` e `select`al <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType> implementazioni.  
  
## <a name="execution-modes"></a>Modalità di esecuzione  
 Per impostazione predefinita, PLINQ è conservativo. Durante il runtime, l'infrastruttura PLINQ analizza la struttura complessiva della query. Se è probabile che la parallelizzazione della query comporti una maggiore velocità di esecuzione, PLINQ esegue il partizionamento della sequenza di origine in attività eseguibili simultaneamente. Se la parallelizzazione della query non risulta un'operazione sicura, PLINQ si limita ad eseguire la query in modo sequenziale. Tra un algoritmo in parallelo potenzialmente dispendioso e un algoritmo sequenziale poco dispendioso, per impostazione predefinita PLINQ sceglie l'algoritmo sequenziale. È possibile utilizzare il <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> (metodo) e <xref:System.Linq.ParallelExecutionMode?displayProperty=nameWithType> enumerazione per indicare a PLINQ per selezionare l'algoritmo in parallelo. Ciò è utile quando si scopre tramite test e misurazioni che una determinata query risulta più veloce quando viene eseguita in parallelo. Per altre informazioni, vedere [Procedura: Specificare la modalità di esecuzione in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
## <a name="degree-of-parallelism"></a>Grado di parallelismo  
 Per impostazione predefinita, PLINQ utilizza tutti i processori nel computer host. È possibile indicare a PLINQ di usare non più di un numero specificato di processori tramite il <xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A> metodo. Ciò è utile quando si vuole garantire che gli altri processi in esecuzione nel computer ricevano una determinata quantità di tempo CPU. Il frammento seguente consente alla query di usare al massimo due processori.  
  
 [!code-csharp[PLINQ#5](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#5)]
 [!code-vb[PLINQ#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#5)]  
  
 Nei casi in cui una query stia eseguendo una quantità significativa di lavoro privo di vincoli di calcolo, ad esempio l'I/O dei file, può risultare vantaggioso specificare un grado di parallelismo maggiore del numero di core nel computer.  
  
## <a name="ordered-versus-unordered-parallel-queries"></a>Confronto fra query parallele ordinate e non ordinate  
 In alcune query l'operatore di query deve produrre risultati che conservano l'ordine della sequenza di origine. PLINQ fornisce il <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> operatore a questo scopo. <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>è diverso da quello di <xref:System.Linq.ParallelEnumerable.AsSequential%2A>. Un <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> sequenza viene comunque elaborata in parallelo, ma i risultati vengono memorizzati nel buffer e ordinati. Poiché la conservazione dell'ordine è in genere comporta lavoro aggiuntivo, un <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> sequenza potrebbe essere elaborata più lentamente rispetto a quello predefinito <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> sequenza. La possibilità che una determinata operazione in parallelo ordinata risulti più veloce di una versione sequenziale dell'operazione dipende da molti fattori.  
  
 L'esempio di codice seguente illustra come scegliere esplicitamente la conservazione dell'ordine.  
  
 [!code-csharp[PLINQ#3](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#3)]
 [!code-vb[PLINQ#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#3)]  
  
 Per altre informazioni, vedere [Conservazione dell'ordine in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
## <a name="parallel-vs-sequential-queries"></a>Confronto fra query parallele e sequenziali  
 Alcune operazioni richiedono che i dati di origine vengano recapitati in modo sequenziale. Il <xref:System.Linq.ParallelEnumerable> query gli operatori di ripristino la modalità sequenziale automaticamente quando necessario. Per gli operatori di query definiti dall'utente e i delegati dell'utente che richiedono l'esecuzione sequenziale, PLINQ fornisce il <xref:System.Linq.ParallelEnumerable.AsSequential%2A> metodo. Quando si utilizza <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, tutti gli operatori successivi nella query vengono eseguiti in sequenza finché <xref:System.Linq.ParallelEnumerable.AsParallel%2A> viene chiamata nuovamente. Per altre informazioni, vedere [Procedura: Combinare query LINQ parallele e sequenziali](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md).  
  
## <a name="options-for-merging-query-results"></a>Opzioni di unione dei risultati di query  
 Quando una query PLINQ viene eseguita in parallelo, i relativi risultati ottenuti da ogni thread di lavoro devono essere uniti nel thread principale affinché vengano usati da un ciclo `foreach` (`For Each` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) o vengano inseriti in un elenco o in una matrice. In alcuni casi può essere vantaggioso specificare un determinato tipo di operazione di unione, ad esempio per iniziare a produrre risultati più velocemente. A tale scopo, PLINQ supporta il <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> (metodo) e <xref:System.Linq.ParallelMergeOptions> enumerazione. Per altre informazioni, vedere [Opzioni di unione in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
## <a name="the-forall-operator"></a>Operatore ForAll  
 In sequenziale [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)] esecuzione query viene posticipata finché non viene enumerata la query in un `foreach` (`For Each` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) ciclo o per richiamare un metodo, ad esempio <xref:System.Linq.ParallelEnumerable.ToList%2A> , <xref:System.Linq.ParallelEnumerable.ToArray%2A> , o <xref:System.Linq.ParallelEnumerable.ToDictionary%2A>. In PLINQ è anche possibile usare `foreach` per eseguire la query e l'iterazione dei risultati. Tuttavia, poiché non viene eseguito in parallelo, `foreach` richiede che l'output di tutte le attività in parallelo venga unito di nuovo nel thread in cui il ciclo è in esecuzione. In PLINQ è possibile usare `foreach` quando è necessario conservare l'ordine finale dei risultati della query nonché quando si elaborano i risultati in modo seriale, ad esempio quando si chiama `Console.WriteLine` per ogni elemento. Per più velocemente quando la conservazione dell'ordine non è necessario eseguire la query e quando l'elaborazione dei risultati può essere parallelizzata, utilizzare il <xref:System.Linq.ParallelEnumerable.ForAll%2A> metodo per eseguire una query PLINQ. <xref:System.Linq.ParallelEnumerable.ForAll%2A>non eseguire questo passaggio di unione. Nell'esempio di codice riportato di seguito viene illustrato come utilizzare il metodo <xref:System.Linq.ParallelEnumerable.ForAll%2A>. <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>viene utilizzato perché è ottimizzato per l'aggiunta contemporaneamente senza tentare di rimuovere tutti gli elementi di più thread.  
  
 [!code-csharp[PLINQ#4](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#4)]
 [!code-vb[PLINQ#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#4)]  
  
 Nella figura seguente mostra la differenza tra `foreach` e <xref:System.Linq.ParallelEnumerable.ForAll%2A> per quanto riguarda l'esecuzione di query.  
  
 ![Confronto tra ForAll e ForEach](../../../docs/standard/parallel-programming/media/vs-isvnt-allvseach.png "VS_ISVNT_ALLvsEACH")  
  
## <a name="cancellation"></a>Annullamento  
 PLINQ è integrato con i tipi di annullamento in [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. Per altre informazioni, vedere [Annullamento in thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md). Di conseguenza, a differenza delle query LINQ to Objects sequenziali, le query PLINQ possono essere annullate. Per creare una query PLINQ annullabile, utilizzare il <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> gli operatori di query e fornire un <xref:System.Threading.CancellationToken> istanza come argomento. Quando il <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> sul token è impostata su true, PLINQ si noti, arrestare l'elaborazione in tutti i thread e generare un <xref:System.OperationCanceledException>.  
  
 È possibile che una query PLINQ continui a elaborare alcuni elementi dopo l'impostazione del token di annullamento.  
  
 Per garantire una maggiore capacità di risposta, è possibile rispondere alle richieste di annullamento anche nei delegati dell'utente di lunga durata. Per altre informazioni, vedere [Procedura: Annullare una query PLINQ](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md).  
  
## <a name="exceptions"></a>Eccezioni  
 Quando viene eseguita una query PLINQ, è possibile che vengano generate simultaneamente più eccezioni da thread diversi. Inoltre, il codice per gestire l'eccezione e quello che ha generato l'eccezione potrebbero trovarsi in thread diversi. PLINQ utilizza il <xref:System.AggregateException> digitare per incapsulare tutte le eccezioni generate da una query e il marshalling al thread chiamante. Nel thread chiamante è necessario un unico blocco try-catch. Tuttavia, è possibile scorrere tutte le eccezioni che sono incapsulate nel <xref:System.AggregateException> e rilevare qualsiasi che è possibile ripristinare in modo sicuro da. In rari casi, potrebbero generate alcune eccezioni che non sono incapsulati in un <xref:System.AggregateException>, e <xref:System.Threading.ThreadAbortException>s sono anche non eseguito il wrapping.  
  
 Quando alle eccezioni è consentita la propagazione fino al thread di unione, è possibile che una query continui a elaborare alcuni elementi dopo la generazione dell'eccezione.  
  
 Per altre informazioni, vedere [Procedura: Gestire le eccezioni in una query PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="custom-partitioners"></a>Partitioner personalizzati  
 In alcuni casi è possibile migliorare le prestazioni delle query scrivendo un Partitioner personalizzato che sfrutta alcune caratteristiche dei dati di origine. Nella query il partitioner personalizzato è l'oggetto enumerabile su cui viene eseguita la query.  
  
 [!code-csharp[PLINQ#2](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#2)]
 [!code-vb[PLINQ#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq3.vb#2)]  
  
 PLINQ supporta un numero fisso di partizioni. È tuttavia possibile che durante il runtime i dati vengano riassegnati dinamicamente alle partizioni per il bilanciamento del carico. <xref:System.Threading.Tasks.Parallel.For%2A>e <xref:System.Threading.Tasks.Parallel.ForEach%2A> supportano solo il partizionamento dinamico, il che significa che il numero di partizioni cambia in fase di esecuzione. Per altre informazioni, vedere [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## <a name="measuring-plinq-performance"></a>Misurazione delle prestazioni di PLINQ  
 In molti casi una query può essere parallelizzata, ma le risorse necessarie per configurare la query parallela rappresentano uno svantaggio superiore al vantaggio ottenuto in termini di prestazioni. Se la query esegue pochi calcoli o se l'origine dati è di dimensioni ridotte, è possibile che una query PLINQ risulti più lenta di una query LINQ to Objects sequenziale. È possibile usare Parallel Performance Analyzer in Visual Studio Team Server per confrontare le prestazioni delle diverse query per individuare colli di bottiglia di elaborazione e determinare se la query è eseguita in parallelo o in modo sequenziale. Per altre informazioni, vedere [Visualizzatore di concorrenze](/visualstudio/profiling/concurrency-visualizer) e [Procedura: Misurare le prestazioni di esecuzione delle query di PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)
