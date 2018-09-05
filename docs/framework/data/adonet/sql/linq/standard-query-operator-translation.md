---
title: Conversione dell'operatore query standard
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
ms.openlocfilehash: fb4910e48af58463c5c851173f8e3caf4594cc3a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43672775"
---
# <a name="standard-query-operator-translation"></a>Conversione dell'operatore query standard
Gli operatori di query standard vengono convertiti in comandi SQL in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Il processore di query del database determina la semantica di esecuzione della conversione SQL.  
  
 Operatori di Query standard definiti per *sequenze*. È una sequenza *ordinati* e si basa sull'identità del riferimento per ogni elemento della sequenza. Per altre informazioni, vedere [panoramica degli operatori Query Standard](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
 SQL vengono principalmente gestiti *insiemi di valori non ordinati*. L'ordinamento è in genere un'operazione di post-elaborazione specificata in modo esplicito, che viene applicata al risultato finale di una query piuttosto che ai risultati intermedi. L'identità viene definita dai valori. Per questo motivo, le query SQL vengono riconosciute come gestiti multiset (*sacchetti*) anziché *imposta*.  
  
 Nei paragrafi seguenti vengono descritte le differenze tra gli operatori di query standard e la relativa conversione SQL per il provider SQL Server per [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
## <a name="operator-support"></a>Supporto degli operatori  
  
### <a name="concat"></a>Concat  
 Il metodo <xref:System.Linq.Enumerable.Concat%2A> viene definito per multiset ordinati in cui l'ordine del ricevente e l'ordine dell'argomento sono uguali. Il funzionamento di <xref:System.Linq.Enumerable.Concat%2A> sui multiset seguiti dall'ordine comune è analogo a quello di `UNION ALL`.  
  
 Il passaggio finale in SQL consiste nell'ordinamento prima che vengano generati i risultati. <xref:System.Linq.Enumerable.Concat%2A> non mantiene l'ordine degli argomenti. Per assicurare che l'ordine sia appropriato, è necessario ordinare i risultati di <xref:System.Linq.Enumerable.Concat%2A> in modo esplicito.  
  
### <a name="intersect-except-union"></a>Metodi Intersect, Except, Union  
 I metodi <xref:System.Linq.Enumerable.Intersect%2A> e <xref:System.Linq.Enumerable.Except%2A> sono definiti correttamente solo sui set, mentre la semantica per i tipi multiset non è definita.  
  
 Il metodo <xref:System.Linq.Enumerable.Union%2A> viene definito per i tipi multiset come concatenazione non ordinata di multiset, che corrisponde in effetti al risultato della clausola UNION ALL in SQL.  
  
### <a name="take-skip"></a>Metodi Take, Skip  
 <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> metodi sono definiti correttamente solo sugli *set ordinati*. mentre la semantica per i set non ordinati o i tipi multiset non è definita.  
  
> [!NOTE]
>  <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> presentano alcune limitazioni quando vengono usati nelle query su SQL Server 2000. Per altre informazioni, vedere la voce "Skip e Take eccezioni in SQL Server 2000" nella [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).  
  
 A causa di limitazioni relative all'ordinamento in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tenta di spostare l'ordinamento dell'argomento di questi metodi per il risultato del metodo. Si consideri ad esempio la seguente query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:  
  
 [!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
 [!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]  
  
 L'SQL generato per questo codice sposta l'ordinamento alla fine, come segue:  
  
```  
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 È quindi evidente che quando <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> vengono concatenati, tutto l'ordinamento specificato deve essere coerente. In caso contrario i risultati non saranno definiti.  
  
 Sia <xref:System.Linq.Enumerable.Take%2A> che <xref:System.Linq.Enumerable.Skip%2A> sono definiti correttamente per gli argomenti di tipo integrale costante non negativi basati sulla specifica dell'operatore di query standard.  
  
### <a name="operators-with-no-translation"></a>Operatori senza conversione  
 I metodi seguenti non vengono convertiti da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Il motivo più comune è la differenza tra i multiset non ordinati e le sequenze.  
  
|Operatori|Spiegazione logica:|  
|---------------|---------------|  
|<xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>|Le query SQL vengono eseguite su multiset, non su sequenze. `ORDER BY` deve essere l'ultima clausola applicata ai risultati. Per questo motivo non esiste una conversione di tipo generico per questi due metodi.|  
|<xref:System.Linq.Enumerable.Reverse%2A>|La conversione di questo metodo è possibile per un set ordinato, ma attualmente non viene eseguita da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|<xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A>|La conversione di questi metodi è possibile per un set ordinato, ma attualmente non viene eseguita da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|<xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|Le query SQL vengono eseguite su multiset, non sulle sequenze indicizzabili.|  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (overload con argomento predefinito)|In generale non è possibile specificare un valore predefinito per una tupla arbitraria. In alcuni casi i valori null per le tuple sono consentiti tramite outer join.|  
  
## <a name="expression-translation"></a>Conversione di espressione  
  
### <a name="null-semantics"></a>Semantica null  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non impone la semantica di confronto in SQL. Gli operatori di confronto vengono sintatticamente convertiti negli equivalenti SQL. Per questo motivo la semantica riflette la semantica SQL definita nelle impostazioni di connessione o del server. Ad esempio, due valori null sono considerati disuguali nelle impostazioni predefinite di SQL Server, ma è possibile modificare le impostazioni per modificare la semantica. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non vengono considerate le impostazioni del server durante la conversione delle query.  
  
 Un confronto con il valore letterale null viene convertito nella versione SQL appropriata (`is null` o `is not null`).  
  
 Il valore `null` nelle regole di confronto viene definito da SQL Server. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non modifica le regole di confronto.  
  
### <a name="aggregates"></a>Aggregati  
 Il metodo di aggregazione dell'operatore di query standard <xref:System.Linq.Enumerable.Sum%2A> restituisce valori zero per tutte le sequenze vuote o che contengono solo valori null. Nelle [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la semantica di SQL rimane invariata, e <xref:System.Linq.Enumerable.Sum%2A> restituisce `null` anziché zero per una sequenza vuota o una sequenza che contiene solo valori null.  
  
 Le limitazioni di SQL sui risultati intermedi vengono applicate agli aggregati in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. La somma, <xref:System.Linq.Enumerable.Sum%2A>, delle quantità di valori integer a 32 bit non viene calcolata utilizzando risultati a 64 bit ed è possibile che si verifichi un overflow per una conversione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di <xref:System.Linq.Enumerable.Sum%2A>, anche se l'implementazione dell'operatore di query standard non provoca un overflow per la corrispondente sequenza in memoria.  
  
 In modo analogo la conversione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di <xref:System.Linq.Enumerable.Average%2A> di valori integer viene calcolata come un valore `integer`, non come un valore `double`.  
  
### <a name="entity-arguments"></a>Argomenti di entità  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Consente i tipi di entità da utilizzare nel <xref:System.Linq.Enumerable.GroupBy%2A> e <xref:System.Linq.Enumerable.OrderBy%2A> metodi. Nella conversione di tali operatori l'uso di un argomento di un tipo viene considerato equivalente della specifica di tutti i membri di quel tipo. Ad esempio, il codice seguente è equivalente.  
  
 [!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
 [!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]  
  
### <a name="equatable--comparable-arguments"></a>Argomenti di uguaglianza/confronto  
 Nell'implementazione dei metodi elencati di seguito è richiesta l'uguaglianza di argomenti:  
  
 <xref:System.Linq.Enumerable.Contains%2A>  
  
 <xref:System.Linq.Enumerable.Skip%2A>  
  
 <xref:System.Linq.Enumerable.Union%2A>  
  
 <xref:System.Linq.Enumerable.Intersect%2A>  
  
 <xref:System.Linq.Enumerable.Except%2A>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta uguaglianza e confronto per *flat* argomenti, ma non per gli argomenti o contenenti sequenze. Un argomento non strutturato è un tipo di cui è possibile eseguire il mapping a una riga SQL. Una proiezione di uno o più tipi di entità, per cui è possibile determinare staticamente che non è presente una sequenza, viene considerata un argomento non strutturato.  
  
 Di seguito sono riportati esempi di argomenti non strutturati:  
  
 [!code-csharp[DLinqSQOTranslation#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
 [!code-vb[DLinqSQOTranslation#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]  
  
 Gli esempi seguenti si riferiscono ad argomenti strutturati (gerarchici).  
  
 [!code-csharp[DLinqSQOTranslation#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
 [!code-vb[DLinqSQOTranslation#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]  
  
### <a name="visual-basic-function-translation"></a>Conversione di funzioni Visual Basic  
 Le seguenti funzioni di supporto usate dal compilatore Visual Basic vengono convertite nei corrispondenti operatori e funzioni SQL:  
  
 `CompareString`  
  
 `DateTime.Compare`  
  
 `Decimal.Compare`  
  
 `IIf (in Microsoft.VisualBasic.Interaction)`  
  
 Metodi di conversione:  
  
|||||  
|-|-|-|-|  
|ToBoolean|ToSByte|ToByte|ToChar|  
|ToCharArrayRankOne|ToDate|ToDecimal|ToDouble|  
|ToInteger|ToUInteger|ToLong|ToULong|  
|ToShort|ToUShort|ToSingle|ToString|  
  
## <a name="inheritance-support"></a>Supporto dell'ereditarietà  
  
### <a name="inheritance-mapping-restrictions"></a>Limitazioni relative al mapping di ereditarietà  
 Per altre informazioni, vedere [procedura: mapping delle gerarchie di ereditarietà](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).  
  
### <a name="inheritance-in-queries"></a>Ereditarietà nelle query  
 I cast C# sono supportati solo nella proiezione. I cast usati in altri contesti non vengono convertiti e sono ignorati. A parte i nomi delle funzioni SQL, in SQL viene in effetti eseguito solo l'equivalente dell'operazione <xref:System.Convert> di Common Language Runtime (CLR). In altre parole SQL è in grado di modificare il valore di un tipo in un altro. Non è disponibile un cast CLR equivalente, in quanto non esiste un concetto che consenta di reinterpretare gli stessi bit di un altro tipo. Per questo motivo un cast C# funziona solo localmente e non viene usato in modalità remota.  
  
 Gli operatori `is` e `as` e il metodo `GetType` non sono limitati all'operatore `Select`, pertanto possono essere usati anche in altri operatori di query.  
  
## <a name="sql-server-2008-support"></a>Supporto di SQL Server 2008  
 A partire da .NET Framework versione 3.5 SP1, LINQ to SQL supporta il mapping ai nuovi tipi di data e ora introdotti con SQL Server 2008. Vi sono tuttavia alcune limitazioni relative agli operatori di query LINQ to SQL che è possibile usare quando si lavora con valori mappati a questi nuovi tipi.  
  
### <a name="unsupported-query-operators"></a>Operatori di query non supportati  
 Gli operatori di query seguenti non sono supportati per i valori mappati ai nuovi tipi di data e ora SQL Server: `DATETIME2`, `DATE`, `TIME` e `DATETIMEOFFSET`.  
  
-   `Aggregate`  
  
-   `Average`  
  
-   `LastOrDefault`  
  
-   `OfType`  
  
-   `Sum`  
  
 Per altre informazioni sul mapping di questi tipi di data e ora di SQL Server, vedere [Mapping dei tipi SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
## <a name="sql-server-2005-support"></a>Supporto di SQL Server 2005  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non supporta le seguenti funzionalità di SQL Server 2005:  
  
-   Stored procedure scritte per CLR SQL.  
  
-   Tipo definito dall'utente.  
  
-   Funzionalità di query XML.  
  
## <a name="sql-server-2000-support"></a>Supporto di SQL Server 2000  
 Le seguenti limitazioni di [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)], rispetto a [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)], influiscono sul supporto di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
### <a name="cross-apply-and-outer-apply-operators"></a>Operatori Cross Apply e Outer Apply  
 Questi operatori non sono disponibili in [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tenta una serie di operazioni di riscrittura per sostituirli con join appropriati.  
  
 `Cross Apply` e `Outer Apply` vengono generati per la navigazione tra relazioni. Il set di query per cui tali riscritture sono possibili non è esattamente definito. Per questo motivo il set minimo di query supportato per [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] è quello che non comporta la navigazione tra relazioni.  
  
### <a name="text--ntext"></a>text/ntext  
 Tipi di dati `text`  /  `ntext` non può essere utilizzato in alcune operazioni di query sulle `varchar(max)`  /  `nvarchar(max)`, che sono supportate da [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)].  
  
 Non sono disponibili risoluzioni per questa limitazione. In particolare, non è possibile usare `Distinct()` su qualsiasi risultato contenente membri di cui è stato eseguito il mapping a colonne `text` o `ntext`.  
  
### <a name="behavior-triggered-by-nested-queries"></a>Comportamento attivato dalle query annidate  
 [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] (con SP4) dello strumento di associazione presenta alcune peculiarità attivate dalle query annidate. Il set di query SQL che attiva queste peculiarità non è esattamente definito. Per questo motivo, è possibile definire il set di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query che potrebbero provocare eccezioni di SQL Server.  
  
### <a name="skip-and-take-operators"></a>Operatori Skip e Take  
 <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> presentano determinate limitazioni quando vengono usati nelle query su [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]. Per altre informazioni, vedere la voce "Skip e Take eccezioni in SQL Server 2000" nella [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).  
  
## <a name="object-materialization"></a>Materializzazione di oggetti  
 La materializzazione crea oggetti CLR da righe restituite da una o più query SQL.  
  
-   Le chiamate seguenti vengono *eseguite localmente* come parte della finestra di materializzazione:  
  
    -   Costruttori  
  
    -   Metodi `ToString` nelle proiezioni  
  
    -   Cast dei tipi nelle proiezioni  
  
-   I metodi che seguono il <xref:System.Linq.Enumerable.AsEnumerable%2A> metodo vengono *eseguito localmente*. Questo metodo non provoca l'esecuzione immediata.  
  
-   È possibile usare `struct` come tipo restituito del risultato di una query o come un membro del tipo di risultato. Le entità devono essere classi. I tipi anonimi vengono materializzati come istanze della classe, tuttavia gli struct denominati, non le entità, possono essere usati nella proiezione.  
  
-   Un membro del tipo restituito del risultato di una query può essere di tipo <xref:System.Linq.IQueryable%601> e viene materializzato come una raccolta locale.  
  
-   I metodi seguenti provocano la *materializzazione immediata* della sequenza che vengono applicati a:  
  
    -   <xref:System.Linq.Enumerable.ToList%2A>  
  
    -   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
    -   <xref:System.Linq.Enumerable.ToArray%2A>  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [Restituire o ignorare elementi in una sequenza](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 [Concatenare due sequenze](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 [Restituire la differenza dei set tra due sequenze](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 [Restituire l'intersezione tra set di due sequenze](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 [Restituire l'unione di set di due sequenze](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)
