---
title: Considerazioni sulla sicurezza (Entity Framework)
ms.date: 03/30/2017
ms.assetid: 84758642-9b72-4447-86f9-f831fef46962
ms.openlocfilehash: e2e1fc75049d41b50aa59092fe1aa21e8cdab659
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452487"
---
# <a name="security-considerations-entity-framework"></a>Considerazioni sulla sicurezza (Entity Framework)
In questo argomento vengono descritte considerazioni sulla sicurezza specifiche per lo sviluppo, la distribuzione e l'esecuzione di applicazioni Entity Framework. È inoltre consigliabile seguire le indicazioni per la creazione di applicazioni .NET Framework protette. Per altre informazioni, vedere [Panoramica della sicurezza](../security-overview.md).  
  
## <a name="general-security-considerations"></a>Considerazioni generali sulla sicurezza  
 Le seguenti considerazioni sulla sicurezza si applicano a tutte le applicazioni che utilizzano il Entity Framework.  
  
#### <a name="use-only-trusted-data-source-providers"></a>Usare solo provider delle origini dati attendibili.  
 Per comunicare con l'origine dati, un provider deve eseguire le operazioni seguenti:  
  
- Ricevere la stringa di connessione dal Entity Framework.  
  
- Convertire l'albero dei comandi nel linguaggio di query nativo dell'origine dati.  
  
- Assemblare e restituire i set di risultati.  
  
 Durante l'operazione di accesso, le informazioni basate sulla password dell'utente vengono passate al server tramite le librerie di rete dell'origine dati sottostante. Un provider malintenzionato può rubare le credenziali utente, generare query dannose o manomettere il set di risultati.  
  
#### <a name="encrypt-your-connection-to-protect-sensitive-data"></a>Crittografare la connessione per proteggere i dati riservati.  
 Il Entity Framework non gestisce direttamente la crittografia dei dati. Se gli utenti accedono ai dati su una rete pubblica, l'applicazione deve stabilire una connessione crittografata all'origine dati per aumentare la sicurezza. Per altre informazioni, vedere la documentazione relativa alla sicurezza dell'origine dati. Per un'origine dati SQL Server, vedere [crittografia delle connessioni a SQL Server](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms189067(v=sql.105)).  
  
#### <a name="secure-the-connection-string"></a>Proteggere la stringa di connessione.  
 La protezione dell'accesso all'origine dati è uno dei principali obiettivi da raggiungere quando si imposta la sicurezza di un'applicazione. Una stringa di connessione presenta una potenziale vulnerabilità se non è protetta o se viene costruita in modo improprio. Se le informazioni di connessione vengono archiviate in testo normale o mantenute in memoria, si rischia di compromettere l'intero sistema. Di seguito sono riportati i metodi di protezione delle stringhe di connessione consigliati.  
  
- Usare l'autenticazione di Windows con un'origine dati SQL Server.  
  
     Quando si usa l'autenticazione di Windows per connettersi a un'origine dati SQL Server, la stringa di connessione non contiene informazioni relative all'accesso e alla password.  
  
- Crittografare le sezioni dei file di configurazione tramite la configurazione protetta.  
  
     In ASP.NET è disponibile una nuova funzionalità, la configurazione protetta, che consente di crittografare le informazioni riservate in un file di configurazione. Sebbene sia stata progettata principalmente per ASP.NET, può essere usata anche per crittografare sezioni dei file di configurazione delle applicazioni Windows. Per una descrizione dettagliata delle nuove funzionalità di configurazione protetta, vedere [crittografia delle informazioni di configurazione tramite la configurazione protetta](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100)).  
  
- Archiviare le stringhe di connessione in file di configurazione protetti.  
  
     Le stringhe di connessione non devono mai essere incorporate nel codice sorgente. La possibilità di archiviarle nei file di configurazione elimina la necessità di incorporarle nel codice. Per impostazione predefinita, la procedura guidata Entity Data Model archivia le stringhe di connessione nel file di configurazione dell'applicazione. Per impedire accessi non autorizzati, è necessario proteggere tale file.  
  
- Usare i generatori di stringhe di connessione durante la creazione dinamica delle connessioni.  
  
     Se è necessario costruire stringhe di connessione in fase di runtime, usare la classe <xref:System.Data.EntityClient.EntityConnectionStringBuilder>. Questa classe del generatore di stringhe consente di impedire attacchi injection delle stringhe di connessione attraverso la convalida e l'esecuzione dell'escape delle informazioni di input non valide. Per altre informazioni, vedere [procedura: compilare una stringa di connessione EntityConnection](how-to-build-an-entityconnection-connection-string.md). Usare anche la classe del generatore di stringhe appropriata per costruire la stringa di connessione all'origine dati che fa parte della stringa di connessione Entity Framework. Per informazioni sui generatori di stringhe di connessione per i provider ADO.NET, vedere la pagina relativa ai [generatori di stringhe di connessione](../connection-string-builders.md).  
  
 Per altre informazioni, vedere [Protezione delle informazioni di connessione](../protecting-connection-information.md).  
  
#### <a name="do-not-expose-an-entityconnection-to-untrusted-users"></a>Non esporre un oggetto EntityConnection a utenti non attendibili.  
 Un oggetto <xref:System.Data.EntityClient.EntityConnection> espone la stringa di connessione della connessione sottostante. Un utente che dispone dell'accesso a un oggetto <xref:System.Data.EntityClient.EntityConnection> può modificare anche l'oggetto <xref:System.Data.ConnectionState> della connessione sottostante. La classe <xref:System.Data.EntityClient.EntityConnection>t non è di tipo thread-safe.  
  
#### <a name="do-not-pass-connections-outside-the-security-context"></a>Non passare connessioni al di fuori del contesto di sicurezza.  
 Dopo aver stabilito una connessione, non è possibile passarla al di fuori del contesto di sicurezza. Un thread con l'autorizzazione ad aprire una connessione, ad esempio, non deve archiviare la connessione in un percorso globale. Da questo percorso, infatti, potrebbe essere usata da uno script dannoso senza un'autorizzazione esplicitamente concessa.  
  
#### <a name="be-aware-that-logon-information-and-passwords-may-be-visible-in-a-memory-dump"></a>Tenere presente che le informazioni relative all'accesso e alla password possono essere visibili in un'immagine della memoria.  
 Quando nella stringa di connessione vengono fornite informazioni relative all'accesso e alla password della stringa di connessione, tali informazioni vengono conservate in memoria fino a quando le risorse non sono richieste dal processo di Garbage Collection. Diventa quindi impossibile determinare quando una stringa della password non è più in memoria. Se un'applicazione si arresta in modo anomalo, è possibile che un file di immagine della memoria contenga informazioni sulla sicurezza riservate che possono quindi diventare visibili all'utente che esegue l'applicazione e a qualsiasi utente con accesso amministrativo al computer. Usare l'autenticazione di Windows per le connessioni a Microsoft SQL Server.  
  
#### <a name="grant-users-only-the-necessary-permissions-in-the-data-source"></a>Concedere agli utenti solo le autorizzazioni necessarie nell'origine dati.  
 Un amministratore dell'origine dati deve concedere solo le autorizzazioni necessarie agli utenti. Sebbene [!INCLUDE[esql](../../../../../includes/esql-md.md)] non supporti istruzioni DML che modificano i dati, ad esempio INSERT, UPDATE o DELETE, gli utenti possono comunque accedere alla connessione all'origine dati. Un utente malintenzionato potrebbe usare questa connessione per eseguire istruzioni DML nel linguaggio nativo dell'origine dati.  
  
#### <a name="run-applications-with-the-minimum-permissions"></a>Eseguire le applicazioni con le autorizzazioni minime.  
 Quando si consente l'esecuzione di un'applicazione gestita con l'autorizzazione di attendibilità totale, il .NET Framework non limita l'accesso dell'applicazione al computer. Questo potrebbe rendere vulnerabile l'applicazione e compromettere l'intero sistema. Per utilizzare la sicurezza dall'accesso di codice e altri meccanismi di sicurezza nella .NET Framework, è necessario eseguire le applicazioni utilizzando le autorizzazioni di attendibilità parziale e il set minimo di autorizzazioni necessarie per consentire il funzionamento dell'applicazione. Le autorizzazioni di accesso al codice seguenti sono le autorizzazioni minime necessarie per l'applicazione Entity Framework:  
  
- <xref:System.Security.Permissions.FileIOPermission>: <xref:System.Security.Permissions.FileIOPermissionAccess.Write> per aprire i file di metadati specificati o <xref:System.Security.Permissions.FileIOPermissionAccess.PathDiscovery> per cercare i file di metadati in una directory.  
  
- <xref:System.Security.Permissions.ReflectionPermission>: <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> per supportare query di LINQ to Entities.  
  
- <xref:System.Transactions.DistributedTransactionPermission>: <xref:System.Security.Permissions.PermissionState.Unrestricted> da inserire in <xref:System.Transactions><xref:System.Transactions.Transaction>.  
  
- <xref:System.Security.Permissions.SecurityPermission>: <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> per serializzare le eccezioni tramite l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.  
  
- Autorizzazione per l'apertura di una connessione al database e l'esecuzione di comandi sul database, ad esempio <xref:System.Data.SqlClient.SqlClientPermission> per un database SQL Server.  
  
 Per altre informazioni, vedere [Code Access Security and ADO.NET](../code-access-security.md).  
  
#### <a name="do-not-install-untrusted-applications"></a>Non installare applicazioni non attendibili.  
 Il Entity Framework non impone alcuna autorizzazione di sicurezza e richiamerà il codice dell'oggetto dati fornito dall'utente in corso, indipendentemente dal fatto che sia o meno attendibile. Assicurarsi che l'autenticazione e l'autorizzazione del client vengano eseguite dall'archivio dati e dall'applicazione.  
  
#### <a name="restrict-access-to-all-configuration-files"></a>Limitare l'accesso a tutti i file di configurazione.  
 Un amministratore deve limitare l'accesso in scrittura a tutti i file che specificano la configurazione per un'applicazione, inclusi enterprisesec. config, Security. config, Machine. conf e il file di configurazione dell'applicazione \<*applicazione*>. exe. config.  
  
 Il nome invariante del provider è modificabile nel file app. config. L'applicazione client deve avere la responsabilità di accedere al provider sottostante tramite il modello factory del provider standard usando un nome sicuro.  
  
#### <a name="restrict-permissions-to-the-model-and-mapping-files"></a>Limitare le autorizzazioni ai file di modello e di mapping.  
 Un amministratore deve limitare l'accesso in scrittura ai file di modello e di mapping (edmx, csdl, ssdl e msl) solo agli utenti che modificano il modello o i mapping. Il Entity Framework richiede solo l'accesso in lettura a questi file in fase di esecuzione. Un amministratore deve inoltre limitare l'accesso al livello oggetti e ai file di codice sorgente di visualizzazione precompilati generati dagli strumenti di Entity Data Model.  
  
## <a name="security-considerations-for-queries"></a>Considerazioni sulla sicurezza relative alle query  
 Le considerazioni sulla sicurezza illustrate di seguito riguardano l'esecuzione di query su un modello concettuale. Tali considerazioni si applicano alle query [!INCLUDE[esql](../../../../../includes/esql-md.md)] che usano EntityClient e alle query di oggetto che usano LINQ, [!INCLUDE[esql](../../../../../includes/esql-md.md)] e i metodi del generatore di query.  
  
#### <a name="prevent-sql-injection-attacks"></a>Impedire attacchi SQL injection.  
 Le applicazioni spesso accettano input esterno, ad esempio da un utente o da un altro agente esterno, ed eseguono azioni basate su tale input. L'eventuale input derivato in modo diretto o indiretto dall'utente o da un agente esterno può includere contenuto che sfrutta la sintassi del linguaggio di destinazione per eseguire azioni non autorizzate. Quando la lingua di destinazione è un Structured Query Language (SQL), ad esempio Transact-SQL, questa manipolazione è nota come attacco SQL injection. Un utente malintenzionato può inserire comandi direttamente nella query e rilasciare una tabella di database, determinare un attacco di tipo Denial of Service o alterare in altro modo la natura dell'operazione da eseguire.  
  
- Attacchi injection di [!INCLUDE[esql](../../../../../includes/esql-md.md)]:  
  
     Gli attacchi SQL injection possono essere eseguiti in [!INCLUDE[esql](../../../../../includes/esql-md.md)] attraverso l'inserimento di input dannoso nei valori usati in un predicato della query e nei nomi del parametro. Per evitare il rischio di SQL injection, è necessario non combinare mai l'input dell'utente con il testo dei comandi [!INCLUDE[esql](../../../../../includes/esql-md.md)].  
  
     Le query [!INCLUDE[esql](../../../../../includes/esql-md.md)] accettano parametri ovunque vengano accettati i valori letterali. È opportuno utilizzare query con parametri, anziché inserire valori letterali direttamente nella query tramite un agente esterno. Si consiglia inoltre di utilizzare i [metodi del generatore di query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896238(v=vs.100)) per costruire in modo sicuro Entity SQL.  
  
- Attacchi di LINQ to Entities injection:  
  
     Sebbene la composizione di query sia possibile in LINQ to Entities, viene eseguita tramite l'API del modello a oggetti. Diversamente dalle query [!INCLUDE[esql](../../../../../includes/esql-md.md)], LINQ to Entities le query non vengono composte mediante la manipolazione o la concatenazione di stringhe e non sono soggette ad attacchi SQL injection tradizionali.  
  
#### <a name="prevent-very-large-result-sets"></a>Evitare la creazione di set di risultati molto grandi.  
 Un set di risultati molto grande può causare la chiusura del sistema client se il client sta eseguendo operazioni che usano una quantità di risorse proporzionale alla dimensione del set di risultati. Set di risultati insolitamente grandi possono essere prodotti in presenza delle condizioni seguenti:  
  
- In query eseguite su un database molto ampio che non includono condizioni di filtro adatte.  
  
- In query che creano join cartesiani sul server.  
  
- In query [!INCLUDE[esql](../../../../../includes/esql-md.md)] annidate.  
  
 Quando si accetta l'input dell'utente, è necessario assicurarsi che esso non causi l'aumento delle dimensioni del set di risultati oltre le capacità di gestione del sistema. Per limitare le dimensioni del set di risultati, è inoltre possibile utilizzare il metodo <xref:System.Linq.Queryable.Take%2A> in LINQ to Entities o l'operatore [limit](./language-reference/limit-entity-sql.md) in [!INCLUDE[esql](../../../../../includes/esql-md.md)].  
  
#### <a name="avoid-returning-iqueryable-results-when-exposing-methods-to-potentially-untrusted-callers"></a>Evitare di restituire risultati IQueryable quando si espongono metodi a chiamanti potenzialmente non attendibili.  
 Evitare di restituire tipi <xref:System.Linq.IQueryable%601> dai metodi esposti a chiamanti potenzialmente non attendibili per i motivi seguenti:  
  
- Un utente di una query che espone un tipo <xref:System.Linq.IQueryable%601> potrebbe chiamare metodi sul risultato che espongono dati sicuri o aumentano la dimensione del set di risultati. Si consideri ad esempio la firma del metodo riportata di seguito:  

    ```csharp
    public IQueryable<Customer> GetCustomer(int customerId)
    ```

    Un utente di questa query potrebbe chiamare `.Include("Orders")` sul tipo `IQueryable<Customer>` restituito per recuperare dati che la query non dovrebbe esporre. È possibile evitare questa situazione impostando il tipo restituito del metodo su <xref:System.Collections.Generic.IEnumerable%601> e chiamando un metodo (quale `.ToList()`) che materializza i risultati.  
  
- Poiché le query <xref:System.Linq.IQueryable%601> vengono eseguite quando viene eseguita un'iterazione dei risultati, un utente di una query che espone un tipo <xref:System.Linq.IQueryable%601> potrebbe intercettare le eccezioni generate. Le eccezioni potrebbero contenere informazioni non destinate all'utente.  
  
## <a name="security-considerations-for-entities"></a>Considerazioni sulla sicurezza relative alle entità  
 Le considerazioni sulla sicurezza illustrate di seguito sono valide in caso di generazione e utilizzo di tipi di entità.  
  
#### <a name="do-not-share-an-objectcontext-across-application-domains"></a>Non condividere un oggetto ObjectContext tra domini dell'applicazione.  
 La condivisione di un oggetto <xref:System.Data.Objects.ObjectContext> con più di un dominio dell'applicazione potrebbe esporre le informazioni contenute nella stringa di connessione. Al contrario, è necessario trasferire oggetti serializzati o oggetti grafici all'altro dominio dell'applicazione e quindi allegarli a un <xref:System.Data.Objects.ObjectContext> nel dominio dell'applicazione. Per ulteriori informazioni, vedere [serializzazione di oggetti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738446(v=vs.100)).  
  
#### <a name="prevent-type-safety-violations"></a>Impedire violazioni dell'indipendenza dai tipi.  
 Se l'indipendenza dai tipi viene violata, il Entity Framework non è in grado di garantire l'integrità dei dati negli oggetti. La violazione può verificarsi se si consente l'esecuzione di applicazioni non attendibili con la sicurezza dall'accesso di codice dall'attendibilità totale.  
  
#### <a name="handle-exceptions"></a>Gestire le eccezioni.  
 Accedere ai metodi e alle proprietà di un oggetto <xref:System.Data.Objects.ObjectContext> all'interno di un blocco try-catch. L'intercettazione di eccezioni impedisce alle eccezioni non gestite di esporre voci nell'oggetto <xref:System.Data.Objects.ObjectStateManager> o informazioni del modello (ad esempio i nomi di tabella) agli utenti dell'applicazione.  
  
## <a name="security-considerations-for-aspnet-applications"></a>Considerazioni sulla sicurezza relative ad applicazioni ASP.NET  

Quando si utilizzano i percorsi nelle applicazioni ASP.NET, è necessario tenere presente quanto segue.  
  
#### <a name="verify-whether-your-host-performs-path-checks"></a>Verificare se l'host esegue i controlli del percorso.  
 Quando si usa la stringa di sostituzione `|DataDirectory|` (racchiusa tra pipe), ADO.NET verifica che il percorso risolto sia supportato. "..", ad esempio, non è consentito dietro `DataDirectory`. Lo stesso controllo per la risoluzione dell'operatore radice dell'applicazione Web (`~`) viene eseguito dal processo che ospita ASP.NET. IIS esegue questo controllo, ma è possibile che host diversi da IIS non verifichino il supporto del percorso risolto. È necessario essere a conoscenza del comportamento dell'host in cui si distribuisce un'applicazione Entity Framework.  
  
#### <a name="do-not-make-assumptions-about-resolved-path-names"></a>Non dare per scontati i nomi di percorso risolti.  
 Anche se i valori a cui l'operatore radice (`~`) e la stringa di sostituzione `DataDirectory` si risolvono devono rimanere costanti durante il runtime dell'applicazione, il Entity Framework non impedisce all'host di modificare questi valori.  
  
#### <a name="verify-the-path-length-before-deployment"></a>Verificare la lunghezza del percorso prima della distribuzione.  
 Prima di distribuire un'applicazione Entity Framework, è necessario assicurarsi che i valori dell'operatore radice (~) e della stringa di sostituzione `DataDirectory` non superino i limiti della lunghezza del percorso nel sistema operativo. I provider di dati ADO.NET non assicurano che la lunghezza del percorso rientri nei limiti validi.  
  
## <a name="security-considerations-for-adonet-metadata"></a>Considerazioni sulla sicurezza relative ai metadati ADO.NET  
 Le considerazioni sulla sicurezza illustrate di seguito si applicano in caso di generazione e utilizzo di file di mapping e di modello.  
  
#### <a name="do-not-expose-sensitive-information-through-logging"></a>Non esporre informazioni riservate tramite la registrazione.  
I componenti del servizio metadati ADO.NET non registrano informazioni private. In presenza di risultati che non è possibile restituire a causa di restrizioni di accesso, i sistemi di gestione dei database e i file system devono restituire zero risultati anziché generare un'eccezione che potrebbe contenere informazioni riservate.  
  
#### <a name="do-not-accept-metadataworkspace-objects-from-untrusted-sources"></a>Non accettare oggetti MetadataWorkspace da fonti non attendibili.  
 Le applicazioni non devono accettare istanze della classe <xref:System.Data.Metadata.Edm.MetadataWorkspace> da fonti non attendibili. Al contrario, è necessario costruire in modo esplicito un'area di lavoro e popolarla a partire da tale origine.  
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](../securing-ado-net-applications.md)
- [Considerazioni sulla distribuzione](deployment-considerations.md)
- [Considerazioni sulla migrazione](migration-considerations.md)
