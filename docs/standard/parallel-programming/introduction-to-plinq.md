---
title: Introduzione a PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, introduction to
ms.assetid: eaa720d8-8999-4eb7-8df5-3c19ca61cad0
ms.openlocfilehash: e50b2bf15d9a627f70ff01616bf2c72c70d7ff33
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290681"
---
# <a name="introduction-to-plinq"></a>Introduzione a PLINQ

Parallel LINQ (PLINQ) è un'implementazione parallela del modello [LINQ (Language-Integrated Query)](../../csharp/programming-guide/concepts/linq/index.md) . PLINQ implementa il set completo di operatori di query standard LINQ come metodi di estensione per lo spazio dei nomi <xref:System.Linq> e dispone di operatori aggiuntivi per le operazioni parallele. PLINQ combina la semplicità e la leggibilità della sintassi di LINQ con la potenza di programmazione in parallelo.

> [!TIP]
> Se non si ha familiarità con LINQ, offre un modello unificato per l'esecuzione di query su qualsiasi origine dati enumerabile in modo indipendente dai tipi. LINQ to Objects è il nome delle query LINQ eseguite su raccolte in memoria, ad esempio oggetti <xref:System.Collections.Generic.List%601> e matrici. Questo articolo presuppone che si abbia già una conoscenza delle nozioni di base di LINQ. Per ulteriori informazioni, vedere [LINQ (Language-Integrated Query)](../../csharp/programming-guide/concepts/linq/index.md).

## <a name="what-is-a-parallel-query"></a>Che cos'è una query parallela?

Una query PLINQ è molto simile a una query LINQ to Objects non parallela. Le query PLINQ, esattamente come le query LINQ sequenziali, operano su <xref:System.Collections.IEnumerable> qualsiasi <xref:System.Collections.Generic.IEnumerable%601> origine dati o in memoria e hanno un'esecuzione posticipata, il che significa che non iniziano l'esecuzione fino a quando la query non viene enumerata. La differenza principale consiste nel fatto che PLINQ tenta di sfruttare al massimo tutti i processori del sistema. A tale scopo esegue il partizionamento dell'origine dati in segmenti e quindi esegue la query su ogni segmento in thread di lavoro distinti e in parallelo su più processori. In molti casi, l'esecuzione parallela rende notevolmente più rapida l'esecuzione della query.

Tramite l'esecuzione parallela, PLINQ può garantire per determinati tipi di query prestazioni significativamente migliori rispetto al codice legacy, spesso con la sola aggiunta dell'operazione di query <xref:System.Linq.ParallelEnumerable.AsParallel%2A> all'origine dati. Tuttavia, il parallelismo può introdurre complessità intrinseche e non tutte le operazioni di query presentano un'esecuzione più veloce in PLINQ. Di fatto, per determinate query la parallelizzazione comporta un'esecuzione più lenta. È pertanto necessario comprendere il modo in cui alcuni aspetti, ad esempio l'ordinamento, influiscono sulle query parallele. Per altre informazioni, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md).

> [!NOTE]
> Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ. Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md).

Nella parte restante di questo articolo viene fornita una panoramica delle classi PLINQ principali e viene illustrato come creare query PLINQ. Ogni sezione contiene collegamenti a informazioni dettagliate ed esempi di codice.

## <a name="the-parallelenumerable-class"></a>Classe ParallelEnumerable

La classe <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType> espone quasi tutte le funzionalità di PLINQ. Questa classe e gli altri tipi dello spazio dei nomi <xref:System.Linq?displayProperty=nameWithType> vengono compilati nell'assembly System.Core.dll. In Visual Studio i progetti C# e Visual Basic predefiniti fanno riferimento all'assembly e importano lo spazio dei nomi.

<xref:System.Linq.ParallelEnumerable> include le implementazioni di tutti gli operatori query standard supportati da LINQ to Objects, anche se non tenta di parallelizzare ognuno di essi. Se non si ha familiarità con LINQ, vedere [Introduzione a LINQ (C#)](../../csharp/programming-guide/concepts/linq/index.md) e [Introduzione a LINQ (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md).

Oltre agli operatori query standard, la classe <xref:System.Linq.ParallelEnumerable> contiene un set di metodi che rendono possibili comportamenti specifici dell'esecuzione parallela. Questi metodi specifici di PLINQ sono elencati nella tabella seguente.

|Operatore ParallelEnumerable|Descrizione|
|---------------------------------|-----------------|
|<xref:System.Linq.ParallelEnumerable.AsParallel%2A>|Punto di ingresso di PLINQ. Specifica che la parte rimanente della query deve essere parallelizzata, se è possibile.|
|<xref:System.Linq.ParallelEnumerable.AsSequential%2A>|Specifica che la parte rimanente della query deve essere eseguita in sequenza, come una query LINQ non parallela.|
|<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>|Specifica che PLINQ deve conservare l'ordine della sequenza di origine per la parte rimanente della query oppure fino a quando l'ordine non viene modificato, ad esempio tramite la clausola orderby (Order By in Visual Basic).|
|<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>|Specifica che non è necessario che PLINQ conservi l'ordine della sequenza di origine per la parte rimanente della query.|
|<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>|Specifica che PLINQ deve monitorare periodicamente lo stato del token di annullamento specificato e, se richiesto, annullare l'esecuzione.|
|<xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>|Specifica il numero massimo di processori che PLINQ deve usare per parallelizzare la query.|
|<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>|Offre un suggerimento su come PLINQ deve unire, se possibile, i risultati paralleli in un'unica sequenza nel thread in uso.|
|<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>|Specifica se PLINQ deve parallelizzare la query anche quando il comportamento predefinito ne prevede l'esecuzione sequenziale.|
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Metodo di enumerazione multithreading che, a differenza dell'iterazione sui risultati della query, consente ai risultati di essere elaborati in parallelo senza prima essere uniti nel thread in uso.|
|Overload <xref:System.Linq.ParallelEnumerable.Aggregate%2A>|Overload esclusivo di PLINQ che consente l'aggregazione intermedia su partizioni di thread locali e che offre una funzione di aggregazione finale per combinare i risultati di tutte le partizioni.|

## <a name="the-opt-in-model"></a>Modello basato su scelta esplicita

Quando si scrive una query è possibile scegliere esplicitamente PLINQ richiamando il metodo di estensione <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> nell'origine dati, come illustrato nell'esempio seguente.

[!code-csharp[PLINQ#1](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#1)]
[!code-vb[PLINQ#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#1)]

Il metodo di estensione <xref:System.Linq.ParallelEnumerable.AsParallel%2A> associa gli operatori di query successivi, in questo caso `where` e `select`, alle implementazioni di <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>.

## <a name="execution-modes"></a>Modalità di esecuzione

Per impostazione predefinita, PLINQ è conservativo. Durante il runtime, l'infrastruttura PLINQ analizza la struttura complessiva della query. Se è probabile che la parallelizzazione della query comporti una maggiore velocità di esecuzione, PLINQ esegue il partizionamento della sequenza di origine in attività eseguibili simultaneamente. Se la parallelizzazione della query non risulta un'operazione sicura, PLINQ si limita ad eseguire la query in modo sequenziale. Tra un algoritmo in parallelo potenzialmente dispendioso e un algoritmo sequenziale poco dispendioso, per impostazione predefinita PLINQ sceglie l'algoritmo sequenziale. È possibile usare il metodo <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> e l'enumerazione <xref:System.Linq.ParallelExecutionMode?displayProperty=nameWithType> per indicare a PLINQ di selezionare l'algoritmo parallelo. Ciò è utile quando si scopre tramite test e misurazioni che una determinata query risulta più veloce quando viene eseguita in parallelo. Per altre informazioni, vedere [Procedura: Specificare la modalità di esecuzione in PLINQ](how-to-specify-the-execution-mode-in-plinq.md).

## <a name="degree-of-parallelism"></a>Grado di parallelismo

Per impostazione predefinita, PLINQ usa tutti i processori nel computer host. Usando il metodo <xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A> è possibile indicare a PLINQ di usare un numero massimo di processori specificato. Ciò è utile quando si vuole garantire che gli altri processi in esecuzione nel computer ricevano una determinata quantità di tempo CPU. Il frammento seguente consente alla query di usare al massimo due processori.

[!code-csharp[PLINQ#5](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#5)]
[!code-vb[PLINQ#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#5)]

Nei casi in cui una query stia eseguendo una quantità significativa di lavoro privo di vincoli di calcolo, ad esempio l'I/O dei file, può risultare vantaggioso specificare un grado di parallelismo maggiore del numero di core nel computer.

## <a name="ordered-versus-unordered-parallel-queries"></a>Confronto fra query parallele ordinate e non ordinate

In alcune query l'operatore di query deve produrre risultati che conservano l'ordine della sequenza di origine. A questo scopo, PLINQ fornisce l'operatore <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>. <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> si differenzia da <xref:System.Linq.ParallelEnumerable.AsSequential%2A>. Una sequenza <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> viene comunque elaborata in parallelo, ma i risultati vengono memorizzati nel buffer e ordinati. Poiché la conservazione dell'ordine comporta in genere un lavoro aggiuntivo, è possibile che una sequenza <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> venga elaborata più lentamente rispetto alla sequenza <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> predefinita. La possibilità che una determinata operazione in parallelo ordinata risulti più veloce di una versione sequenziale dell'operazione dipende da molti fattori.

L'esempio di codice seguente illustra come scegliere esplicitamente la conservazione dell'ordine.

[!code-csharp[PLINQ#3](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#3)]
[!code-vb[PLINQ#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#3)]

Per altre informazioni, vedere [Conservazione dell'ordine in PLINQ](order-preservation-in-plinq.md).

## <a name="parallel-vs-sequential-queries"></a>Query parallele e sequenziali

Alcune operazioni richiedono che i dati di origine vengano recapitati in modo sequenziale. Quando è necessario, gli operatori di query <xref:System.Linq.ParallelEnumerable> ripristinano automaticamente la modalità sequenziale. Per gli operatori di query definiti dall'utente e i delegati dell'utente che richiedono l'esecuzione sequenziale, PLINQ fornisce il metodo <xref:System.Linq.ParallelEnumerable.AsSequential%2A>. Quando si usa <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, tutti gli operatori successivi nella query vengono eseguiti in sequenza fino a quando non viene richiamato il metodo <xref:System.Linq.ParallelEnumerable.AsParallel%2A>. Per altre informazioni, vedere [Procedura: Combinare query LINQ parallele e sequenziali](how-to-combine-parallel-and-sequential-linq-queries.md).

## <a name="options-for-merging-query-results"></a>Opzioni di unione dei risultati di query

Quando una query PLINQ viene eseguita in parallelo, i relativi risultati ottenuti da ogni thread di lavoro devono essere uniti nel thread principale affinché vengano usati da un ciclo `foreach` (`For Each` in Visual Basic) o vengano inseriti in un elenco o in una matrice. In alcuni casi può essere vantaggioso specificare un determinato tipo di operazione di unione, ad esempio per iniziare a produrre risultati più velocemente. A tale scopo, PLINQ supporta il metodo <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> e l'enumerazione <xref:System.Linq.ParallelMergeOptions>. Per altre informazioni, vedere [Opzioni di unione in PLINQ](merge-options-in-plinq.md).

## <a name="the-forall-operator"></a>Operatore ForAll

Nelle query LINQ sequenziali l'esecuzione viene posticipata fino a quando la query non viene enumerata in un `foreach` `For Each` ciclo (in Visual Basic) o richiamando un metodo come <xref:System.Linq.ParallelEnumerable.ToList%2A> , <xref:System.Linq.ParallelEnumerable.ToArray%2A> o <xref:System.Linq.ParallelEnumerable.ToDictionary%2A> . In PLINQ è anche possibile usare `foreach` per eseguire la query e l'iterazione dei risultati. Tuttavia, poiché non viene eseguito in parallelo, `foreach` richiede che l'output di tutte le attività in parallelo venga unito di nuovo nel thread in cui il ciclo è in esecuzione. In PLINQ è possibile usare `foreach` quando è necessario conservare l'ordine finale dei risultati della query nonché quando si elaborano i risultati in modo seriale, ad esempio quando si chiama `Console.WriteLine` per ogni elemento. Per eseguire più velocemente una query quando la conservazione dell'ordine non è richiesta e quando la stessa elaborazione dei risultati può essere parallelizzata, usare il metodo <xref:System.Linq.ParallelEnumerable.ForAll%2A> per eseguire una query PLINQ. <xref:System.Linq.ParallelEnumerable.ForAll%2A> non esegue questo passaggio di merge finale. Nell'esempio di codice riportato di seguito viene illustrato come utilizzare il metodo <xref:System.Linq.ParallelEnumerable.ForAll%2A>. In questo caso viene usato l'oggetto <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType> perché è ottimizzato per l'aggiunta simultanea di più thread senza un tentativo di rimuovere gli elementi.

[!code-csharp[PLINQ#4](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#4)]
[!code-vb[PLINQ#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#4)]

La figura seguente mostra la differenza tra `foreach` e <xref:System.Linq.ParallelEnumerable.ForAll%2A> per quanto riguarda l'esecuzione di query.

![ForAll e ForEach](media/vs-isvnt-allvseach.png "VS_ISVNT_ALLvsEACH")

## <a name="cancellation"></a>Annullamento

PLINQ è integrato con i tipi di annullamento in .NET Framework 4. Per ulteriori informazioni, vedere [annullamento in thread gestiti](../threading/cancellation-in-managed-threads.md). Pertanto, a differenza delle query di LINQ to Objects sequenziali, le query PLINQ possono essere annullate. Per creare una query PLINQ annullabile, usare l'operatore <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> nella query e fornire un'istanza di <xref:System.Threading.CancellationToken> come argomento. Quando la proprietà <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> nel token è impostata su true, PLINQ rileva questa impostazione, arresta l'elaborazione in tutti i thread e genera un'eccezione <xref:System.OperationCanceledException>.

È possibile che una query PLINQ continui a elaborare alcuni elementi dopo l'impostazione del token di annullamento.

Per garantire una maggiore capacità di risposta, è possibile rispondere alle richieste di annullamento anche nei delegati dell'utente di lunga durata. Per altre informazioni, vedere [Procedura: Annullare una query PLINQ](how-to-cancel-a-plinq-query.md).

## <a name="exceptions"></a>Eccezioni

Quando viene eseguita una query PLINQ, è possibile che vengano generate simultaneamente più eccezioni da thread diversi. Inoltre, il codice per gestire l'eccezione e quello che ha generato l'eccezione potrebbero trovarsi in thread diversi. PLINQ usa il tipo <xref:System.AggregateException> per incapsulare tutte le eccezioni generate da una query e quindi eseguirne il marshalling nel thread chiamante. Nel thread chiamante è necessario un unico blocco try-catch. È possibile tuttavia eseguire l'iterazione in tutte le eccezioni incapsulate in <xref:System.AggregateException> e rilevare quelle gestibili in modo sicuro. In casi rari, alcune eccezioni possono essere generate senza wrapping in <xref:System.AggregateException>. Anche <xref:System.Threading.ThreadAbortException> non prevede il wrapping.

Quando alle eccezioni è consentita la propagazione fino al thread di unione, è possibile che una query continui a elaborare alcuni elementi dopo la generazione dell'eccezione.

Per altre informazioni, vedere [Procedura: Gestire le eccezioni in una query PLINQ](how-to-handle-exceptions-in-a-plinq-query.md).

## <a name="custom-partitioners"></a>Partitioner personalizzati

In alcuni casi è possibile migliorare le prestazioni delle query scrivendo un Partitioner personalizzato che sfrutta alcune caratteristiche dei dati di origine. Nella query il partitioner personalizzato è l'oggetto enumerabile su cui viene eseguita la query.

[!code-csharp[PLINQ#2](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#2)]
[!code-vb[PLINQ#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq3.vb#2)]

PLINQ supporta un numero fisso di partizioni. È tuttavia possibile che durante il runtime i dati vengano riassegnati dinamicamente alle partizioni per il bilanciamento del carico. <xref:System.Threading.Tasks.Parallel.For%2A> e <xref:System.Threading.Tasks.Parallel.ForEach%2A> supportano solo il partizionamento dinamico, il che significa che il numero di partizioni cambia in fase di esecuzione. Per altre informazioni, vedere [Partitioner personalizzati per PLINQ e TPL](custom-partitioners-for-plinq-and-tpl.md).

## <a name="measuring-plinq-performance"></a>Misurazione delle prestazioni di PLINQ

In molti casi una query può essere parallelizzata, ma le risorse necessarie per configurare la query parallela rappresentano uno svantaggio superiore al vantaggio ottenuto in termini di prestazioni. Se la query esegue pochi calcoli o se l'origine dati è di dimensioni ridotte, è possibile che una query PLINQ risulti più lenta di una query LINQ to Objects sequenziale. È possibile usare Parallel Performance Analyzer in Visual Studio Team Server per confrontare le prestazioni delle diverse query per individuare colli di bottiglia di elaborazione e determinare se la query è eseguita in parallelo o in modo sequenziale. Per altre informazioni, vedere [Visualizzatore di concorrenze](/visualstudio/profiling/concurrency-visualizer) e [Procedura: Misurare le prestazioni di esecuzione delle query di PLINQ](how-to-measure-plinq-query-performance.md).

## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
- [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md)
