---
title: "Informazioni sull'aumento di velocità in PLINQ"
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
helpviewer_keywords: PLINQ queries, performance tuning
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3373cb6a2c535bd7d42eb062e1f9727952f7cfb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="understanding-speedup-in-plinq"></a>Informazioni sull'aumento di velocità in PLINQ
Lo scopo principale di PLINQ consiste nel velocizzare l'esecuzione di LINQ per le query di oggetti tramite l'esecuzione di delegati di query in parallelo nei computer multicore. PLINQ offre le prestazioni migliori quando l'elaborazione di ogni elemento in una raccolta di origine è indipendente e non condiviso alcuno stato singoli delegati. Tali operazioni sono comuni in LINQ to Objects e PLINQ e spesso vengono denominate "*deliziosamente parallele*" perché si prestano facilmente alla pianificazione su più thread. Tuttavia, non tutte le query costituite interamente operazioni deliziosamente parallele. Nella maggior parte dei casi, una query implica alcuni operatori che non possono essere eseguiti o che rallentano l'esecuzione parallela. E anche le query sono interamente deliziosamente parallele, PLINQ deve comunque suddividere l'origine dati e pianificare il lavoro sul thread e in genere il merge dei risultati al termine della query. Tutte queste operazioni di aggiungono al costo computazionale della parallelizzazione. i costi di aggiunta di parallelizzazione vengono chiamati *overhead*. Per ottenere prestazioni ottimali in una query PLINQ, l'obiettivo è ottimizzare le parti deliziosamente parallele e ridurre al minimo le parti che comportano un sovraccarico. Questo articolo fornisce informazioni che consentono di scrivere query PLINQ che sono più efficaci possibile producano comunque risultati corretti.  
  
## <a name="factors-that-impact-plinq-query-performance"></a>Fattori che influiscono sulle prestazioni delle Query PLINQ  
 Nelle sezioni seguenti sono elencati alcuni dei fattori più importanti che influiscono sulle prestazioni di query parallele. Si tratta di istruzioni generali che da soli non sono sufficienti per stimare le prestazioni delle query in tutti i casi. Come sempre, è importante misurare le prestazioni effettive di query specifiche in computer con una gamma di configurazioni e carichi rappresentativi.  
  
1.  Calcolo dei costi di lavoro complessivo.  
  
     Per ottenere un aumento di velocità, una query PLINQ deve avere sufficiente lavoro deliziosamente parallelo per compensare l'overhead. Il lavoro può essere espresso come il costo di calcolo di ogni delegato moltiplicato per il numero di elementi nella raccolta di origine. Supponendo che un'operazione può essere eseguito in parallelo, calcoli più complessi costosa è, maggiore la possibilità di aumento della velocità. Ad esempio, se una funzione accetta un millisecondo, per eseguire una query sequenza oltre 1000 elementi sarà necessario un secondo per eseguire tale operazione, mentre una query parallela su un computer con quattro core potrebbe richiedere solo 250 millisecondi. Ciò produce un aumento di velocità di 750 millisecondi. Se la funzione è necessario un secondo per l'esecuzione per ogni elemento, l'aumento di velocità sarebbe 750 secondi. Se il delegato è molto costoso, PLINQ può offrire un aumento di velocità significativo con solo alcuni elementi nella raccolta di origine. Al contrario, le raccolte di origine di dimensioni ridotte con semplici delegati non sono in genere candidati validi per PLINQ.  
  
     Nell'esempio seguente, queryA è probabilmente un buon candidato per PLINQ, presupponendo che la funzione di selezione implica molto lavoro. queryB probabilmente non è un buon candidato perché non è sufficiente lavoro nell'istruzione Select, e l'overhead di parallelizzazione compensate gran parte o tutto l'aumento di velocità.  
  
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
  
2.  Il numero di core logici nel sistema (grado di parallelismo).  
  
     Questo punto è un ovvio corollario della sezione precedente, le query deliziosamente parallele vengono eseguite più velocemente nei computer con più core perché il lavoro può essere suddiviso tra più thread simultanei. La quantità totale di aumento di velocità dipende la percentuale di lavoro complessivo della query eseguibili in parallelo. Tuttavia, si presuppone che tutte le query verranno eseguito due volte come fast su un computer con otto core come un computer di quattro core. Durante l'ottimizzazione di query per ottenere prestazioni ottimali, è importante misurare i risultati effettivi nei computer con un numero di core. Questo punto è correlato al punto #1: set di dati più grande sono necessarie per sfruttare le risorse di elaborazione.  
  
3.  Il numero e tipo di operazioni.  
  
     PLINQ fornisce l'operatore AsOrdered per situazioni in cui è necessario mantenere l'ordine degli elementi nella sequenza di origine. È un costo associato con l'ordine, ma questo costo è in genere limitato. Le operazioni di Join e GroupBy allo stesso modo sovraccarico di lavoro. PLINQ offre le prestazioni migliori quando è consentita per elaborare gli elementi della raccolta di origine in qualsiasi ordine e passare al successivo operatore non appena sono pronti. Per altre informazioni, vedere [Conservazione dell'ordine in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
4.  Il modulo di esecuzione di query.  
  
     Se si archiviano i risultati di una query chiamando ToArray o ToList, i risultati di tutti i thread paralleli devono essere uniti in unica struttura di dati. Ciò comporta un costo computazionale inevitabile. Analogamente, se si esegue un'iterazione dei risultati utilizzando un ciclo foreach (For Each in Visual Basic), i risultati dei thread di lavoro devono essere serializzati sul thread dell'enumeratore. Ma se si desidera eseguire un'azione in base al risultato da ogni thread, è possibile utilizzare il metodo ForAll per eseguire questa operazione su più thread.  
  
5.  Il tipo di opzioni di unione.  
  
     PLINQ può essere configurato per il relativo output nel buffer e produrre, in blocchi o in una sola volta dopo l'intero set di risultati viene prodotta, oppure per i singoli risultati flusso non appena vengono prodotti. Il risultato precedente è ridotti i tempi di esecuzione complessivi e i risultati di quest'ultimi una riduzione della latenza tra gli elementi prodotti.  Mentre le opzioni di unione non presentano sempre un impatto significativo sulle prestazioni delle query complessive, possono avere un impatto sulle prestazioni percepite in quanto controllano per quanto tempo un utente deve attendere per verificare i risultati. Per altre informazioni, vedere [Opzioni di unione in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
6.  Il tipo di partizionamento.  
  
     In alcuni casi, una query PLINQ su una raccolta di origine indicizzabile può comportare un carico di lavoro non equilibrato. In questo caso, potrebbe essere in grado di aumentare le prestazioni delle query creando un partitioner. Per altre informazioni, vedere [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## <a name="when-plinq-chooses-sequential-mode"></a>Quando PLINQ sceglie la modalità sequenziale  
 PLINQ tenterà sempre di eseguire una query almeno stessa velocità con la query verrebbe eseguita in sequenza. Anche se PLINQ non computazionale costosa i delegati dell'utente o Qual è l'origine di input, sembra essere per determinate query "forme". In particolare, Cerca gli operatori di query o delle combinazioni di operatori che in genere una query viene eseguita più lentamente in modalità parallela. Quando trova tali forme, PLINQ per impostazione predefinita il fallback alla modalità sequenziale.  
  
 Tuttavia, dopo la misurazione delle prestazioni di query specifico, è possibile determinare che venga effettivamente eseguito più velocemente in modalità parallela. In questi casi è possibile utilizzare il <xref:System.Linq.ParallelExecutionMode.ForceParallelism?displayProperty=nameWithType> flag tramite il <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> metodo per indicare a PLINQ per parallelizzare la query. Per altre informazioni, vedere [Procedura: Specificare la modalità di esecuzione in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
 L'elenco seguente descrive le forme di query PLINQ per impostazione predefinita verranno eseguite in modalità sequenziale:  
  
-   Le query che contengono un'istruzione Select, Where indicizzata, SelectMany indicizzata o nella clausola ElementAt dopo un operatore di ordinamento o filtro che ha rimosso o riorganizzare gli indici originali.  
  
-   Query che contengono metodi Take, TakeWhile, Skip, SkipWhile operatore e in cui gli indici nella sequenza di origine non sono nell'ordine originale.  
  
-   Query che contengono Zip o SequenceEquals, a meno che in una delle origini dati non sia presente un indice originariamente ordinato e l'altra origine dati non sia indicizzabile (ad esempio un array o IList(T)).  
  
-   Query che contengono Concat, a meno che non viene applicato a origini dati indicizzabili.  
  
-   Invertire le query che contengono, a meno che non applicato a un'origine dati indicizzabili.  
  
## <a name="see-also"></a>Vedere anche  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
