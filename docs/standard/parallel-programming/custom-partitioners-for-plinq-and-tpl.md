---
title: Partitioner personalizzati per PLINQ e TPL
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
helpviewer_keywords: tasks, partitioners
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12d234b86b0067178d54d2fdcb5d37ceaee6109d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="custom-partitioners-for-plinq-and-tpl"></a>Partitioner personalizzati per PLINQ e TPL
Per parallelizzare un'operazione su un'origine dati, è uno dei passaggi essenziali per *partizione* l'origine in più sezioni a cui è possibile accedere contemporaneamente da più thread. PLINQ e Task Parallel Library (TPL) forniscono partitioner predefiniti che funzionano in modo trasparente quando si scrive una query parallela o <xref:System.Threading.Tasks.Parallel.ForEach%2A> ciclo. Per scenari più avanzati, è possibile collegare il proprio partitioner.  
  
## <a name="kinds-of-partitioning"></a>Tipi di partizionamento  
 Esistono diversi modi per suddividere un'origine dati. Negli approcci più efficienti, più thread cooperano ai fini della sequenza di origine originale invece di separazione fisica di origine in più sottosequenze. Per le matrici e altri indicizzata origini, ad esempio <xref:System.Collections.IList> raccolte in cui la lunghezza è nota in anticipo, *il partizionamento per intervalli* è il tipo più semplice di partizionamento. Ogni thread riceve univoco indici iniziali e finali, in modo che sia possibile elaborare l'intervallo di origine senza sovrascrivere o vengano sovrascritti dagli altri thread. L'unico overhead necessario per eseguire il partizionamento per intervalli è il lavoro iniziale di creazione degli intervalli; Nessun ulteriore sincronizzazione è necessario in seguito. Pertanto, può fornire buone prestazioni, purché il carico di lavoro viene suddiviso equamente. Uno svantaggio del partizionamento per intervalli è che se un thread termina prima del previsto, in grado di altri thread terminato il lavoro.  
  
 Per gli elenchi collegati o altri insiemi la cui lunghezza non è noto, è possibile utilizzare *il partizionamento*. Nel partizionamento, ogni thread o attività in un ciclo parallelo o la query utilizza un determinato numero di elementi di origine in un blocco, li elabora e quindi torna a recuperare altri elementi. Il partitioner garantisce che tutti gli elementi vengono distribuiti e che non siano presenti duplicati. Un blocco può essere di qualsiasi dimensione. Ad esempio, l'elemento partitioner viene dimostrato in [come: partizioni dinamiche implementano](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md) creazione di blocchi che contengono un solo elemento. Finché i blocchi non sono troppo grandi, questo tipo di partizionamento è progettato per il bilanciamento del carico perché l'assegnazione di elementi per i thread non è predeterminato. Tuttavia, l'elemento partitioner, tuttavia, il sovraccarico della sincronizzazione ogni volta che il thread per ottenere un altro blocco. La quantità di sincronizzazione in questi casi è inversamente proporzionale alla dimensione dei blocchi.  
  
 In generale, il partizionamento per intervalli è più veloce quando il tempo di esecuzione del delegato è ridotto a moderato e l'origine contiene un numero elevato di elementi e il lavoro totale di ogni partizione è quasi equivalente. Il partizionamento è pertanto in genere più veloce nella maggior parte dei casi. Origini con un numero limitato di elementi o tempi di esecuzione per il delegato, quindi le prestazioni di blocco e il partizionamento per intervalli riguarda uguale.  
  
 I partitioner TPL supportano anche un numero di partizioni dinamico. Ciò significa che possono creare partizioni in qualsiasi momento, ad esempio, quando il <xref:System.Threading.Tasks.Parallel.ForEach%2A> ciclo genera una nuova attività. Questa funzionalità consente il partitioner scalabilità insieme al ciclo stesso. Partitioner dinamico sono anche implicitamente il bilanciamento del carico. Quando si crea un partitioner personalizzato, è necessario supportare il partizionamento dinamico per essere utilizzabile da un <xref:System.Threading.Tasks.Parallel.ForEach%2A> ciclo.  
  
### <a name="configuring-load-balancing-partitioners-for-plinq"></a>Configurazione di bilanciamento del carico partitioner per PLINQ  
 Alcuni overload di <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> metodo consentono di creare un partitioner per una matrice o <xref:System.Collections.IList> di origine e specificare se deve tentare di bilanciare il carico di lavoro tra i thread. Quando il partitioner è configurato per il bilanciamento del carico, il partizionamento viene utilizzato e gli elementi vengono passati a ogni partizione in piccoli blocchi quando vengono richiesti. Questo approccio consente di garantire che tutte le partizioni sono presenti elementi da elaborare fino a quando l'intero ciclo o query è stata completata. Un overload aggiuntivo utilizzabile per implementare il bilanciamento del carico di partizionamento di qualsiasi <xref:System.Collections.IEnumerable> origine.  
  
 Il bilanciamento del carico richiede in genere, le partizioni per richiedere elementi relativamente spesso il partitioner. Al contrario, un partitioner che esegue il partizionamento statico può assegnare gli elementi a ogni partitioner tutti contemporaneamente utilizzando l'intervallo o il partizionamento. Ciò comporta un sovraccarico minore rispetto a bilanciamento del carico, ma potrebbe richiedere più tempo se un thread finisce con molte più attività rispetto alle altre. Per impostazione predefinita quando viene passato una IList o una matrice, PLINQ Usa sempre il partizionamento per intervalli senza bilanciamento del carico. Per abilitare il bilanciamento del carico per PLINQ, utilizzare il `Partitioner.Create` (metodo), come illustrato nell'esempio seguente.  
  
 [!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
 [!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]  
  
 Il modo migliore per determinare se per utilizzare il bilanciamento del carico in qualsiasi scenario specificato è nello sperimentare e misurare il tempo impiegato completamento nelle configurazioni di computer e carichi rappresentativi delle operazioni. Ad esempio, il partizionamento statico potrebbe fornire un aumento significativo in un computer multicore con solo pochi core, ma potrebbe causare rallentamenti nei computer che dispongono di core relativamente elevato.  
  
 La tabella seguente elenca gli overload disponibili del <xref:System.Collections.Concurrent.Partitioner.Create%2A> metodo. Questi partitioner non sono limitati a usare solo con PLINQ o <xref:System.Threading.Tasks.Task>. Possono inoltre essere utilizzati con qualsiasi costrutto parallelo personalizzato.  
  
|Eseguire l'overload|Usa il bilanciamento del carico|  
|--------------|-------------------------|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Sempre|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Quando l'argomento booleano viene specificato come true|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Quando l'argomento booleano viene specificato come true|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Mai|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Mai|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Mai|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Mai|  
  
### <a name="configuring-static-range-partitioners-for-parallelforeach"></a>Configurazione di partitioner statico intervallo per Parallel. foreach  
 In un <xref:System.Threading.Tasks.Parallel.For%2A> ciclo, il corpo del ciclo viene fornito come un delegato al metodo. Il costo della chiamata al delegato è paragonabile a una chiamata al metodo virtuale. In alcuni scenari, il corpo di un ciclo parallelo potrebbe essere sufficientemente piccolo che diventa significativo il costo della chiamata al delegato a ogni iterazione del ciclo. In tali situazioni, è possibile utilizzare uno del <xref:System.Collections.Concurrent.Partitioner.Create%2A> overload per creare un <xref:System.Collections.Generic.IEnumerable%601> di partizioni a intervalli sugli elementi di origine. Quindi, è possibile passare questo insieme di intervalli per un <xref:System.Threading.Tasks.Parallel.ForEach%2A> metodo il cui corpo è costituito da una normale `for` ciclo. Il vantaggio di questo approccio è che il costo della chiamata al delegato si verifica una sola volta per ogni intervallo, anziché una volta per ogni elemento. Nell'esempio seguente viene illustrato il modello di base.  
  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Ogni thread nel ciclo riceve il proprio <xref:System.Tuple%602> che contiene i valori iniziale e finale dell'indice dell'intervallo secondario specificato. Interna `for` ciclo viene utilizzato il `fromInclusive` e `toExclusive` valori per eseguire il ciclo di matrice o <xref:System.Collections.IList> direttamente.  
  
 Uno del <xref:System.Collections.Concurrent.Partitioner.Create%2A> overload consente di specificare le dimensioni delle partizioni e il numero di partizioni. Questo overload è utilizzabile negli scenari in cui ogni elemento di lavoro viene così ridotto che anche un metodo virtuale chiamata per ogni elemento ha un impatto notevole sulle prestazioni.  
  
## <a name="custom-partitioners"></a>Partitioner personalizzati  
 In alcuni scenari, potrebbe essere utile o anche necessari per implementare un partitioner personalizzato. Ad esempio, potrebbe essere una classe di raccolta personalizzato che è possibile partizionare in modo più efficiente rispetto al valore predefinito di partitioner può, in base alla propria conoscenza della struttura interna della classe. In alternativa, è consigliabile creare partizioni a intervalli di dimensioni variabili in base alla propria conoscenza del tempo necessario per l'elaborazione degli elementi in posizioni diverse nella raccolta di origine.  
  
 Per creare un partitioner personalizzato di base, derivare una classe da <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=nameWithType> ed eseguire l'override dei metodi virtuali, come descritto nella tabella seguente.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|Questo metodo viene chiamato una volta dal thread principale e restituisce un IList(IEnumerator(TSource)). Ogni thread di lavoro del ciclo o di una query è possibile chiamare `GetEnumerator` dell'elenco per recuperare un <xref:System.Collections.Generic.IEnumerator%601> su una partizione distinta.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Restituire `true` se si implementa <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, in caso contrario, `false`.|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Se <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> è `true`, questo metodo può essere chiamato facoltativamente anziché <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 Se i risultati devono essere ordinabili o si richiede l'accesso indicizzato agli elementi, derivare da <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> ed eseguire l'override dei metodi virtuali, come descritto nella tabella seguente.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|Questo metodo viene chiamato una volta dal thread principale e restituisce un `IList(IEnumerator(TSource))`. Ogni thread di lavoro del ciclo o di una query è possibile chiamare `GetEnumerator` dell'elenco per recuperare un <xref:System.Collections.Generic.IEnumerator%601> su una partizione distinta.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Restituire `true` se si implementa <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>; in caso contrario, false.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|In genere, si limita a chiamare <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Se <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> è `true`, questo metodo può essere chiamato facoltativamente anziché <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 Nella tabella seguente fornisce informazioni aggiuntive dettagliate su come i tre tipi di bilanciamento del carico partitioner implementare la <xref:System.Collections.Concurrent.OrderablePartitioner%601> classe.  
  
|Metodo o proprietà|IList / matrice senza bilanciamento del carico|IList / matrice con bilanciamento del carico|IEnumerable|  
|----------------------|-------------------------------------------|----------------------------------------|-----------------|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Utilizza il partizionamento per intervallo|Utilizza il partizionamento ottimizzato per gli elenchi per l'elemento partitionCount specificato|Utilizza il partizionamento tramite la creazione di un numero statico di partizioni.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=nameWithType>|Eccezione generata non supportata|Utilizza il partizionamento ottimizzato per gli elenchi e le partizioni dinamiche|Utilizza il partizionamento tramite la creazione di un numero di partizioni dinamico.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Restituisce `true`.|Restituisce `true`.|Restituisce `true`.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Restituisce `true`.|Restituisce `false`.|Restituisce `false`.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Restituisce `true`.|Restituisce `true`.|Restituisce `true`.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Restituisce `false`.|Restituisce `true`.|Restituisce `true`.|  
  
### <a name="dynamic-partitions"></a>Partizioni dinamiche  
 Se si prevede che il partitioner da utilizzare in un <xref:System.Threading.Tasks.Parallel.ForEach%2A> (metodo), è necessario essere in grado di restituire un numero di partizioni dinamico. Ciò significa che il partitioner può fornire un enumeratore per una nuova partizione su richiesta in qualsiasi momento durante l'esecuzione del ciclo. In pratica, ogni volta che il ciclo aggiunge una nuova attività parallela, verrà richiesta una nuova partizione per l'attività. Se si richiedono i dati siano ordinabili, derivare da <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> in modo che ogni elemento in ogni partizione viene assegnato un indice univoco.  
  
 Per ulteriori informazioni e un esempio, vedere [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
### <a name="contract-for-partitioners"></a>Contratto per i partitioner  
 Quando si implementa un partitioner personalizzato, seguire queste linee guida per garantire la corretta interazione con PLINQ e <xref:System.Threading.Tasks.Parallel.ForEach%2A> in TPL:  
  
-   Se <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> viene chiamata con un argomento di zero o meno, per `partitionsCount`, generare <xref:System.ArgumentOutOfRangeException>. Anche se PLINQ e TPL non passeranno mai in un `partitionCount` uguale a 0, si consiglia comunque di prevenire il possibilità.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>e <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> deve sempre restituire `partitionsCount` numero di partizioni. Se l'elemento partitioner dati si esaurisce e non è possibile creare tante partizioni quante richiesto, il metodo deve restituire un enumeratore vuoto per ciascuna delle rimanenti partizioni. In caso contrario, sia PLINQ e TPL genererà un <xref:System.InvalidOperationException>.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, e <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> non devono mai restituire `null` (`Nothing` in Visual Basic). In caso affermativo, PLINQ / TPL genererà un <xref:System.InvalidOperationException>.  
  
-   Metodi che restituiscono le partizioni devono sempre restituire partizioni che possono enumerare completamente e in modo univoco l'origine dati. Devono essere presenti duplicati nell'origine dati o elementi ignorati a meno che non specificamente richiesto dalla progettazione del partitioner. Se questa regola non viene rispettata, può alterato l'ordine di output.  
  
-   Il getter booleana seguente deve sempre restituire esattamente i valori seguenti in modo che l'ordine di output non è codificato:  
  
    -   `KeysOrderedInEachPartition`: Ogni partizione restituisce gli elementi con indici di chiave incrementali.  
  
    -   `KeysOrderedAcrossPartitions`: Per tutte le partizioni che vengono restituiti gli indici di chiave di partizione *si* sono maggiori degli indici di chiave di partizione *si*-1.  
  
    -   `KeysNormalized`: Tutti gli indici di chiave sono a incremento progressivo costante senza interruzioni, a partire da zero.  
  
-   Tutti gli indici devono essere univoci. Potrebbe non essere indici duplicati. Se questa regola non viene rispettata, può alterato l'ordine di output.  
  
-   Tutti gli indici devono essere negativi. Se questa regola non viene rispettata, PLINQ/TPL può generare eccezioni.  
  
## <a name="see-also"></a>Vedere anche  
 [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)  
 [Procedura: Implementare partizioni dinamiche](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)  
 [Procedura: Implementare un partitioner per il partizionamento statico](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
