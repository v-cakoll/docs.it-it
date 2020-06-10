---
title: Problemi potenziali nel parallelismo di dati e attività
description: Informazioni sui potenziali problemi nel parallelismo di dati e attività, perché il parallelismo aggiunge complessità non rilevate nel codice sequenziale.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel programming, pitfalls
ms.assetid: 1e357177-e699-4b8f-9e49-56d3513ed128
ms.openlocfilehash: 05d934b80e60a8630db5b70e16a07c014598487a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599763"
---
# <a name="potential-pitfalls-in-data-and-task-parallelism"></a>Problemi potenziali nel parallelismo di dati e attività
In molti casi, <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> possono offrire miglioramenti significativi delle prestazioni nei normali cicli sequenziali. Le operazioni necessarie per parallelizzare il ciclo comportano tuttavia delle complessità che possono determinare problemi che in un codice sequenziale sono meno frequenti o addirittura assenti. In questo argomento sono elencati alcuni suggerimenti da tenere presenti quando si scrivono cicli paralleli.  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a>Non presupporre che l'approccio in parallelo sia sempre più veloce  
 In determinati casi l'esecuzione di un ciclo parallelo potrebbe essere più lenta dell'equivalente sequenziale. La regola generale di base è che per i cicli paralleli con poche iterazioni e con delegati dell'utente veloci raramente si verifica un aumento significativo della velocità di esecuzione. Poiché molti fattori influiscono sulle prestazioni, è comunque consigliabile misurare sempre i risultati effettivi.  
  
## <a name="avoid-writing-to-shared-memory-locations"></a>Evitare di scrivere in percorsi di memoria condivisi  
 Nel codice sequenziale spesso si eseguono operazioni di lettura e scrittura su variabili o campi di classe statici. Tuttavia, ogni volta che più thread eseguono un accesso simultaneo a queste variabili, è molto probabile che si verifichino race condition. Anche se è possibile sincronizzare l'accesso alla variabile mediante l'utilizzo di blocchi, il costo di questa sincronizzazione può influire negativamente sulle prestazioni. È pertanto consigliabile evitare o almeno limitare il più possibile l'accesso allo stato condiviso in un ciclo parallelo. Il modo migliore per eseguire questa operazione è usare gli overload di <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> che usano una variabile <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> per archiviare lo stato thread-local durante l'esecuzione del ciclo. Per altre informazioni, vedere [Procedura: Scrivere un ciclo Parallel.For con variabili di thread locali](how-to-write-a-parallel-for-loop-with-thread-local-variables.md) e [Procedura: Scrivere un ciclo Parallel.ForEach con variabili partition-local](how-to-write-a-parallel-foreach-loop-with-partition-local-variables.md).  
  
## <a name="avoid-over-parallelization"></a>Evitare parallelizzazioni eccessive  
 L'utilizzo dei cicli paralleli comporta costi di sovraccarico dovuti al partizionamento della raccolta di origine e alla sincronizzazione dei thread di lavoro. I vantaggi della parallelizzazione vengono limitati ulteriormente dal numero di processori nel computer. Non si ottiene alcun aumento di velocità eseguendo più thread con vincoli di calcolo in un unico processore. È pertanto fondamentale evitare la parallelizzazione eccessiva di un ciclo.  
  
 La situazione più comune in cui si verifica la parallelizzazione eccessiva è quando si utilizzano cicli annidati. Nella maggior parte dei casi è meglio parallelizzare solo il ciclo esterno, a meno che non sussista almeno una delle condizioni seguenti:  
  
- È noto che il ciclo interno è molto lungo.  
  
- Si eseguono calcoli dispendiosi in ogni ordine. L'operazione mostrata nell'esempio non è dispendiosa.  
  
- È noto che il sistema di destinazione presenta un numero di processori sufficiente per gestire il numero di thread che verranno prodotti dalla parallelizzazione della query su `cust.Orders`.  
  
 In ogni caso, il miglior modo per determinare la forma ottimale della query è tramite lo svolgimento di test e misure.  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a>Evitare chiamate a metodi non thread-safe  
 La scrittura in metodi di istanza non thread-safe da un ciclo parallelo può comportare un danneggiamento dei dati che può passare inosservato nel programma. Può inoltre comportare la generazione di eccezioni. L'esempio seguente mostra uno scenario in cui più thread tentano di chiamare simultaneamente il metodo <xref:System.IO.FileStream.WriteByte%2A?displayProperty=nameWithType>. Tuttavia, la classe non supporta le chiamate simultanee.  
  
 [!code-csharp[TPL_Pitfalls#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#04)]
 [!code-vb[TPL_Pitfalls#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#04)]  
  
## <a name="limit-calls-to-thread-safe-methods"></a>Limitare le chiamate ai metodi thread-safe  
 La maggior parte dei metodi statici in .NET Framework è thread-safe e può essere chiamata simultaneamente da più thread. Tuttavia, anche in questi casi, la sincronizzazione da applicare può comportare un rallentamento significativo della query.  
  
> [!NOTE]
> Per verificare ciò basta inserire nelle query alcune chiamate a <xref:System.Console.WriteLine%2A>. Anche se questo metodo viene utilizzato a scopo dimostrativo negli esempi della documentazione, è consigliabile evitare di utilizzarlo nei cicli paralleli, a meno che non sia necessario.  
  
## <a name="be-aware-of-thread-affinity-issues"></a>Tenere presente i problemi di affinità di thread  
 Alcune tecnologie, ad esempio l'interoperabilità COM per i componenti apartment a thread singolo (STA, Single-Threaded Apartment), Windows Form e Windows Presentation Foundation (WPF), impongono restrizioni di affinità di thread che richiedono l'esecuzione del codice in un thread specifico. Ad esempio, sia in Windows Form sia in WPF, l'accesso a un controllo può essere eseguito solo nel thread in cui è stato creato. Ciò significa, ad esempio, che non è possibile aggiornare un controllo elenco da un ciclo parallelo, a meno che non si configuri l'utilità di pianificazione del thread in modo che venga pianificato solo il thread UI. Per altre informazioni, vedere [Specifica di un contesto di sincronizzazione](xref:System.Threading.Tasks.TaskScheduler#specifying-a-synchronization-context).  
  
## <a name="use-caution-when-waiting-in-delegates-that-are-called-by-parallelinvoke"></a>Prestare attenzione quando si attendono delegati chiamati da Parallel.Invoke  
 In determinate circostanze Task Parallel Library rende inline un'attività, ovvero viene eseguito sull'attività nel thread attualmente in esecuzione. Per ulteriori informazioni, vedere [utilità di pianificazione delle attività](xref:System.Threading.Tasks.TaskScheduler). Questa ottimizzazione delle prestazioni può causare un deadlock in alcuni casi. Due attività potrebbero ad esempio eseguire lo stesso codice di delegato, che segnala quando si verifica un evento, quindi attende che l'altra attività segnali un evento. Se la seconda attività viene resa inline nello stesso thread del primo, e il primo entra in un ciclo di attesa, la seconda attività non sarà mai in grado di segnalare il rispettivo evento. Per evitare questa situazione, è possibile specificare un timeout sull'operazione di attesa o utilizzare costruttori di thread espliciti per garantire che un'attività non blocchi l'altra.  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a>Non presupporre che le iterazioni di Foreach, For e ForAll vengano eseguite sempre in parallelo  
 È importante tenere presente che le singole iterazioni in un ciclo <xref:System.Threading.Tasks.Parallel.For%2A>, <xref:System.Threading.Tasks.Parallel.ForEach%2A> o <xref:System.Linq.ParallelEnumerable.ForAll%2A> possono non necessariamente essere eseguite in parallelo. È pertanto necessario evitare di scrivere codice la cui correttezza dipenda dall'esecuzione parallela delle iterazioni o dall'esecuzione delle iterazioni in un particolare ordine. Il codice seguente, ad esempio, è molto probabile che conduca a un deadlock:  
  
 [!code-csharp[TPL_Pitfalls#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#01)]
 [!code-vb[TPL_Pitfalls#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#01)]  
  
 In questo esempio, un'unica iterazione imposta un evento e tutte le altre iterazioni attendono l'evento. Nessuna delle iterazioni in attesa può essere completata fino a quando non viene completata l'iterazione di impostazione dell'evento. È tuttavia possibile che le iterazioni in attesa blocchino tutti i thread utilizzati per eseguire il ciclo parallelo, prima che l'iterazione di impostazione dell'evento abbia avuto la possibilità di essere eseguita. Ciò comporta un deadlock. L'iterazione di impostazione dell'evento non verrà mai eseguita e le iterazioni in attesa non verranno mai riattivate.  
  
 In particolare, l'avanzamento di un'iterazione di un ciclo parallelo non deve dipendere da un'altra iterazione del ciclo. Se il ciclo parallelo decide di pianificare le iterazioni in sequenza ma nell'ordine opposto, si verificherà un deadlock.  
  
## <a name="avoid-executing-parallel-loops-on-the-ui-thread"></a>Evitare di eseguire cicli paralleli sul thread UI  
 È importante mantenere reattiva l'interfaccia utente dell'applicazione. Se un'operazione comporta lavoro sufficiente a garantire la parallelizzazione, è probabile che non debba essere eseguita sul thread UI.  Il carico di lavoro dell'operazione dovrebbe invece essere ripartito in modo che l'operazione venga eseguita su un thread in background. Se ad esempio si desidera utilizzare un ciclo parallelo per calcolare dati di cui deve essere eseguito il rendering in un controllo dell'interfaccia utente, è consigliabile eseguire il ciclo all'interno di un'istanza dell'attività anziché direttamente in un gestore eventi dell'interfaccia utente.  Solo quando il calcolo principale è stato completato dovrebbe essere eseguito nuovamente il marshalling dell'aggiornamento dell'interfaccia utente nel thread UI.  
  
 Se si eseguono cicli paralleli sul thread UI, evitare di aggiornare controlli dell'interfaccia utente dall'interno del ciclo. Se si prova ad aggiornare controlli dell'interfaccia utente dall'interno di un ciclo parallelo in esecuzione sul thread UI possono verificarsi un danneggiamento dello stato, eccezioni, aggiornamenti ritardati e deadlock, a seconda di come viene richiamato l'aggiornamento dell'Interfaccia utente. Nell'esempio seguente il ciclo parallelo blocca il thread UI sul quale è in esecuzione fino a che non vengono completate tutte le iterazioni. Se tuttavia un'iterazione del ciclo è in esecuzione su un thread in background (come può accadere per <xref:System.Threading.Tasks.Parallel.For%2A>), la chiamata al metodo Invoke comporta l'invio di un messaggio al thread UI e l'attesa da parte dei blocchi dell'elaborazione del messaggio. Poiché il thread UI è bloccato nell'esecuzione di <xref:System.Threading.Tasks.Parallel.For%2A>, il messaggio non potrà mai essere elaborato e si verifica un deadlock del thread UI.  
  
 [!code-csharp[TPL_Pitfalls#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#02)]
 [!code-vb[TPL_Pitfalls#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#02)]  
  
 Nell'esempio seguente viene mostrato come evitare il deadlock mediante l'esecuzione del ciclo in un'istanza dell'attività. Il thread UI non è bloccato dal ciclo e il messaggio può essere elaborato.  
  
 [!code-csharp[TPL_Pitfalls#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#03)]
 [!code-vb[TPL_Pitfalls#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#03)]  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione parallela](index.md)
- [Problemi potenziali dell'utilizzo di PLINQ](potential-pitfalls-with-plinq.md)
- [Documento contenente una panoramica dei modelli per la programmazione parallela, ovvero come comprendere e applicare modelli paralleli con .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=19222)
