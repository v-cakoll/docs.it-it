---
title: Partitioner personalizzati per PLINQ e TPL
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, partitioners
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
ms.openlocfilehash: 8caea6d8a97b8c0daf7c59718479ea2e12a52d78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141562"
---
# <a name="custom-partitioners-for-plinq-and-tpl"></a>Partitioner personalizzati per PLINQ e TPL

Per parallelizzare un'operazione in un'origine dati, è essenziale *partizionare* l'origine in più sezioni a cui è possibile accedere contemporaneamente da più thread. PLINQ e Task Parallel Library (TPL) forniscono partitioner predefiniti che funzionano in modo trasparente quando si scrive una query o un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A> parallelo. Per scenari più avanzati, è possibile collegare il proprio partitioner.

## <a name="kinds-of-partitioning"></a>Tipi di partizionamento

Esistono diversi modi per partizionare un'origine dati. Negli approcci più efficienti, più thread cooperano per elaborare la sequenza di origine originale, invece di separare fisicamente l'origine in più sottosequenze. Per le matrici e le altre origini indicizzate, ad esempio le raccolte <xref:System.Collections.IList> in cui la lunghezza è nota in anticipo, il *partizionamento per intervalli* è il tipo più semplice di partizionamento. Ogni thread riceve indici iniziali e finali univoci, in modo che possa elaborare l'intervallo dell'origine senza sovrascrivere un altro thread o esserne sovrascritto. L'unico sovraccarico che si verifica nel partizionamento per intervalli è dovuto all'attività iniziale di creazione degli intervalli, dopo la quale non sono necessarie altre operazioni di sincronizzazione. Può quindi offrire buone prestazioni purché il carico di lavoro sia suddiviso equamente. Uno svantaggio del partizionamento per intervalli è che, se un thread termina prima del previsto, non può supportare il completamento degli altri thread.

Per gli elenchi collegati o altre raccolte la cui lunghezza non è nota, è possibile usare il *partizionamento in blocchi*. Nel partizionamento in blocchi ogni thread o attività in un ciclo o una query parallela usa un determinato numero di elementi di origine in un blocco, li elabora e quindi torna a recuperare altri elementi. Il partitioner garantisce che tutti gli elementi vengano distribuiti e che non siano presenti duplicati. Un blocco può essere di qualsiasi dimensione. Ad esempio, il partitioner illustrato in [Procedura: Implementare partizioni dinamiche](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md) crea blocchi che contengono un solo elemento. Purché i blocchi non siano troppo grandi, questo tipo di partizionamento esegue di per sé il bilanciamento del carico perché l'assegnazione di elementi ai thread non è predeterminata. Il partitioner, tuttavia, comporta il sovraccarico di sincronizzazione ogni volta che il thread deve ottenere un altro blocco. La quantità di operazioni di sincronizzazione eseguite in questi casi è inversamente proporzionale alle dimensioni dei blocchi.

Il partizionamento per intervalli è in generale più veloce solo quando il tempo di esecuzione del delegato è da breve a medio, l'origine ha un numero elevato di elementi e il lavoro totale di ogni partizione è quasi equivalente. Il partizionamento in blocchi è quindi in genere più veloce nella maggior parte dei casi. Nelle origini con un numero limitato di elementi o tempi di esecuzione più lunghi per il delegato le prestazioni del partizionamento in blocchi e per intervalli sono più o meno uguali.

I partitioner TPL supportano anche un numero di partizioni dinamico. Ciò significa che possono creare le partizioni immediatamente, ad esempio, quando il ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A> genera una nuova attività. Questa funzionalità consente al partitioner di essere ridimensionato con il ciclo stesso. I partitioner dinamici eseguono anche implicitamente il bilanciamento del carico. Quando si crea un partitioner personalizzato, è necessario supportare il partizionamento dinamico perché sia utilizzabile da un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A>.

### <a name="configuring-load-balancing-partitioners-for-plinq"></a>Configurazione di partitioner di bilanciamento del carico per PLINQ

Alcuni overload del metodo <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> consentono di creare un partitioner per una matrice o un'origine <xref:System.Collections.IList> e di specificare se deve provare a bilanciare il carico di lavoro tra i thread. Quando il partitioner è configurato per il bilanciamento del carico, viene usato il partizionamento in blocchi e gli elementi vengono passati a ogni partizione in piccoli blocchi quando vengono richiesti. Questo approccio consente di garantire che tutte le partizioni abbiano elementi da elaborare finché l'intero ciclo o query non viene completata. Si può usare un overload aggiuntivo per fornire il partizionamento del bilanciamento del carico di qualsiasi origine <xref:System.Collections.IEnumerable>.

Per il bilanciamento del carico le partizioni devono in genere richiedere gli elementi al partitioner relativamente spesso. Al contrario, un partitioner che esegue il partizionamento statico può assegnare tutti gli elementi a ogni partitioner contemporaneamente usando il partizionamento per intervalli o in blocchi. Ciò comporta un sovraccarico minore rispetto al bilanciamento del carico, ma l'esecuzione potrebbe richiedere più tempo se un thread termina con molte più attività rispetto agli altri. Per impostazione predefinita, quando viene passato un elemento IList o una matrice, PLINQ usa sempre il partizionamento per intervalli senza bilanciamento del carico. Per abilitare il bilanciamento del carico per PLINQ, usare il metodo `Partitioner.Create`, come illustrato nell'esempio seguente.

[!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
[!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]

Il modo migliore per stabilire se è opportuno usare il bilanciamento del carico in qualsiasi scenario specificato consiste nello sperimentare e misurare il tempo necessario per il completamento delle operazioni con carichi e configurazioni di computer rappresentativi. Il partizionamento statico, ad esempio, potrebbe offrire un considerevole aumento di velocità in un computer con solo pochi core, ma potrebbe comportare rallentamenti nei computer con un numero relativamente elevato di core.

Nella tabella seguente sono elencati gli overload disponibili del metodo <xref:System.Collections.Concurrent.Partitioner.Create%2A>. Questi partitioner non sono limitati all'uso con PLINQ o <xref:System.Threading.Tasks.Task>. Possono essere usati anche con qualsiasi costrutto parallelo personalizzato.

|Overload|Usa il bilanciamento del carico|
|--------------|-------------------------|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Sempre|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Quando l'argomento booleano viene specificato come true|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Quando l'argomento booleano viene specificato come true|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Never|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Never|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Never|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Never|

### <a name="configuring-static-range-partitioners-for-parallelforeach"></a>Configurazione di partitioner per intervalli statici per Parallel.ForEach

In un ciclo <xref:System.Threading.Tasks.Parallel.For%2A> il corpo del ciclo viene fornito al metodo come delegato. Il costo della chiamata a tale delegato è più o meno lo stesso di una chiamata a un metodo virtuale. In alcuni scenari il corpo di un ciclo parallelo potrebbe essere tanto piccolo che il costo della chiamata al delegato a ogni iterazione del ciclo diventa considerevole. In tali situazioni, è possibile usare uno degli overload <xref:System.Collections.Concurrent.Partitioner.Create%2A> per creare un'interfaccia <xref:System.Collections.Generic.IEnumerable%601> di partizioni a intervalli sugli elementi di origine. È quindi possibile passare questa raccolta di intervalli a un metodo <xref:System.Threading.Tasks.Parallel.ForEach%2A> il cui corpo è costituito da un normale ciclo `for`. Il vantaggio di questo approccio è che il costo della chiamata al delegato viene applicato una sola volta per intervallo, invece che una volta per elemento. L'esempio seguente illustra il modello di base.

[!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
[!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]

Ogni thread nel ciclo riceve la propria classe <xref:System.Tuple%602> che contiene i valori degli indici iniziali e finali dell'intervallo secondario specificato. Il ciclo `for` interno usa i valori `fromInclusive` e `toExclusive` per eseguire il ciclo direttamente sulla matrice o sull'interfaccia <xref:System.Collections.IList>.

Uno degli overload <xref:System.Collections.Concurrent.Partitioner.Create%2A> consente di specificare le dimensioni delle partizioni e il numero di partizioni. Questo overload può essere usato negli scenari in cui il lavoro per ogni elemento è così ridotto che anche una sola chiamata a un metodo virtuale per ogni elemento ha un impatto notevole sulle prestazioni.

## <a name="custom-partitioners"></a>Partitioner personalizzati

In alcuni scenari, potrebbe essere utile o anche necessario implementare un partitioner personalizzato. Si potrebbe, ad esempio, avere una classe di raccolte personalizzata che è possibile partizionare in modo più efficiente di quanto possono fare i partitioner predefiniti, in base alla propria conoscenza della struttura interna della classe. In altri casi, può rivelarsi utile creare partizioni a intervalli di dimensioni variabili a seconda del tempo necessario per elaborare gli elementi in posizioni diverse della raccolta di origine.

Per creare un partitioner personalizzato di base, derivare una classe da <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=nameWithType> ed eseguire l'override dei metodi virtuali, come illustrato nella tabella seguente.

|||
|-|-|
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|Questo metodo viene chiamato una volta dal thread principale e restituisce un'interfaccia IList(IEnumerator(TSource)). Ogni thread di lavoro nel ciclo o nella query può chiamare `GetEnumerator` sull'elenco per recuperare un'interfaccia <xref:System.Collections.Generic.IEnumerator%601> su una partizione distinta.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Restituisce `true` se si implementa <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>. In caso contrario, `false`.|
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Se <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> è `true`, si può chiamare questo metodo invece di <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|

Se i risultati devono essere ordinabili o è necessario l'accesso indicizzato agli elementi, derivare da <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> ed eseguire l'override dei metodi virtuali, come illustrato nella tabella seguente.

|||
|-|-|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|Questo metodo viene chiamato una volta dal thread principale e restituisce un'interfaccia `IList(IEnumerator(TSource))`. Ogni thread di lavoro nel ciclo o nella query può chiamare `GetEnumerator` sull'elenco per recuperare un'interfaccia <xref:System.Collections.Generic.IEnumerator%601> su una partizione distinta.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Restituisce `true` se si implementa <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>. In caso contrario, false.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|In genere, si limita a chiamare <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Se <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> è `true`, si può chiamare questo metodo invece di <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|

La tabella seguente fornisce altri dettagli su come i tre tipi di partitioner di bilanciamento del carico implementano la classe <xref:System.Collections.Concurrent.OrderablePartitioner%601>.

|Metodo/Proprietà|IList/Matrice senza bilanciamento del carico|IList/Matrice con bilanciamento del carico|IEnumerable|
|----------------------|-------------------------------------------|----------------------------------------|-----------------|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Usa il partizionamento per intervalli|Usa il partizionamento in blocchi ottimizzato per gli elenchi del partitionCount specificato|Usa il partizionamento in blocchi creando un numero statico di partizioni.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=nameWithType>|Genera un'eccezione non supportata|Usa il partizionamento in blocchi ottimizzato per gli elenchi e le partizioni dinamiche|Usa il partizionamento in blocchi creando un numero dinamico di partizioni.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Restituisce `true`.|Restituisce `true`.|Restituisce `true`.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Restituisce `true`.|Restituisce `false`.|Restituisce `false`.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Restituisce `true`.|Restituisce `true`.|Restituisce `true`.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Restituisce `false`.|Restituisce `true`.|Restituisce `true`.|

### <a name="dynamic-partitions"></a>Partizioni dinamiche

Se si prevede che il partitioner venga usato in un metodo <xref:System.Threading.Tasks.Parallel.ForEach%2A>, è necessario poter restituire un numero dinamico di partizioni. Questo significa che il partitioner può fornire un enumeratore per una nuova partizione on demand in qualsiasi momento durante l'esecuzione del ciclo. In sostanza, quando il ciclo aggiunge una nuova attività parallela, richiede una nuova partizione per tale attività. Se è necessario che i dati siano ordinabili, derivare da <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> in modo che a ogni elemento in ogni partizione venga assegnato un indice univoco.

Per altre informazioni e per un esempio, vedere [Procedura: Implementare partizioni dinamiche](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).

### <a name="contract-for-partitioners"></a>Contratto per i partitioner

Quando si implementa un partitioner personalizzato, seguire queste linee guida per assicurare la corretta interazione con PLINQ e <xref:System.Threading.Tasks.Parallel.ForEach%2A> in TPL:

- Se <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> viene chiamato con un argomento pari a zero o meno per `partitionsCount`, generare <xref:System.ArgumentOutOfRangeException>. Anche se PLINQ e TPL non passeranno mai un `partitionCount` uguale a 0, è tuttavia consigliabile proteggersi da questa possibilità.

- <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> e <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> devono restituire sempre un numero di partizioni pari a `partitionsCount`. Se il partitioner non ha dati sufficienti e non può creare tutte le partizioni richieste, il metodo deve restituire un enumeratore vuoto per ogni partizione rimanente. In caso contrario, sia PLINQ che TPL genereranno un'eccezione <xref:System.InvalidOperationException>.

- <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A> e <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> non devono mai restituire `null` (`Nothing` in Visual Basic), altrimenti PLINQ/TPL genererà un'eccezione <xref:System.InvalidOperationException>.

- I metodi che restituiscono partizioni devono sempre restituire partizioni che possano enumerare l'origine dati in modo completo e univoco. Non devono essere presenti duplicazioni nell'origine dati o elementi ignorati se non specificamente richiesto dalla progettazione del partitioner. Se questa regola non viene seguita, l'ordine dell'output potrebbe non risultare corretto.

- I getter booleani seguenti devono sempre restituire in modo accurato i valori seguenti in modo che l'ordine dell'output sia corretto:

  - `KeysOrderedInEachPartition`: ogni partizione restituisce elementi con indici di chiave crescenti.

  - `KeysOrderedAcrossPartitions`: per tutte le partizioni restituite, gli indici di chiave della partizione *i* hanno un valore superiore rispetto a quelli nella partizione *i*-1.

  - `KeysNormalized`: tutti gli indici di chiave sono a incremento progressivo costante senza gap, a partire da zero.

- Tutti gli indici devono essere univoci. Non possono essere presenti indici duplicati. Se questa regola non viene seguita, l'ordine dell'output potrebbe non risultare corretto.

- Tutti gli indici devono essere non negativi. Se questa regola non viene rispettata, PLINQ/TPL può generare eccezioni.

## <a name="see-also"></a>Vedere anche

- [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)
- [Procedura: implementare partizioni dinamiche](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)
- [Procedura: implementare un partitioner per il partizionamento statico](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
