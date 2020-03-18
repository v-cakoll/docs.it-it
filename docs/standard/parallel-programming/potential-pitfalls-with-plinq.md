---
title: Potenziali insidie con PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
ms.openlocfilehash: 3ddc0c013335e6a7b4708a5dd8be0b2247b2f60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74716247"
---
# <a name="potential-pitfalls-with-plinq"></a>Potenziali insidie con PLINQ

In molti casi, PLINQ può fornire miglioramenti significativi a livello di prestazioni su query LINQ to Objects sequenziali. Le operazioni necessarie per parallelizzare l'esecuzione delle query comportano tuttavia delle complessità che possono determinare problemi che in un codice sequenziale sono meno frequenti o addirittura assenti. In questo argomento sono elencati alcuni suggerimenti da tenere presenti quando si scrivono query PLINQ.

## <a name="dont-assume-that-parallel-is-always-faster"></a>Non dare per scontato che il parallelo sia sempre più veloce

In alcuni casi la parallelizzazione rallenta l'esecuzione di una query PLINQ rispetto all'esecuzione di una query LINQ to Objects equivalente. La regola generale di base è che per le query con pochi elementi di origine e con delegati dell'utente veloci raramente si verifica un aumento significativo della velocità di esecuzione. Poiché molti fattori influiscono sulle prestazioni, è comunque consigliabile misurare sempre i risultati effettivi prima di decidere se usare PLINQ. Per altre informazioni, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md).

## <a name="avoid-writing-to-shared-memory-locations"></a>Evitare di scrivere in posizioni di memoria condivisa

Nel codice sequenziale spesso si eseguono operazioni di lettura e scrittura su variabili o campi di classe statici. Tuttavia, ogni volta che più thread eseguono un accesso simultaneo a queste variabili, è molto probabile che si verifichino race condition. Anche se è possibile sincronizzare l'accesso alla variabile mediante l'utilizzo di blocchi, il costo di questa sincronizzazione può influire negativamente sulle prestazioni. È pertanto consigliabile evitare o almeno limitare il più possibile l'accesso allo stato condiviso in una query PLINQ.

## <a name="avoid-over-parallelization"></a>Evitare la conparallelizzazione eccessiva

Utilizzando il `AsParallel` metodo, si incorre nei costi generali di partizionamento della raccolta di origine e sincronizzazione dei thread di lavoro. I vantaggi della parallelizzazione vengono limitati ulteriormente dal numero di processori nel computer. Non si ottiene alcun aumento di velocità eseguendo più thread con vincoli di calcolo in un unico processore. È pertanto fondamentale evitare la parallelizzazione eccessiva di una query.

La situazione più comune in cui si verifica la parallelizzazione eccessiva è quando si usano query annidate, come illustrato nel frammento di codice seguente.

[!code-csharp[PLINQ#20](~/samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
[!code-vb[PLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]

In questo caso è meglio parallelizzare solo l'origine dati esterna (clienti), a meno che non sussista almeno una delle condizioni seguenti:

- È noto che l'origine dati interna (cust.Orders) è molto lunga.

- Si eseguono calcoli dispendiosi in ogni ordine. L'operazione mostrata nell'esempio non è dispendiosa.

- È noto che il sistema di destinazione presenta un numero di processori sufficiente per gestire il numero di thread che verranno prodotti dalla parallelizzazione della query su `cust.Orders`.

In ogni caso, il miglior modo per determinare la forma ottimale della query è tramite lo svolgimento di test e misure. Per altre informazioni, vedere [Procedura: Misurare le prestazioni di esecuzione delle query di PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).

## <a name="avoid-calls-to-non-thread-safe-methods"></a>Evitare le chiamate a metodi non thread-safeAvoid calls to non-thread-safe methods

La scrittura in metodi di istanza non thread-safe da una query PLINQ può comportare un danneggiamento dei dati che può passare inosservato nel programma. Può inoltre comportare la generazione di eccezioni. L'esempio seguente mostra uno scenario in cui più thread tentano di chiamare simultaneamente il metodo `FileStream.Write`. Tuttavia, la classe non supporta le chiamate simultanee.

```vb
Dim fs As FileStream = File.OpenWrite(…)
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))
```

```csharp
FileStream fs = File.OpenWrite(...);
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));
```

## <a name="limit-calls-to-thread-safe-methods"></a>Limitare le chiamate ai metodi thread-safeLimit calls to thread-safe methods

La maggior parte dei metodi statici in .NET Framework è thread-safe e può essere chiamata simultaneamente da più thread. Tuttavia, anche in questi casi, la sincronizzazione da applicare può comportare un rallentamento significativo della query.

> [!NOTE]
> Per verificare ciò basta inserire nelle query alcune chiamate a <xref:System.Console.WriteLine%2A>. Anche se questo metodo viene usato a scopo dimostrativo negli esempi della documentazione, è consigliabile evitare di usarlo nelle query PLINQ.

## <a name="avoid-unnecessary-ordering-operations"></a>Evitare operazioni di ordinamento non necessarie

Quando PLINQ esegue una query in parallelo, divide la sequenza di origine in partizioni che possono essere usate contemporaneamente su più thread. Per impostazione predefinita, l'ordine di elaborazione delle partizioni e i risultati restituiti non sono prevedibili, ad eccezione degli operatori quali, ad esempio, `OrderBy`. È possibile indicare a PLINQ di conservare l'ordine di qualsiasi sequenza di origine, ma ciò ha un impatto negativo sulle prestazioni. La procedura consigliata, se possibile, è strutturare le query in modo che non si basino sulla conservazione dell'ordine. Per altre informazioni, vedere [Conservazione dell'ordine in PLINQ](order-preservation-in-plinq.md).

## <a name="prefer-forall-to-foreach-when-it-is-possible"></a>Preferire ForAll a ForEach quando è possibile

Anche se PLINQ esegue una query su più thread, se si usano i risultati in un ciclo `foreach` (`For Each` in Visual Basic), i risultati della query devono essere uniti in un unico thread e l'enumeratore dovrà accedervi in modo seriale. In alcuni casi, questo è inevitabile. Tuttavia, se possibile, usare il metodo `ForAll` per consentire a ogni thread di restituire i propri risultati, ad esempio scrivendo in una raccolta thread-safe quale <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.

Lo stesso problema <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>vale per . In altre `source.AsParallel().Where().ForAll(...)` parole, dovrebbe `Parallel.ForEach(source.AsParallel().Where(), ...)`essere fortemente preferito a .

## <a name="be-aware-of-thread-affinity-issues"></a>Prestare attenzione ai problemi di affinità dei thread

Alcune tecnologie, ad esempio l'interoperabilità COM per i componenti apartment a thread singolo (STA, Single-Threaded Apartment), Windows Form e Windows Presentation Foundation (WPF), impongono restrizioni di affinità di thread che richiedono l'esecuzione del codice in un thread specifico. Ad esempio, sia in Windows Form sia in WPF, l'accesso a un controllo può essere eseguito solo nel thread in cui è stato creato. Se si tenta di accedere allo stato condiviso di un controllo Windows Form in una query PLINQ, viene generata un'eccezione se si esegue il debugger. Questa impostazione può essere disattivata. Tuttavia, se la query viene utilizzata nel thread dell'interfaccia `foreach` utente, è possibile accedere al controllo dal ciclo che enumera i risultati della query perché tale codice viene eseguito su un solo thread.

## <a name="dont-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a>Non presupporre che le iterazioni di ForEach, For e ForAll vengano sempre eseguite in parallelo

È importante tenere presente che le singole <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>iterazioni <xref:System.Linq.ParallelEnumerable.ForAll%2A> in un ciclo , , o possono ma non devono essere eseguite in parallelo. È pertanto necessario evitare di scrivere codice la cui correttezza dipenda dall'esecuzione parallela delle iterazioni o dall'esecuzione delle iterazioni in un particolare ordine.

Il codice seguente, ad esempio, è molto probabile che conduca a un deadlock:

```vb
Dim mre = New ManualResetEventSlim()
Enumerable.Range(0, Environment.ProcessorCount * 100).AsParallel().ForAll(Sub(j)
   If j = Environment.ProcessorCount Then
       Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)
       mre.Set()
   Else
       Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)
       mre.Wait()
   End If
End Sub) ' deadlocks
```

```csharp
ManualResetEventSlim mre = new ManualResetEventSlim();
Enumerable.Range(0, Environment.ProcessorCount * 100).AsParallel().ForAll((j) =>
{
    if (j == Environment.ProcessorCount)
    {
        Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);
        mre.Set();
    }
    else
    {
        Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);
        mre.Wait();
    }
}); //deadlocks
```

In questo esempio, un'unica iterazione imposta un evento e tutte le altre iterazioni attendono l'evento. Nessuna delle iterazioni in attesa può essere completata fino a quando non viene completata l'iterazione di impostazione dell'evento. È tuttavia possibile che le iterazioni in attesa blocchino tutti i thread utilizzati per eseguire il ciclo parallelo, prima che l'iterazione di impostazione dell'evento abbia avuto la possibilità di essere eseguita. Ciò comporta un deadlock. L'iterazione di impostazione dell'evento non verrà mai eseguita e le iterazioni in attesa non verranno mai riattivate.

In particolare, l'avanzamento di un'iterazione di un ciclo parallelo non deve dipendere da un'altra iterazione del ciclo. Se il ciclo parallelo decide di pianificare le iterazioni in sequenza ma nell'ordine opposto, si verificherà un deadlock.

## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](parallel-linq-plinq.md)
