---
title: Informazioni sull'aumento di velocità in PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, performance tuning
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
ms.openlocfilehash: 07b5027d560a4caccc6c0a516c3f70c11df6be83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139913"
---
# <a name="understanding-speedup-in-plinq"></a>Informazioni sull'aumento di velocità in PLINQ
L'obiettivo principale di PLINQ consiste nel velocizzare l'esecuzione di query LINQ to Objects mediante l'esecuzione di delegati di query in parallelo in computer multicore. PLINQ assicura le prestazioni migliori quando l'elaborazione di ogni elemento in una raccolta di origine è indipendente, senza stati condivisi tra i singoli delegati. Tali operazioni sono comuni in LINQ to Objects e PLINQ e spesso vengono definite "*squisitamente parallele*" perché si prestano facilmente alla pianificazione su più thread. Tuttavia, non tutte le query sono costituite interamente da operazioni squisitamente parallele. Nella maggior parte dei casi una query implica alcuni operatori che non possono essere parallelizzati o che rallentano l'esecuzione parallela. Anche in caso di query che sono tutte squisitamente parallele, PLINQ deve comunque partizionare l'origine dati e pianificare il lavoro sui thread, unendo in genere i risultati al termine della query. Tutte queste operazioni incrementano i costi di calcolo della parallelizzazione, che vengono definiti *sovraccarico*. Per ottenere prestazioni ottimali in una query PLINQ, l'obiettivo è ottimizzare le parti squisitamente parallele e ridurre al minimo quelle che comportano un sovraccarico. Questo articolo fornisce informazioni che consentono di scrivere query PLINQ che siano il più efficaci possibile producendo comunque risultati corretti.  
  
## <a name="factors-that-impact-plinq-query-performance"></a>Fattori che influiscono sulle prestazioni delle query PLINQ  
 Nelle sezioni successive sono elencati alcuni dei fattori più importanti che influiscono sulle prestazioni delle query parallele. Si tratta di istruzioni generali che da sole non sono sufficienti per stimare le prestazioni delle query in tutti i casi. Come sempre, è importante misurare le prestazioni effettive di query specifiche in computer con una gamma di configurazioni e carichi rappresentativi.  
  
1. Costo di calcolo del lavoro complessivo.  
  
     Per ottenere un aumento della velocità, una query PLINQ deve avere abbastanza lavoro squisitamente parallelo da compensare il sovraccarico. Il lavoro può essere espresso come il costo di calcolo di ogni delegato moltiplicato per il numero di elementi nella raccolta di origine. Supponendo che un'operazione possa essere parallelizzata, quanto più è onerosa dal punto di vista del calcolo, maggiore sarà la possibilità di aumento della velocità. Ad esempio, se una funzione impiega un millisecondo per essere eseguita, una query sequenziale su 1000 elementi richiederà un secondo per eseguire questa operazione, mentre una query parallela in un computer con quattro core potrebbe richiedere solo 250 millisecondi. Il risultato è un aumento della velocità di 750 millisecondi. Se la funzione impiega un secondo per essere eseguita per ogni elemento, l'aumento della velocità potrebbe essere di 750 secondi. Se il delegato è molto costoso, PLINQ potrebbe assicurare un aumento della velocità significativo con solo alcuni elementi nella raccolta di origine. Al contrario, le raccolte di origine di dimensioni ridotte con delegati semplici non costituiscono in genere una scelta valida per PLINQ.  
  
     Nell'esempio seguente la queryA è con buone probabilità un candidato valido per PLINQ, presupponendo che la funzione Select comporti molto lavoro. È probabile invece che la queryB non sia un candidato valido, in quanto nell'istruzione Select non è presente un volume di lavoro sufficiente e il sovraccarico della parallelizzazione compenserà interamente o in buona parte l'aumento di velocità.  
  
    ```vb  
    Dim queryA = From num In numberList.AsParallel()  
                 Select ExpensiveFunction(num); 'good for PLINQ  
  
    Dim queryB = From num In numberList.AsParallel()  
                 Where num Mod 2 > 0  
                 Select num; 'not as good for PLINQ  
    ```  
  
    ```csharp  
    var queryA = from num in numberList.AsParallel()  
                 select ExpensiveFunction(num); //good for PLINQ  
  
    var queryB = from num in numberList.AsParallel()  
                 where num % 2 > 0  
                 select num; //not as good for PLINQ  
    ```  
  
2. Numero di core logici nel sistema (grado di parallelismo).  
  
     Questo punto è un ovvio corollario della sezione precedente. Le query squisitamente parallele vengono eseguite più velocemente nei computer con più core perché il lavoro può essere suddiviso tra più thread simultanei. L'aumento di velocità totale dipende dalla percentuale di lavoro complessivo della query parallelizzabile. Tuttavia, non bisogna partire dal presupposto che tutte le query verranno eseguite a velocità raddoppiata in un computer con otto core rispetto a uno con quattro core. In fase di ottimizzazione delle query per ottenere prestazioni di livello più elevato, è importante misurare i risultati effettivi nei computer con diversi numeri di core. Questo punto è strettamente correlato al primo: sono richiesti set di dati più grandi per sfruttare i vantaggi offerti da maggiori risorse di elaborazione.  
  
3. Numero e tipo di operazioni.  
  
     PLINQ fornisce l'operatore AsOrdered per situazioni in cui è necessario mantenere l'ordine degli elementi nella sequenza di origine. L'ordinamento prevede un costo, che tuttavia è in genere limitato. Anche GroupBy e le operazioni di join comportano un sovraccarico. PLINQ assicura le prestazioni migliori quando è consentito elaborare gli elementi nella raccolta di origine in qualsiasi ordine e passarli all'operatore successivo non appena sono pronti. Per altre informazioni, vedere [Conservazione dell'ordine in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
4. Formato di esecuzione della query.  
  
     Se si archiviano i risultati di una query chiamando ToArray o ToList, i risultati di tutti i thread paralleli devono essere uniti in un'unica struttura di dati. Ciò comporta un costo di calcolo inevitabile. Analogamente, se si scorrono i risultati usando un ciclo foreach (For Each in Visual Basic), i risultati dei thread di lavoro devono essere serializzati sul thread dell'enumeratore. Ma se si vogliono semplicemente eseguire operazioni basate sul risultato di ogni thread, è possibile usare il metodo ForAll per eseguire questa attività su più thread.  
  
5. Tipo di opzioni di unione.  
  
     PLINQ può essere configurato per il buffering dell'output e la relativa visualizzazione in blocchi o tutto in una volta dopo che è stato prodotto l'intero set di risultati oppure per lo streaming dei singoli risultati mano a mano che vengono prodotti. Nel primo caso il tempo di esecuzione complessivo diminuisce, mentre nel secondo il risultato è una riduzione della latenza tra gli elementi restituiti.  Mentre le opzioni di unione non hanno sempre un impatto significativo sulle prestazioni complessive delle query, possono incidere sulle prestazioni percepite dal momento che controllano quanto tempo deve attendere un utente per vedere i risultati. Per altre informazioni, vedere [Opzioni di unione in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
6. Tipo di partizionamento.  
  
     In alcuni casi una query PLINQ su una raccolta di origine indicizzabile può comportare un carico di lavoro non equilibrato. Quando ciò si verifica, potrebbe essere possibile aumentare le prestazioni delle query creando un partitioner personalizzato. Per altre informazioni, vedere [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## <a name="when-plinq-chooses-sequential-mode"></a>Quando PLINQ sceglie la modalità sequenziale  
 PLINQ tenterà sempre di eseguire una query almeno alla stessa velocità con cui la query verrebbe eseguita in sequenza. Anche se PLINQ non prende in considerazione il costo dei delegati dell'utente dal punto di vista del calcolo o la grandezza dell'origine di input, presta attenzione a determinate "forme" delle query. In particolare, prende in considerazione operatori di query o combinazioni di operatori che possono rallentare l'esecuzione di una query in modalità parallela. Quando vengono individuate tali forme, per impostazione predefinita PLINQ torna alla modalità sequenziale.  
  
 Tuttavia, dopo avere misurato le prestazioni di una query specifica, è possibile determinare che viene effettivamente eseguita più velocemente in modalità parallela. In questi casi è possibile usare il flag <xref:System.Linq.ParallelExecutionMode.ForceParallelism?displayProperty=nameWithType> tramite il metodo <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> per indicare a PLINQ di parallelizzare la query. Per altre informazioni, vedere [Procedura: Specificare la modalità di esecuzione in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
 Nell'elenco seguente sono riportate le forme delle query che per impostazione predefinita PLINQ eseguirà in modalità sequenziale:  
  
- Query che contengono una clausola Select, una clausola Where indicizzata, una clausola SelectMany indicizzata o una clausola ElementAt dopo un operatore di ordinamento o di filtro che ha rimosso o riorganizzato gli indici originali.  
  
- Query che contengono un operatore Take, TakeWhile, Skip, SkipWhile e in cui gli indici nella sequenza di origine non sono nell'ordine originale.  
  
- Query che contengono Zip o SequenceEquals, a meno che in una delle origini dati non sia presente un indice originariamente ordinato e l'altra origine dati non sia indicizzabile (ad esempio un array o IList(T)).  
  
- Query che contengono Concat, a meno che non sia applicato a origini dati indicizzabili.  
  
- Query che contengono Reverse, a meno che non sia applicato a un'origine dati indicizzabile.  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
