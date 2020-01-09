---
title: Procedure consigliate per l'ottimizzazione dell'affidabilità
ms.date: 03/30/2017
helpviewer_keywords:
- marking locks
- rebooting databases
- denial of service attacks
- back-out code
- SQL Server [.NET Framework], reliability
- synchronization, reliability
- single-threaded COM components
- slow leaks
- suspending threads
- asynchronous exception handling
- leaked resources [.NET Framework]
- unmanaged memory
- memory, reliability
- threading [.NET Framework], reliability
- process-wide domain shared states
- shared states
- SafeHandle class, reliability
- reliability contracts [.NET Framework]
- cleanup operations
- constrained execution regions
- CERs
- finalizers, reliability
- reliability [.NET Framework]
- blocks, reliability
- finally clauses
- cross-application domain shared states
- catch blocks
- identifying locks
- writing reliable code
- impersonation
- GC.KeepAlive method
- managed threading
- locks, reliability
- STA-dependent features
- fibers
ms.assetid: cf624c1f-c160-46a1-bb2b-213587688da7
ms.openlocfilehash: bd51ea1b79ac1dbd89a862f3961cc8508a87f301
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715975"
---
# <a name="reliability-best-practices"></a>Procedure consigliate per l'ottimizzazione dell'affidabilità

Le regole seguenti relative all'affidabilità riguardano specificamente SQL Server, ma sono valide anche per qualsiasi applicazione server basata su host. È molto importante che nei server, ad esempio SQL Server, non si verifichino problemi di perdita di risorse e arresto.  Non è tuttavia possibile ottenere questo risultato scrivendo codice di annullamento per ogni metodo che modifica lo stato di un oggetto.  L'obiettivo da raggiungere non è quello di scrivere codice gestito completamente affidabile, in grado di eseguire il ripristino da qualsiasi errore in qualunque posizione tramite codice di annullamento.  Sarebbe un'attività estremamente impegnativa con scarse probabilità di successo.  Common Language Runtime (CLR) non è sempre in grado di offrire garanzie sufficienti per il codice gestito per consentire di scrivere codice perfetto.  Inoltre, a differenza di ASP.NET, SQL Server usa un solo processo che non può essere riciclato senza disattivare il database per un periodo di tempo eccessivamente lungo.

In considerazione delle garanzie limitate di CLR e dell'esecuzione di SQL Server in un unico processo, l'affidabilità si basa sull'interruzione dei thread o sul riciclo dei domini delle applicazioni, quando necessario, oltre che sull'adozione di precauzioni per evitare la perdita di risorse del sistema operativo, come handle o memoria.  Anche in questo modo, comunque, i requisiti per l'affidabilità rimangono rilevanti:

- Non devono mai verificarsi perdite di risorse del sistema operativo.

- Tutti i blocchi gestiti, in qualsiasi formato, devono essere identificati in CLR.

- Lo stato condiviso tra domini delle applicazioni non deve mai essere interrotto, in modo da consentire un facile funzionamento del riciclo di <xref:System.AppDomain>.

Anche se a livello teorico è possibile scrivere codice gestito per gestire le eccezioni <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> e <xref:System.OutOfMemoryException>, non è ragionevole aspettarsi che gli sviluppatori scrivano codice con un tale livello di affidabilità per un'intera applicazione.  Per questo motivo, le eccezioni fuori banda determinano l'interruzione del thread in esecuzione. Se il thread interrotto sta modificando uno stato condiviso, come si può capire dal fatto che il thread applica un blocco, l'oggetto <xref:System.AppDomain> viene scaricato.  Quando un metodo che sta modificando lo stato condiviso viene terminato, lo stato risulta danneggiato perché non è possibile scrivere codice di annullamento affidabile per gli aggiornamenti dello stato condiviso.

In .NET Framework versione 2.0 l'unico host che presenta requisiti di affidabilità è SQL Server.  Se l'assembly è destinato all'esecuzione su SQL Server, è opportuno verificare che i requisiti di affidabilità siano soddisfatti per ogni parte dell'assembly, anche se è prevista la disabilitazione di funzionalità specifiche durante l'esecuzione nel database.  Questa verifica è necessaria perché il motore di analisi del codice esamina il codice a livello di assembly e non è in grado di distinguere il codice disabilitato. In ambito di programmazione per SQL Server è anche necessario tenere presente che SQL Server esegue tutti i componenti in un unico processo e che il riciclo di <xref:System.AppDomain> viene usato per la pulizia di tutte le risorse, come la memoria e gli handle del sistema operativo.

Per il codice di annullamento, non è possibile basarsi su finalizzatori, distruttori o blocchi `try/finally`. Questi elementi potrebbero venire interrotti o non venire chiamati.

Possono venire generate eccezioni asincrone in posizioni impreviste, ipoteticamente in ogni istruzione del linguaggio macchina: <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> e <xref:System.OutOfMemoryException>.

I thread gestiti non sono necessariamente thread Win32 in SQL, ma possono anche essere fiber.

La modifica dello stato condiviso modificabile tra domini delle applicazioni o a livello di processo è un'operazione estremamente rischiosa e deve essere evitata, quando possibile.

Le condizioni di memoria insufficiente non sono rare in SQL Server.

Se le librerie ospitate in SQL Server non aggiornano correttamente il loro stato condiviso, è molto probabile che il codice non venga ripristinato fino al riavvio del database.  In alcuni casi estremi, ciò potrebbe provocare un errore nel processo SQL Server e, di conseguenza, il riavvio del database.  Il riavvio del database può rendere non disponibile un sito Web o può influire sui processi operativi aziendali, con effetti negativi sulla disponibilità.  Una perdita lenta di risorse del sistema operativo, come handle o memoria, può impedire al server di allocare gli handle, senza alcuna possibilità di ripristino, oppure può determinare una lenta riduzione delle prestazioni del server e della disponibilità delle applicazioni dei clienti.  È chiaramente opportuno evitare scenari di questo tipo.

## <a name="best-practice-rules"></a>Regole procedure consigliate

Nell'introduzione è stato illustrato cosa è necessario intercettare con la revisione del codice gestito in esecuzione nel server per aumentare la stabilità e l'affidabilità del framework. Tutti questi controlli, che sono in genere consigliati in qualsiasi situazione, sono indispensabili nel server.

In caso di deadlock o di vincoli delle risorse, SQL Server interrompe un thread o elimina un oggetto <xref:System.AppDomain>.  Quando ciò accade, è garantita solo l'esecuzione del codice di annullamento in un'area a esecuzione vincolata (CER, Constrained Execution Region).

### <a name="use-safehandle-to-avoid-resource-leaks"></a>Utilizzare SafeHandle per evitare perdite di risorse

In caso di scaricamento di un oggetto <xref:System.AppDomain>, non è possibile dipendere da blocchi `finally` o dall'esecuzione di finalizzatori, quindi è importante astrarre l'accesso a tutte le risorse del sistema operativo tramite la classe <xref:System.Runtime.InteropServices.SafeHandle> invece di <xref:System.IntPtr>, <xref:System.Runtime.InteropServices.HandleRef> o classi simili. In questo modo, CLR può tenere traccia degli handle usati e chiuderli, anche in caso di eliminazione di <xref:System.AppDomain>.  <xref:System.Runtime.InteropServices.SafeHandle> userà un finalizzatore critico, che verrà sempre eseguito da CLR.

L'handle del sistema operativo rimane archiviato nell'handle Safe dal momento della creazione fino a quello del rilascio.  In nessun momento può verificarsi un'eccezione <xref:System.Threading.ThreadAbortException> con perdita di un handle.  Inoltre, la funzionalità platform invoke eseguirà il conteggio dei riferimenti dell'handle, consentendo di tenerne traccia per l'intera durata dell'handle e impedendo un eventuale problema di sicurezza dovuto a una race condition tra `Dispose` e un metodo che fa attualmente uso dell'handle.

La maggior parte delle classi che attualmente hanno un finalizzatore solo per eliminare un handle del sistema operativo non ne avrà più bisogno. Il finalizzatore sarà invece incluso nella classe derivata <xref:System.Runtime.InteropServices.SafeHandle>.

Si noti che <xref:System.Runtime.InteropServices.SafeHandle> non sostituisce <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>.  L'eliminazione esplicita delle risorse del sistema operativo offre ancora potenziali vantaggi in termini di prestazioni e di risoluzione di conflitti di risorse.  Basta considerare che i blocchi `finally` che eseguono l'eliminazione esplicita delle risorse potrebbero non venire eseguiti completamente.

<xref:System.Runtime.InteropServices.SafeHandle> consente di implementare un metodo <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> che esegue le operazioni appropriate per liberare l'handle, ad esempio passando lo stato a una routine di rilascio degli handle del sistema operativo oppure liberando un set di handle in un ciclo.  L'esecuzione di questo metodo è garantita da CLR.  È responsabilità dell'autore dell'implementazione di <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> garantire che l'handle venga rilasciato in qualsiasi circostanza. In caso contrario, l'handle andrà perso e ciò spesso causa una perdita delle risorse native associate all'handle. È quindi fondamentale strutturare le classi derivate di <xref:System.Runtime.InteropServices.SafeHandle> in modo che l'implementazione di <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> non richieda l'allocazione di alcuna risorsa che potrebbe non essere disponibile al momento della chiamata. Si noti che è consentito chiamare metodi che possono generare errori nell'ambito dell'implementazione di <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>, a condizione che il codice possa gestire tali errori e rispettare il contratto per rilasciare l'handle nativo. Ai fini del debug, <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> restituisce un valore <xref:System.Boolean>, che può essere impostato su `false` qualora si verifichi un errore irreversibile che impedisce il rilascio della risorsa. In questo modo, verrà attivato l'assistente al debug gestito [releaseHandleFailed](../debug-trace-profile/releasehandlefailed-mda.md), se abilitato, per aiutare nell'identificazione del problema. Non ci saranno altri effetti sul runtime. Il metodo <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> non verrà chiamato di nuovo per la stessa risorsa e, di conseguenza, l'handle andrà perso.

L'oggetto <xref:System.Runtime.InteropServices.SafeHandle> non è appropriato in determinati contesti.  Poiché il metodo <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> può essere eseguito in un thread finalizzatore <xref:System.GC>, non è opportuno eseguire il wrapping in un oggetto <xref:System.Runtime.InteropServices.SafeHandle> degli handle che devono essere rilasciati in un thread specifico.

Gli oggetti Runtime Callable Wrapper (RCW) possono essere eliminati da CLR senza codice aggiuntivo.  Il codice che usa platform invoke e tratta un oggetto COM come `IUnknown*` o <xref:System.IntPtr> deve essere riscritto in modo da usare un oggetto RCW.  L'oggetto <xref:System.Runtime.InteropServices.SafeHandle> potrebbe non essere adatto in questo scenario a causa di un possibile callback al codice gestito da parte di un metodo di rilascio non gestito.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Usare <xref:System.Runtime.InteropServices.SafeHandle> per incapsulare le risorse del sistema operativo. Non usare <xref:System.Runtime.InteropServices.HandleRef> o campi di tipo <xref:System.IntPtr>.

### <a name="ensure-finalizers-do-not-have-to-run-to-prevent-leaking-operating-system-resources"></a>Verificare che non sia necessario eseguire i finalizzatori per evitare perdite di risorse del sistema operativo

Esaminare accuratamente i finalizzatori per accertarsi che, anche se non vengono eseguiti, non si verifichi la perdita di una risorsa critica del sistema operativo.  A differenza di quanto avviene durante il normale scaricamento di <xref:System.AppDomain> quando l'applicazione è in esecuzione in uno stato stabile o quando viene arrestato un server, come SQL Server, durante uno scaricamento improvviso di <xref:System.AppDomain>, gli oggetti non vengono finalizzati.  Assicurarsi che non si verifichi una perdita di risorse in caso di scaricamento improvviso, perché la corretta esecuzione di un'applicazione non può essere garantita, ma è indispensabile che venga mantenuta l'integrità del server evitando la perdita di risorse.  Usare <xref:System.Runtime.InteropServices.SafeHandle> per liberare le risorse del sistema operativo.

### <a name="ensure-that-finally-clauses-do-not-have-to-run-to-prevent-leaking-operating-system-resources"></a>Verificare che non sia necessario eseguire le clausole finally per evitare perdite di risorse del sistema operativo

Poiché non è possibile garantire che le clausole `finally` vengano eseguite fuori dalle aree a esecuzione vincolata, gli sviluppatori di librerie non devono basarsi sul codice all'interno di un blocco `finally` per liberare le risorse non gestite.  A questo scopo, si consiglia di usare <xref:System.Runtime.InteropServices.SafeHandle>.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Per la pulizia delle risorse del sistema operativo, usare <xref:System.Runtime.InteropServices.SafeHandle> invece di `Finalize`. Non usare <xref:System.IntPtr>. Usare <xref:System.Runtime.InteropServices.SafeHandle> per incapsulare le risorse. Se è necessario eseguire la clausola finally, inserirla in un'area a esecuzione vincolata.

### <a name="all-locks-should-go-through-existing-managed-locking-code"></a>Tutti i blocchi devono passare attraverso il codice di blocco gestito esistente

CLR deve essere in grado di identificare i casi di blocco del codice, in modo da stabilire se procedere all'eliminazione dell'oggetto <xref:System.AppDomain> invece di interrompere semplicemente il thread.  L'interruzione del thread può risultare pericolosa perché i dati elaborati dal thread possono rimanere in uno stato incoerente. È pertanto necessario riciclare l'intero oggetto <xref:System.AppDomain>.  La mancata identificazione di un blocco può causare deadlock o risultati non corretti. Per identificare le aree di blocco, usare i metodi <xref:System.Threading.Thread.BeginCriticalRegion%2A> e <xref:System.Threading.Thread.EndCriticalRegion%2A>.  Si tratta di metodi statici inclusi nella classe <xref:System.Threading.Thread> che si applicano solo al thread corrente e aiutano a impedire che un thread modifichi il conteggio dei blocchi di un altro thread.

Poiché <xref:System.Threading.Monitor.Enter%2A> e <xref:System.Threading.Monitor.Exit%2A> hanno questa notifica CLR incorporata, si consiglia il loro uso. Lo stesso vale per l'[istruzione lock](../../csharp/language-reference/keywords/lock-statement.md), che usa questi metodi.

Gli altri meccanismi di blocco, ad esempio gli spinlock e l'oggetto <xref:System.Threading.AutoResetEvent>, devono chiamare questi metodi per notificare a CLR l'ingresso in una sezione critica.  Questi metodi non acquisiscono alcun blocco, ma informano CLR che il codice è in esecuzione in una sezione critica e che l'interruzione del thread può causare problemi di incoerenza dello stato condiviso.  Se è stato definito un tipo di blocco specifico, ad esempio una classe <xref:System.Threading.ReaderWriterLock> personalizzata, usare questi metodi di conteggio dei blocchi.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Contrassegnare e identificare tutti i blocchi usando <xref:System.Threading.Thread.BeginCriticalRegion%2A> e <xref:System.Threading.Thread.EndCriticalRegion%2A>. Non usare <xref:System.Threading.Interlocked.CompareExchange%2A>, <xref:System.Threading.Interlocked.Increment%2A> e <xref:System.Threading.Interlocked.Decrement%2A> in un ciclo.  Non eseguire platform invoke per le varianti Win32 di questi metodi.  Non usare <xref:System.Threading.Thread.Sleep%2A> in un ciclo.  Non usare campi volatili.

### <a name="cleanup-code-must-be-in-a-finally-or-a-catch-block-not-following-a-catch"></a>Il codice di pulizia deve trovarsi in un blocco finally o catch, non dopo un catch

Il codice di pulizia non deve mai seguire un blocco `catch`, ma deve essere inserito in un blocco `finally` o nel blocco `catch` stesso. Questa dovrebbe essere la normale procedura da seguire. Un blocco `finally` è in genere preferibile perché esegue lo stesso codice sia quando viene generata un'eccezione che quando viene raggiunta normalmente la fine del blocco `try`.  Se viene generata un'eccezione imprevista, ad esempio <xref:System.Threading.ThreadAbortException>, il codice di pulizia non viene eseguito.  Per evitare perdite, è opportuno eseguire il wrapping in un oggetto <xref:System.Runtime.InteropServices.SafeHandle> delle risorse non gestite di cui viene normalmente eseguita la pulizia in un blocco `finally`.  Si noti che per eliminare in modo efficace gli oggetti, inclusi gli handle, è possibile usare la parola chiave `using` C#.

Anche se il riciclo di <xref:System.AppDomain> può pulire le risorse sul thread finalizzatore, è comunque importante inserire il codice di pulizia nella posizione corretta. Si noti che, se un thread riceve un'eccezione asincrona senza applicare un blocco, CLR tenta di terminare il thread senza eseguire il riciclo di <xref:System.AppDomain>.  Assicurarsi che la pulizia delle risorse avvenga il prima possibile per aumentarne la disponibilità e gestire meglio la durata. Se non si chiude in modo esplicito l'handle di un file in un percorso di codice di errore e si attende la pulizia da parte del finalizzatore <xref:System.Runtime.InteropServices.SafeHandle>, alla successiva esecuzione, il codice potrebbe non riuscire ad accedere allo stesso file se il finalizzatore non è già stato eseguito.  Per questo motivo è opportuno, anche se non obbligatorio, verificare che il codice di pulizia sia presente e funzioni correttamente, in modo da consentire un ripristino più semplice e veloce dagli errori.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Il codice di pulizia dopo `catch` deve trovarsi in un blocco `finally`. Inserire le chiamate per l'eliminazione delle risorse in un blocco finally. I blocchi `catch` devono terminare in un elemento throw o rethrow. Anche se verranno generate eccezioni, ad esempio durante la verifica della possibilità di stabilire una connessione di rete, in cui può venire generata una di numerose eccezioni possibili, qualsiasi codice che in circostanze normali richiede l'intercettazione di un certo numero di eccezioni dovrebbe indicare la necessità di eseguire test per controllare se l'elaborazione avrà esito positivo.

### <a name="process-wide-mutable-shared-state-between-application-domains-should-be-eliminated-or-use-a-constrained-execution-region"></a>Lo stato condiviso modificabile a livello di processo tra i domini applicazione deve essere eliminato o usare un'area a esecuzione vincolata

Come indicato nell'introduzione, può essere molto difficile scrivere codice gestito che monitora lo stato condiviso a livello di processo tra domini delle applicazioni in modo affidabile.  Per stato condiviso a livello di processo si intende qualsiasi tipo di struttura dei dati condivisa tra domini delle applicazioni, nel codice Win32, all'interno di CLR o nel codice gestito tramite la comunicazione remota.  Uno stato condiviso modificabile è molto difficile da scrivere correttamente nel codice gestito e uno stato condiviso statico richiede estrema attenzione.  Se c'è uno stato condiviso a livello di processo o di computer, trovare un modo per eliminarlo oppure proteggerlo tramite un'area a esecuzione vincolata.  Si noti che qualsiasi libreria con stato condiviso non identificato o non corretto può determinare l'arresto anomalo di un host, ad esempio SQL Server, che richiede lo scaricamento pulito di <xref:System.AppDomain>.

Se il codice usa un oggetto COM, evitare di condividere tale oggetto COM tra domini delle applicazioni.

### <a name="locks-do-not-work-process-wide-or-between-application-domains"></a>I blocchi non funzionano a livello di processo o tra domini dell'applicazione.

In precedenza, <xref:System.Threading.Monitor.Enter%2A> e l'[istruzione lock](../../csharp/language-reference/keywords/lock-statement.md) venivano usati per creare blocchi di processo globali.  Ciò si verifica, ad esempio, quando si applica un blocco sulle classi Agile di <xref:System.AppDomain>, ad esempio le istanze di <xref:System.Type> da assembly non condivisi, gli oggetti <xref:System.Threading.Thread>, le stringhe centralizzate e alcune stringhe condivise tra domini delle applicazioni tramite la comunicazione remota.  Questi blocchi non sono più a livello di processo.  Per identificare la presenza di un blocco tra diversi domini delle applicazioni a livello di processo, determinare se il codice all'interno del blocco fa uso di risorse esterne persistenti, ad esempio un file su disco o eventualmente un database.

Si noti che l'acquisizione di un blocco all'interno di un oggetto <xref:System.AppDomain> può provocare problemi se il codice protetto usa una risorsa esterna, perché il codice può essere eseguito simultaneamente tra più domini delle applicazioni.  Ciò può costituire un problema quando si scrive in un file di log o si esegue il binding a un socket per l'intero processo.  Queste modifiche indicano che non esiste un modo semplice, usando il codice gestito, per ottenere un blocco globale del processo, se non usando un'istanza denominata di <xref:System.Threading.Mutex> o <xref:System.Threading.Semaphore>.  Creare codice che non viene eseguito simultaneamente in due domini delle applicazioni oppure usare la classe <xref:System.Threading.Mutex> o <xref:System.Threading.Semaphore>.  Se non è possibile modificare il codice esistente, non usare un mutex denominato Win32 per ottenere la sincronizzazione, perché l'esecuzione in modalità fiber implica l'impossibilità di garantire che un mutex venga acquisito e rilasciato dallo stesso thread del sistema operativo.  È necessario usare la classe gestita <xref:System.Threading.Mutex>, una classe denominata <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.AutoResetEvent> oppure una classe <xref:System.Threading.Semaphore> per sincronizzare il blocco del codice in modo che CLR ne sia consapevole invece che sincronizzare il blocco tramite codice non gestito.

#### <a name="avoid-locktypeofmytype"></a>Evitare lock(typeof(MyType))

Anche gli oggetti <xref:System.Type> pubblici e privati inclusi negli assembly condivisi, con una sola copia del codice condivisa tra tutti i domini delle applicazioni, presentano problemi.  Per gli assembly condivisi c'è un'unica istanza di un oggetto <xref:System.Type> per processo e, di conseguenza, più domini delle applicazioni condividono la stessa istanza di <xref:System.Type>.  L'acquisizione di un blocco su un'istanza di <xref:System.Type> ha effetto sull'intero processo e non solo su <xref:System.AppDomain>.  Se un oggetto <xref:System.AppDomain> acquisisce un blocco su un oggetto <xref:System.Type>, il thread viene interrotto improvvisamente senza rilasciare il blocco.  Tale blocco può quindi causare una situazione di deadlock in altri domini delle applicazioni.

Una tecnica efficace per acquisire blocchi nei metodi statici consiste nell'aggiungere al codice un oggetto statico di sincronizzazione interna.  Questo oggetto può essere inizializzato nel costruttore della classe, se presente, oppure nel modo seguente:

```csharp
private static Object s_InternalSyncObject;
private static Object InternalSyncObject
{
    get
    {
        if (s_InternalSyncObject == null)
        {
            Object o = new Object();
            Interlocked.CompareExchange(
                ref s_InternalSyncObject, o, null);
        }
        return s_InternalSyncObject;
    }
}
```

Quando si acquisisce un blocco, usare la proprietà `InternalSyncObject` per ottenere un oggetto a cui applicare il blocco.  Non è necessario usare questa proprietà se l'oggetto di sincronizzazione interna è stato inizializzato nel costruttore della classe.  Il codice di inizializzazione del blocco per la doppia verifica dovrebbe essere simile all'esempio seguente:

```csharp
public static MyClass SingletonProperty
{
    get
    {
        if (s_SingletonProperty == null)
        {
            lock(InternalSyncObject)
            {
                // Do not use lock(typeof(MyClass))
                if (s_SingletonProperty == null)
                {
                    MyClass tmp = new MyClass(…);
                    // Do all initialization before publishing
                    s_SingletonProperty = tmp;
                }
            }
        }
        return s_SingletonProperty;
    }
}
```

#### <a name="a-note-about-lockthis"></a>Nota sul blocco (this)

In genere è possibile acquisire un blocco su un singolo oggetto accessibile pubblicamente.  Se tuttavia si tratta di un oggetto Singleton, che può causare il deadlock di un intero sottosistema, prendere in considerazione anche la possibilità di usare lo schema progettuale illustrato in precedenza.  Un blocco sul singolo oggetto <xref:System.Security.SecurityManager> può ad esempio causare un deadlock in <xref:System.AppDomain>, rendendo inutilizzabile l'intero oggetto <xref:System.AppDomain>. È consigliabile non acquisire alcun blocco su un oggetto accessibile pubblicamente di questo tipo.  Tuttavia, un blocco su una singola matrice o raccolta non rappresenta in genere un problema.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Non acquisire blocchi su tipi che possono essere usati tra domini delle applicazioni o che non hanno una forte identità. Non chiamare <xref:System.Threading.Monitor.Enter%2A> su un oggetto <xref:System.Type>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.PropertyInfo>, <xref:System.String>, <xref:System.ValueType>, <xref:System.Threading.Thread> o su qualsiasi oggetto che deriva da <xref:System.MarshalByRefObject>.

### <a name="remove-gckeepalive-calls"></a>Rimuovere GC. Chiamate KeepAlive

Una quantità significativa di codice esistente non usa <xref:System.GC.KeepAlive%2A> quando opportuno oppure lo usa in casi in cui non è appropriato.  Dopo la conversione in <xref:System.Runtime.InteropServices.SafeHandle>, non è necessario che le classi chiamino <xref:System.GC.KeepAlive%2A>, presupponendo che non abbiano un finalizzatore ma si basino su <xref:System.Runtime.InteropServices.SafeHandle> per finalizzare gli handle del sistema operativo.  Mentre i costi a livello di prestazioni risultanti dal mantenimento di una chiamata a <xref:System.GC.KeepAlive%2A> sono trascurabili, la percezione che una chiamata a <xref:System.GC.KeepAlive%2A> sia necessaria o sufficiente per la risoluzione di un problema di durata, che potrebbe non esserci più, rende più difficile la gestione del codice.  Tuttavia, quando si usano gli oggetti Runtime Callable Wrapper CLR di interoperabilità COM, <xref:System.GC.KeepAlive%2A> è ancora necessario per il codice.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Rimuovere <xref:System.GC.KeepAlive%2A>.

### <a name="use-the-hostprotection-attribute"></a>Usare l'attributo HostProtection

La classe <xref:System.Security.Permissions.HostProtectionAttribute> (HPA) consente di usare azioni di sicurezza dichiarative per determinare i requisiti di protezione host. In questo modo, l'host può impedire anche al codice completamente attendibile di chiamare determinati metodi che non sono appropriati per l'host specifico, ad esempio <xref:System.Environment.Exit%2A> o <xref:System.Windows.Forms.MessageBox.Show%2A> per SQL Server.

L'attributo di protezione host influisce solo sulle applicazioni non gestite che ospitano Common Language Runtime e implementano la protezione host, ad esempio SQL Server. Quando applicata, l'azione di sicurezza comporta la creazione di una richiesta di collegamento in base alle risorse host esposte dalla classe o dal metodo. Se il codice viene eseguito in un'applicazione client o in un server non protetto dall'host, l'attributo non ha alcun effetto. Non viene rilevato e quindi nemmeno applicato.

> [!IMPORTANT]
> Lo scopo di questo attributo è quello di imporre le linee guida del modello di programmazione specifico per l'host, non il comportamento di sicurezza.  Anche se per controllare la conformità ai requisiti del modello di programmazione viene usata una richiesta di collegamento, l'oggetto <xref:System.Security.Permissions.HostProtectionAttribute> non è un'autorizzazione di sicurezza.

Se l'host non ha i requisiti del modello di programmazione, le richieste di collegamento non vengono effettuate.

Questo attributo identifica quanto segue:

- Metodi o classi non idonei per il modello di programmazione dell'host ma benigni.

- Metodi o classi non idonei per il modello di programmazione dell'host e che potrebbero portare alla destabilizzazione del codice utente gestito dal server.

- Metodi o classi non idonei per il modello di programmazione dell'host e che potrebbero portare alla destabilizzazione del processo server stesso.

> [!NOTE]
> Se si crea una libreria di classi che verrà chiamata da applicazioni eseguibili in un ambiente protetto dall'host, è necessario applicare questo attributo ai membri che espongono categorie di risorse <xref:System.Security.Permissions.HostProtectionResource>. I membri della libreria di classi .NET Framework con questo attributo provocano solo il controllo del chiamante immediato.  Analogamente, anche i membri della propria libreria devono determinare il controllo del relativo chiamante immediato.

Per altre informazioni sull'attributo di protezione host, vedere <xref:System.Security.Permissions.HostProtectionAttribute>.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Per SQL Server, tutti i metodi usati per introdurre la sincronizzazione o il threading devono essere identificati con l'attributo di protezione host. Tra questi metodi sono inclusi quelli che condividono lo stato, sono sincronizzati o gestiscono processi esterni. I valori di <xref:System.Security.Permissions.HostProtectionResource> che influiscono su SQL Server sono <xref:System.Security.Permissions.HostProtectionResource.SharedState>, <xref:System.Security.Permissions.HostProtectionResource.Synchronization> e <xref:System.Security.Permissions.HostProtectionResource.ExternalProcessMgmt>. Tuttavia, l'identificazione con un attributo di protezione host è necessaria per tutti i metodi che espongono qualsiasi oggetto <xref:System.Security.Permissions.HostProtectionResource>, non solo per quelli che usano risorse che interessano SQL.

### <a name="do-not-block-indefinitely-in-unmanaged-code"></a>Non bloccare a tempo indefinito nel codice non gestito

L'inserimento di un blocco nel codice non gestito invece che in quello gestito può determinare un attacco Denial of Service perché CLR non è in grado di interrompere il thread.  Un thread bloccato impedisce a CLR di scaricare <xref:System.AppDomain>, se non mediante l'esecuzione di operazioni assolutamente non sicure.  Il blocco mediante una primitiva di sincronizzazione di Windows è un esempio chiaro di qualcosa che non è consentito.  Il blocco in una chiamata a `ReadFile` in un socket deve essere evitato se possibile. idealmente, l'API Windows deve fornire un meccanismo per il timeout di un'operazione come questa.

Tutti i metodi che effettuano chiamate nel codice nativo dovrebbero usare una chiamata Win32 con un valore finito e ragionevole di timeout.  Anche se autorizzato a specificare il timeout, l'utente non deve avere la possibilità di impostare un timeout infinito, a meno che non abbia autorizzazioni di sicurezza specifiche.  Come indicazione generale, tenere presente che, se un metodo si blocca per più di circa 10 secondi, sarà necessario usare una versione che supporta i timeout oppure disporre di supporto CLR aggiuntivo.

Di seguito sono riportati alcuni esempi di API problematiche.  Unnamed pipe e named pipe possono essere create senza timeout, tuttavia il codice non deve mai chiamare `CreateNamedPipe` né `WaitNamedPipe` con NMPWAIT_WAIT_FOREVER.  È inoltre possibile che si verifichi un blocco imprevisto anche se è specificato un timeout.  La chiamata a `WriteFile` su una unnamed pipe causa un blocco finché non vengono scritti tutti i byte e quindi, se il buffer contiene dati non letti, il blocco determinato dalla chiamata a `WriteFile` si protrarrà finché il lettore non libera spazio nel buffer della pipe.  I socket devono sempre usare API che rispettano un meccanismo di timeout.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Un blocco senza timeout nel codice non gestito è un attacco Denial of Service. Non eseguire chiamate di platform invoke su `WaitForSingleObject`, `WaitForSingleObjectEx`, `WaitForMultipleObjects`, `MsgWaitForMultipleObjects` e `MsgWaitForMultipleObjectsEx`.  Non usare NMPWAIT_WAIT_FOREVER.

### <a name="identify-any-sta-dependent-features"></a>Identificare tutte le funzionalità dipendenti da STA

Identificare il codice che usa apartment a thread singolo (STA, Single-Threaded Apartment) COM.  Gli apartment a thread singolo sono disabilitati nel processo SQL Server.  Le funzionalità che dipendono da `CoInitialize`, ad esempio i contatori delle prestazioni o gli Appunti, devono essere disabilitate in SQL Server.

### <a name="ensure-finalizers-are-free-of-synchronization-problems"></a>Verificare che i finalizzatori siano privi di problemi di sincronizzazione

È possibile che nelle versioni future di .NET Framework ci saranno più thread finalizzatori e che quindi i finalizzatori per istanze diverse dello stesso tipo vengano eseguiti simultaneamente.  Non è necessario che i finalizzatori siano completamente thread-safe perché il Garbage Collector garantisce che un solo thread eseguirà il finalizzatore per un'istanza di un determinato oggetto.  È tuttavia necessario che i finalizzatori siano codificati per evitare situazioni di race condition e deadlock quando vengono eseguiti simultaneamente su più istanze di oggetti diverse.  Quando si usa qualsiasi stato esterno in un finalizzatore, ad esempio per scrivere in un file di log, è necessario gestire i problemi di threading.  Non fare affidamento sulla finalizzazione per fornire caratteristiche di thread safety. Non usare l'archiviazione thread-local, gestita o nativa, per archiviare lo stato nel thread finalizzatore.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

I finalizzatori non devono avere alcun problema di sincronizzazione. Non usare uno stato modificabile statico in un finalizzatore.

### <a name="avoid-unmanaged-memory-if-possible"></a>Se possibile, evitare la memoria non gestita

La memoria non gestita può andare perduta, proprio come un handle del sistema operativo. Se possibile, provare a usare la memoria nello stack tramite [stackalloc](../../csharp/language-reference/operators/stackalloc.md), un oggetto gestito bloccato, come l'[istruzione fixed](../../csharp/language-reference/keywords/fixed-statement.md), o un oggetto <xref:System.Runtime.InteropServices.GCHandle> che fa uso di un byte[]. Alla fine, <xref:System.GC> eseguirà la pulizia di questi elementi. Se tuttavia è necessario allocare memoria non gestita, prendere in considerazione l'uso di una classe che deriva da <xref:System.Runtime.InteropServices.SafeHandle> per eseguire il wrapping dell'allocazione della memoria.

Si noti che c'è almeno un caso in cui l'oggetto <xref:System.Runtime.InteropServices.SafeHandle> non è adeguato. Per le chiamate ai metodi COM che allocano o liberano memoria, viene in genere usata una DLL per allocare la memoria tramite `CoTaskMemAlloc`, seguita da un'altra DLL per liberare la memoria con `CoTaskMemFree`.  L'uso di <xref:System.Runtime.InteropServices.SafeHandle> in questi contesti risulta inappropriato perché questo oggetto tenta di legare la durata della memoria non gestita alla durata di <xref:System.Runtime.InteropServices.SafeHandle>, invece di consentire che venga controllata dall'altra DLL.

### <a name="review-all-uses-of-catchexception"></a>Esaminare tutti gli utilizzi di catch (Exception)

I blocchi catch che intercettano tutte le eccezioni invece di un'eccezione specifica sono ora in grado di intercettare anche le eccezioni asincrone. Esaminare ogni blocco catch(Exception) verificando che non sia presente codice di annullamento o di rilascio di risorse importanti che potrebbe essere ignorato oppure un comportamento potenzialmente non corretto nel blocco catch stesso per la gestione di <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> o <xref:System.OutOfMemoryException>.  Si noti che il codice potrebbe registrare o presupporre di poter rilevare solo determinate eccezioni oppure che ogni volta che si verifica un'eccezione la causa è sempre un motivo specifico.  È possibile che questi presupposti debbano essere aggiornati in modo da includere <xref:System.Threading.ThreadAbortException>.

Prendere in considerazione l'opportunità di modificare tutti i punti in cui vengono intercettate le eccezioni in modo da intercettare un tipo specifico di eccezione che si prevede venga generato, ad esempio un'eccezione <xref:System.FormatException> dai metodi di formattazione delle stringhe.  In questo modo è possibile impedire l'esecuzione del blocco catch in caso di eccezioni impreviste e garantire che il codice non nasconda bug intercettando eccezioni di questo tipo.  Come regola generale, evitare sempre di gestire un'eccezione nel codice di libreria (il codice che richiede di intercettare un'eccezione può indicare la presenza di un difetto di progettazione nel codice chiamato).  In alcuni casi è opportuno intercettare un'eccezione e generarne un'altra di tipo diverso per fornire più dati.  A tale scopo, usare eccezioni annidate, archiviando la causa effettiva dell'errore nella proprietà <xref:System.Exception.InnerException%2A> della nuova eccezione.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Esaminare tutti i blocchi catch nel codice gestito che intercettano tutti gli oggetti o tutte le eccezioni.  In C#, questo significa contrassegnare sia `catch` {} che `catch(Exception)` {}.  Prendere in considerazione l'opportunità di rendere molto specifico il tipo di eccezione oppure esaminare il codice per assicurarsi che non si verifichino comportamenti non corretti qualora venga intercettata un'eccezione di tipo imprevisto.

### <a name="do-not-assume-a-managed-thread-is-a-win32-thread--it-is-a-fiber"></a>Non presupporre che un thread gestito sia un thread Win32, ovvero una fibra

È possibile usare l'archiviazione thread-local gestita, ma non quella non gestita, né è possibile presupporre che il codice verrà eseguito di nuovo nel thread del sistema operativo corrente. Non modificare impostazioni quali le impostazioni locali dei thread. Non chiamare `InitializeCriticalSection` o `CreateMutex` tramite platform invoke perché questi metodi richiedono che un thread del sistema operativo che attiva un blocco possa anche disattivarlo. Poiché con i fiber questo non si verifica, non è possibile usare mutex e sezioni critiche Win32 direttamente in SQL.  Si noti che la classe gestita <xref:System.Threading.Mutex> non gestisce questi problemi di affinità di thread.

È possibile usare senza alcun rischio la maggior parte dei dati sullo stato in un oggetto <xref:System.Threading.Thread> gestito, tra cui l'archiviazione thread-local gestita e le impostazioni cultura dell'interfaccia utente correnti del thread. È anche possibile usare l'oggetto <xref:System.ThreadStaticAttribute>, che rende accessibile il valore di una variabile statica esistente solo al thread gestito corrente. Si tratta di una tecnica alternativa per gestire l'archiviazione locale dei fiber in CLR. Per motivi legati al modello di programmazione, non è consentito modificare le impostazioni cultura correnti di un thread durante l'esecuzione in SQL.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

SQL Server viene eseguito in modalità fiber. Non usare l'archiviazione thread-local. Non eseguire chiamate di platform invoke su `TlsAlloc`, `TlsFree`, `TlsGetValue` e `TlsSetValue.`

### <a name="let-sql-server-handle-impersonation"></a>Consentire a SQL Server di gestire la rappresentazione

Poiché la rappresentazione opera a livello di thread e SQL può essere eseguito in modalità fiber, il codice gestito non deve rappresentare utenti né chiamare `RevertToSelf`.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Consentire a SQL Server di gestire la rappresentazione. Non usare `RevertToSelf`, `ImpersonateAnonymousToken`, `DdeImpersonateClient`, `ImpersonateDdeClientWindow`, `ImpersonateLoggedOnUser`, `ImpersonateNamedPipeClient`, `ImpersonateSelf`, `RpcImpersonateClient`, `RpcRevertToSelf`, `RpcRevertToSelfEx` o `SetThreadToken`.

### <a name="do-not-call-threadsuspend"></a>Non chiamare thread:: Suspend

Nonostante possa sembrare un'operazione semplice, la sospensione di un thread può causare situazioni di deadlock.  Se un thread che applica un blocco viene sospeso da un secondo thread e quest'ultimo cerca di acquisire lo stesso blocco, si verifica un deadlock.  Attualmente <xref:System.Threading.Thread.Suspend%2A> può interferire con la sicurezza, il caricamento delle classi, la comunicazione remota e la reflection.

#### <a name="code-analysis-rule"></a>Regola di analisi codice

Non chiamare <xref:System.Threading.Thread.Suspend%2A>. Prendere invece in considerazione l'uso di una primitiva di sincronizzazione effettiva, ad esempio un oggetto <xref:System.Threading.Semaphore> o <xref:System.Threading.ManualResetEvent>.

### <a name="protect-critical-operations-with-constrained-execution-regions-and-reliability-contracts"></a>Proteggere le operazioni critiche con le aree di esecuzione vincolate e i contratti di affidabilità

Quando si esegue un'operazione complessa che aggiorna uno stato condiviso o che deve avere esito completamente positivo o negativo, assicurarsi che sia protetta da un'area a esecuzione vincolata. In questo modo, si garantisce che il codice venga eseguito in ogni caso, anche se si verifica un'interruzione improvvisa del thread o uno scaricamento improvviso di <xref:System.AppDomain>.

Un'area a esecuzione vincolata consiste in un particolare blocco `try/finally`, immediatamente preceduto da una chiamata a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>.

In questo modo, il compilatore JIT prepara tutto il codice nel blocco finally prima di eseguire il blocco `try`. Si ha così la garanzia che il codice nel blocco finally venga compilato ed eseguito in tutti i casi. Non è raro che in un'area a esecuzione vincolata sia presente un blocco `try` vuoto. L'uso di un'area di questo tipo garantisce la protezione da interruzioni di thread asincrone ed eccezioni di memoria insufficiente. Per un formato di area a esecuzione vincolata in grado di gestire anche gli overflow dello stack per codice eccessivamente dettagliato, vedere <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.ConstrainedExecution>
- [Programmazione per SQL Server e attributi di protezione host](sql-server-programming-and-host-protection-attributes.md)
