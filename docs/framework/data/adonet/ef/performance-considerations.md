---
title: Considerazioni sulle prestazioni (Entity Framework)
ms.date: 03/30/2017
ms.assetid: 61913f3b-4f42-4d9b-810f-2a13c2388a4a
ms.openlocfilehash: 0ff018fe0d8199dcd790bcd3de18751662e0a92b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149739"
---
# <a name="performance-considerations-entity-framework"></a>Considerazioni sulle prestazioni (Entity Framework)
In questo argomento vengono descritte le caratteristiche relative alle prestazioni di ADO.NET Entity Framework e vengono illustrate alcune considerazioni per migliorare le prestazioni di applicazioni Entity Framework.  
  
## <a name="stages-of-query-execution"></a>Fasi di esecuzione di query  
 Per capire meglio le prestazioni delle query in Entity Framework, è utile capire le operazioni che si verificano quando una query viene eseguita su un modello concettuale e restituisce dati come oggetti. Nella tabella seguente viene descritta questa serie di operazioni.  
  
|Operazione|Costo relativo|Frequenza|Commenti|  
|---------------|-------------------|---------------|--------------|  
|Caricamento di metadati|Moderata|Una volta in ogni dominio dell'applicazione.|I metadati del modello e di mapping usati da Entity Framework sono caricati in un <xref:System.Data.Metadata.Edm.MetadataWorkspace>. Questi metadati sono memorizzati nella cache globalmente e sono disponibili per altre istanze di <xref:System.Data.Objects.ObjectContext> nello stesso dominio dell'applicazione.|  
|Apertura della connessione al database|Moderato<sup>1</sup>|Secondo le necessità.|Poiché una connessione aperta al database utilizza una risorsa preziosa, la Entity Framework apre e chiude la connessione al database solo in base alle esigenze. È possibile aprire anche in modo esplicito la connessione. Per ulteriori informazioni, vedere [gestione delle connessioni e delle transazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).|  
|Generazione di visualizzazioni|Alto|Una volta in ogni dominio dell'applicazione. Possono essere generate anticipatamente.|Prima di poter eseguire una query su un modello concettuale o salvare delle modifiche all'origine dati, Entity Framework deve generare un set di visualizzazioni query locali per accedere al database. A causa del costo elevato della generazione di queste visualizzazioni, è possibile generarle in anticipo e aggiungerle al progetto in fase di progettazione. Per altre informazioni, vedere [procedura: pre-generare viste per migliorare le prestazioni di esecuzione delle query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100)).|  
|Preparazione della query|Moderato<sup>2</sup>|Una volta per ogni query univoca.|Include i costi per creare il comando della query, generare un albero dei comandi basato sui metadati del modello e di mapping e definire la forma dei dati restituiti. Poiché vengono memorizzati nella cache sia i comandi delle query Entity SQL sia le query LINQ, le successive esecuzioni dei comandi della stessa query sono più veloci. Tuttavia, è possibile usare le query LINQ compilate per ridurre il costo nelle esecuzioni successive e le query compilate possono essere più efficienti di quelle LINQ che vengono memorizzate nella cache automaticamente. Per ulteriori informazioni, vedere [query compilate (LINQ to Entities)](./language-reference/compiled-queries-linq-to-entities.md). Per informazioni generali sull'esecuzione di query LINQ, vedere [LINQ to Entities](./language-reference/linq-to-entities.md). **Nota:**  LINQ to Entities le query che applicano l' `Enumerable.Contains` operatore alle raccolte in memoria non vengono memorizzate automaticamente nella cache. Inoltre, la parametrizzazione delle raccolte in memoria nelle query LINQ compilate non è consentita.|  
|Esecuzione della query|Basso<sup>2</sup>|Una volta per ogni query.|Costo dell'esecuzione del comando sull'origine dati tramite il provider di dati ADO.NET. Poiché la maggior parte delle origini dati memorizzano nella cache i piani di query, è possibile che le successive esecuzioni della stessa query siano ancor più veloci.|  
|Caricamento e convalida di tipi|Basso<sup>3</sup>|Una volta per ciascuna istanza <xref:System.Data.Objects.ObjectContext>.|I tipi vengono caricati e convalidati rispetto ai tipi definiti nel modello concettuale.|  
|Rilevamento|Basso<sup>3</sup>|Una volta per ogni oggetto restituito da una query. <sup>4</sup>|Se una query usa l'opzione di merge <xref:System.Data.Objects.MergeOption.NoTracking>, questa fase non influisce sulle prestazioni.<br /><br /> Se la query usa l'opzione di merge <xref:System.Data.Objects.MergeOption.AppendOnly>, <xref:System.Data.Objects.MergeOption.PreserveChanges> o <xref:System.Data.Objects.MergeOption.OverwriteChanges>, i risultati della query vengono rilevati nell'oggetto <xref:System.Data.Objects.ObjectStateManager>. Un oggetto <xref:System.Data.EntityKey> viene generato per ogni oggetto rilevato che la query restituisce e viene usato per creare un oggetto <xref:System.Data.Objects.ObjectStateEntry> in <xref:System.Data.Objects.ObjectStateManager>. Se è possibile trovare un oggetto <xref:System.Data.Objects.ObjectStateEntry> per <xref:System.Data.EntityKey>, viene restituito l'oggetto esistente. Se viene usata l'opzione <xref:System.Data.Objects.MergeOption.PreserveChanges> o <xref:System.Data.Objects.MergeOption.OverwriteChanges>, l'oggetto viene aggiornato prima di essere restituito.<br /><br /> Per ulteriori informazioni, vedere [risoluzione delle identità, gestione dello stato e rilevamento modifiche](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896269(v=vs.100)).|  
|Materializzazione degli oggetti|Moderato<sup>3</sup>|Una volta per ogni oggetto restituito da una query. <sup>4</sup>|Processo di lettura dell'oggetto <xref:System.Data.Common.DbDataReader> restituito, di creazione di oggetti e di impostazione di valori di proprietà che si basano sui valori in ciascuna istanza della classe <xref:System.Data.Common.DbDataRecord>. Se l'oggetto esiste già in <xref:System.Data.Objects.ObjectContext> e la query usa l'opzione di unione <xref:System.Data.Objects.MergeOption.AppendOnly> o <xref:System.Data.Objects.MergeOption.PreserveChanges>, questa fase non influisce sulle prestazioni. Per ulteriori informazioni, vedere [risoluzione delle identità, gestione dello stato e rilevamento modifiche](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896269(v=vs.100)).|  
  
 <sup>1</sup> quando un provider dell'origine dati implementa il pool di connessioni, il costo di apertura di una connessione viene distribuito nel pool. Il provider .NET per SQL Server supporta i pool di connessioni.  
  
 <sup>2</sup> aumentano i costi con maggiore complessità delle query.  
  
 <sup>3</sup> il costo totale aumenta in modo proporzionale al numero di oggetti restituiti dalla query.  
  
 <sup>4</sup> questo sovraccarico non è necessario per le query EntityClient perché le query EntityClient <xref:System.Data.EntityClient.EntityDataReader> restituiscono un anziché oggetti. Per ulteriori informazioni, vedere [Provider EntityClient per Entity Framework](entityclient-provider-for-the-entity-framework.md).  
  
## <a name="additional-considerations"></a>Ulteriori considerazioni  
 Di seguito sono illustrate altre considerazioni che possono influire sulle prestazioni di applicazioni Entity Framework.  
  
### <a name="query-execution"></a>Esecuzione di query  
 Poiché le query possono richiedere l'uso intenso delle risorse, è bene considerare in quale punto del codice e in quale computer viene eseguita una query.  
  
#### <a name="deferred-versus-immediate-execution"></a>Esecuzione posticipata e immediata  
 Quando si crea un oggetto <xref:System.Data.Objects.ObjectQuery%601> o una query LINQ, è possibile che la query non sia eseguita immediatamente. L'esecuzione della query è rinviata fino a quando i risultati non diventano necessari, ad esempio durante un'enumerazione `foreach` (C#) o `For Each` (Visual Basic) o quando è assegnata per completare una raccolta <xref:System.Collections.Generic.List%601>. L'esecuzione della query inizia immediatamente quando si chiama il metodo <xref:System.Data.Objects.ObjectQuery%601.Execute%2A> in un oggetto <xref:System.Data.Objects.ObjectQuery%601> o quando si chiama un metodo LINQ che restituisce una query Singleton, ad esempio <xref:System.Linq.Enumerable.First%2A> o <xref:System.Linq.Enumerable.Any%2A>. Per ulteriori informazioni, vedere [query di oggetti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)) ed [esecuzione di query (LINQ to Entities)](./language-reference/query-execution.md).  
  
#### <a name="client-side-execution-of-linq-queries"></a>Esecuzione di query LINQ sul lato client  
 Sebbene l'esecuzione di una query LINQ avvenga nel computer che ospita l'origine dati, è possibile che alcune parti della query LINQ vengano valutate nel computer client. Per ulteriori informazioni, vedere la sezione esecuzione dello Store di [esecuzione di query (LINQ to Entities)](./language-reference/query-execution.md).  
  
### <a name="query-and-mapping-complexity"></a>Complessità delle query e del mapping  
 La complessità di query singole e del mapping nel modello dell'entità influirà in modo significativo sulle prestazioni delle query.  
  
#### <a name="mapping-complexity"></a>Complessità del mapping  
 I modelli che sono più complessi di un mapping uno a uno tra entità nel modello concettuale e tabelle nel modello di archiviazione generano comandi più complessi rispetto ai modelli che dispongono di un mapping uno a uno.  
  
#### <a name="query-complexity"></a>Complessità delle query  
 Le query con un elevato numero di join nei comandi che sono eseguite sull'origine dati o che restituiscono una grande quantità di dati influiscono sulle prestazioni nei seguenti modi:  
  
- Le query su un modello concettuale che sembrano semplici possono comportare l'esecuzione di query più complesse sull'origine dati. Il motivo consiste nel fatto che Entity Framework traduce una query su un modello concettuale in una equivalente query sull'origine dati. Quando un singolo set di entità nel modello concettuale esegue il mapping a più tabelle nell'origine dati, o quando una relazione tra entità viene mappata a una tabella di join, è possibile che il comando di query eseguito sulla query dell'origine dati richieda uno o più join.  
  
    > [!NOTE]
    > Usare il metodo <xref:System.Data.Objects.ObjectQuery.ToTraceString%2A> della classe <xref:System.Data.Objects.ObjectQuery%601> o <xref:System.Data.EntityClient.EntityCommand> per visualizzare i comandi che sono eseguiti sull'origine dati per una data query. Per altre informazioni, vedere [procedura: visualizzare i comandi di archiviazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896348(v=vs.100)).  
  
- Le query Entity SQL annidate possono creare join nel server e possono restituire un elevato numero di righe.  
  
     Di seguito è riportato un esempio di query annidata in una clausola di proiezione:  
  
    ```sql  
    SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2
        FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1
        FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
    ```  
  
     Inoltre, tali query fanno in modo che la pipeline delle query generi un'unica query con duplicazione di oggetti tra le query annidate. Per questo motivo una singola colonna può essere duplicata più volte. In alcuni database, tra cui SQL Server, questo può causare un forte aumento delle dimensioni della tabella TempDB, con effetti negativi sulle prestazioni del server. Occorre quindi prestare attenzione quando si eseguono query annidate.  
  
- Qualsiasi query che restituisce un elevato numero di dati può causare una diminuzione delle prestazioni se il client in quel momento sta eseguendo operazioni che consumano risorse in modo proporzionale alle dimensioni del set dei risultati. In tali casi, è necessario limitare la quantità di dati restituiti dalla query. Per ulteriori informazioni, vedere [procedura: pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)).  
  
 Qualsiasi comando generato automaticamente da Entity Framework può essere più complesso degli analoghi comandi scritti in modo esplicito da un sviluppatore del database. Se è necessario avere il controllo esplicito sui comandi eseguiti sull'origine dati, si può definire un mapping a una funzione con valori di tabella o una stored procedure.  
  
#### <a name="relationships"></a>Relazioni  
 Per ottenere prestazioni ottimali nell'esecuzione delle query, è necessario definire delle relazioni tra entità sia come associazioni nel modello di entità che come relazioni logiche nell'origine dati.  
  
### <a name="query-paths"></a>Percorsi della query  
 Per impostazione predefinita, quando si esegue un <xref:System.Data.Objects.ObjectQuery%601>, gli oggetti correlati non vengono restituiti (anche se si tratta di oggetti che rappresentano le relazioni). È possibile caricare oggetti correlati in una delle tre modalità riportate di seguito:  
  
1. Impostando il percorso della query prima che venga eseguito l'oggetto <xref:System.Data.Objects.ObjectQuery%601>.  
  
2. Chiamando il metodo `Load` sulla proprietà di navigazione esposta dall'oggetto.  
  
3. Impostando l'opzione <xref:System.Data.Objects.ObjectContextOptions.LazyLoadingEnabled%2A> nell'oggetto <xref:System.Data.Objects.ObjectContext> su `true`. Si noti che questa operazione viene eseguita automaticamente quando si genera codice del livello oggetti con la [finestra di progettazione Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716685(v=vs.100)). Per ulteriori informazioni, vedere [Cenni preliminari sul codice generato](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982041(v=vs.100)).  
  
 Nella scelta dell'opzione da usare, considerare il compromesso tra il numero di richieste nel database e la quantità di dati restituiti in una singola query. Per ulteriori informazioni, vedere [caricamento di oggetti correlati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896272(v=vs.100)).  
  
#### <a name="using-query-paths"></a>Uso di percorsi della query  
 I percorsi della query definiscono il grafico degli oggetti restituiti da una query. Quando si definisce un percorso della query, è sufficiente una sola richiesta al database per restituire tutti gli oggetti definiti dal percorso. L'uso di percorsi della query può comportare l'esecuzione di comandi complessi nell'origine dati, derivanti da query di oggetto apparentemente semplici. Questo si verifica in quanto per restituire oggetti correlati in una singola query sono necessari uno o più join. Questa complessità è maggiore nelle query su un modello di entità complesso, ad esempio un'entità con ereditarietà o un percorso che include relazioni molti-a-molti.  
  
> [!NOTE]
> Usare il metodo <xref:System.Data.Objects.ObjectQuery.ToTraceString%2A> per visualizzare il comando che verrà generato da un oggetto <xref:System.Data.Objects.ObjectQuery%601>. Per altre informazioni, vedere [procedura: visualizzare i comandi di archiviazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896348(v=vs.100)).  
  
 Quando un percorso della query include troppi oggetti correlati o gli oggetti contengono troppi dati delle righe, potrebbe non essere possibile completare la query dall'origine dati. Questo si verifica se la query richiede un'archiviazione temporanea intermedia superiore alle possibilità dell'origine dati. In questo caso, è possibile ridurre la complessità della query sull'origine dati caricando in modo esplicito gli oggetti correlati.  
  
#### <a name="explicitly-loading-related-objects"></a>Caricamento esplicito di oggetti correlati  
 È possibile caricare in modo esplicito degli oggetti correlati chiamando il metodo `Load` in una proprietà di navigazione che restituisce un oggetto <xref:System.Data.Objects.DataClasses.EntityCollection%601> o <xref:System.Data.Objects.DataClasses.EntityReference%601>. Il caricamento esplicito di oggetti richiede un round trip al database ad ogni chiamata del metodo `Load`.  
  
> [!NOTE]
> Se si chiama il metodo `Load` durante l'esecuzione di ciclo in una raccolta di oggetti restituiti, come quando si usa l'istruzione `foreach` (`For Each` in Visual Basic), è necessario che il provider specifico dell'origine dati supporti più set dei risultati attivi in un'unica connessione. Per un database di SQL Server, è necessario specificare un valore di `MultipleActiveResultSets = true` nella stringa di connessione del provider.  
  
 È inoltre possibile usare il metodo <xref:System.Data.Objects.ObjectContext.LoadProperty%2A> quando non si dispone di proprietà <xref:System.Data.Objects.DataClasses.EntityCollection%601> o <xref:System.Data.Objects.DataClasses.EntityReference%601> sulle entità. Questa situazione si rivela utile quando si usano entità POCO.  
  
 Anche se il caricamento esplicito di oggetti correlati ridurrà il numero di join e ridurrà la quantità di dati ridondanti, `Load` richiede ripetute connessioni al database e questa procedura può diventare costosa se si caricano in modo esplicito molti oggetti.  
  
### <a name="saving-changes"></a>Salvataggio delle modifiche  
 Quando si chiama il metodo <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> in un oggetto <xref:System.Data.Objects.ObjectContext>, viene generato un comando di creazione, aggiornamento o eliminazione distinto per ogni oggetto aggiunto, aggiornato o eliminato nel contesto. Questi comandi vengono eseguiti sull'origine dati in una sola transazione. Come avviene per le query, le prestazioni delle operazioni di creazione, aggiornamento ed eliminazione dipendono dalla complessità del mapping nel modello concettuale.  
  
### <a name="distributed-transactions"></a>Transazioni distribuite  
 Le operazioni in una transazione esplicita che richiedono risorse gestite dal DTC (Distributed Transaction Coordinator) saranno molto più costose di un'operazione analoga che non richiede il DTC. Una promozione al DTC avverrà nelle situazioni seguenti:  
  
- Una transazione esplicita con un'operazione su un database SQL Server 2000 o altra origine dati che promuove sempre transazioni esplicite al DTC.  
  
- Transazione esplicita con un'operazione su SQL Server 2005 quando la connessione viene gestita dal Entity Framework. Questo problema si verifica perché SQL Server 2005 promuove a un DTC ogni volta che una connessione viene chiusa e riaperta all'interno di una singola transazione, che è il comportamento predefinito del Entity Framework. Questa promozione al DTC non avviene quando si utilizza SQL Server 2008. Per evitare questa promozione quando si utilizza SQL Server 2005, è necessario aprire e chiudere la connessione in modo esplicito all'interno della transazione. Per ulteriori informazioni, vedere [gestione delle connessioni e delle transazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).  
  
 Una transazione esplicita viene usata quando una o più operazioni vengono eseguite all'interno di una transazione <xref:System.Transactions>. Per ulteriori informazioni, vedere [gestione delle connessioni e delle transazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).  
  
## <a name="strategies-for-improving-performance"></a>Strategie per migliorare le prestazioni  
 È possibile migliorare le prestazioni complessive delle query in Entity Framework usando le strategie seguenti.  
  
#### <a name="pre-generate-views"></a>Generare in anticipo le visualizzazioni  
 La generazione di visualizzazioni basate su un modello di entità ha un costo significativo la prima volta che un'applicazione esegue una query. Usare EdmGen.exe per generare in anticipo visualizzazioni come un file di codice Visual Basic o C# che può essere aggiunto al progetto nella fase di progettazione. Per generare visualizzazioni pre-compilate, è inoltre possibile usare il toolkit di trasformazione dei modelli di testo. Le visualizzazioni generate in anticipo vengono convalidate in fase di esecuzione per garantirne la coerenza con la versione corrente del modello di entità specificato. Per altre informazioni, vedere [procedura: pre-generare viste per migliorare le prestazioni di esecuzione delle query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100)).
  
 Quando si usano modelli di dimensioni elevate, si applica la considerazione seguente:  
  
 Il formato dei metadati .NET limita il numero di caratteri di stringa specificabili dall'utente in un file binario a 16.777.215 (0xFFFFFF). Se si generano visualizzazioni per un modello di dimensioni molto grandi e il file di visualizzazione raggiunge tale limite, verrà visualizzato lo spazio logico per la creazione di altre stringhe utente. errore di compilazione. Questa limitazione delle dimensioni si applica a tutti i file binari gestiti. Per ulteriori informazioni, vedere il [Blog](https://docs.microsoft.com/archive/blogs/appfabriccat/solving-the-no-logical-space-left-to-create-more-user-strings-error-and-improving-performance-of-pre-generated-views-in-visual-studio-net4-entity-framework) che illustra come evitare l'errore quando si utilizzano modelli complessi e di grandi dimensioni.  
  
#### <a name="consider-using-the-notracking-merge-option-for-queries"></a>Usare l'opzione di merge NoTracking per le query  
 Esiste un costo necessario per tenere traccia degli oggetti restituiti nel contesto dell'oggetto. Il rilevamento di modifiche agli oggetti e la garanzia che più richieste per la stessa l'entità logica restituiscano la stessa istanza dell'oggetto richiedono che gli oggetti siano allegati a un'istanza <xref:System.Data.Objects.ObjectContext>. Se non si intende effettuare aggiornamenti o eliminazioni di oggetti e non è necessaria la gestione delle identità, è consigliabile <xref:System.Data.Objects.MergeOption.NoTracking> utilizzare le opzioni di Unione quando si eseguono le query.  
  
#### <a name="return-the-correct-amount-of-data"></a>Restituire la quantità corretta di dati  
 In alcuni scenari, la specifica di un percorso della query usando il metodo <xref:System.Data.Objects.ObjectQuery%601.Include%2A> è molto più veloce perché richiede meno round trip al database. Tuttavia, in altri scenari, l'esecuzione di round trip aggiuntivi al database per caricare oggetti correlati potrebbe risultare più veloce perché le query più semplici con meno join comportano meno ridondanza di dati. Per questo motivo si consiglia di testare le prestazioni usando varie modalità di recupero di oggetti correlati. Per ulteriori informazioni, vedere [caricamento di oggetti correlati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896272(v=vs.100)).  
  
 Per evitare la restituzione di troppi dati in una sola query, si può considerare di eseguire il paging dei risultati della query in gruppi più gestibili. Per ulteriori informazioni, vedere [procedura: pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)).  
  
#### <a name="limit-the-scope-of-the-objectcontext"></a>Limitare l'ambito di ObjectContext  
 Nella maggior parte dei casi, è necessario creare un'istanza <xref:System.Data.Objects.ObjectContext> all'interno di un'istruzione `using` (`Using…End Using` in Visual Basic). In questo modo le prestazioni migliorano in quanto viene garantita l'eliminazione automatica delle risorse associate al contesto dell'oggetto quando il codice esce dal blocco di istruzioni. Tuttavia, quando i controlli vengono associati a oggetti gestiti dal contesto dell'oggetto, l'istanza <xref:System.Data.Objects.ObjectContext> deve essere gestita finché l'associazione è necessaria e viene eliminata manualmente. Per ulteriori informazioni, vedere [gestione delle connessioni e delle transazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).  
  
#### <a name="consider-opening-the-database-connection-manually"></a>Aprire manualmente la connessione al database  
 Quando l'applicazione esegue una serie di query di oggetto o chiama <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> di frequente per rendere permanente le operazioni di creazione, aggiornamento ed eliminazione nell'origine dati, il Entity Framework deve aprire e chiudere continuamente la connessione all'origine dati. In queste situazioni, può essere utile aprire manualmente la connessione all'inizio di queste operazioni e chiuderla o eliminarla quando le operazioni sono completate. Per ulteriori informazioni, vedere [gestione delle connessioni e delle transazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).  
  
## <a name="performance-data"></a>Dati prestazioni  
 Alcuni dati sulle prestazioni per il Entity Framework sono pubblicati nei post seguenti nel [Blog del team di ADO.NET](https://docs.microsoft.com/archive/blogs/adonet/):  
  
- [Analisi delle prestazioni di ADO.NET Entity Framework - parte 1](https://docs.microsoft.com/archive/blogs/adonet/exploring-the-performance-of-the-ado-net-entity-framework-part-1)  
  
- [Analisi delle prestazioni di ADO.NET Entity Framework - parte 2](https://docs.microsoft.com/archive/blogs/adonet/exploring-the-performance-of-the-ado-net-entity-framework-part-2)  
  
- [Confronto di prestazioni di ADO.NET Entity Framework](https://docs.microsoft.com/archive/blogs/adonet/ado-net-entity-framework-performance-comparison)  
  
## <a name="see-also"></a>Vedi anche

- [Considerazioni sullo sviluppo e sulla distribuzione](development-and-deployment-considerations.md)
