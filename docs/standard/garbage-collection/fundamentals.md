---
title: Principi fondamentali di Garbage Collection
description: Informazioni su come funziona il Garbage Collector e su come può essere configurato per ottenere prestazioni ottimali.
ms.date: 11/15/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, generations
- garbage collection, background
- garbage collection, concurrent
- garbage collection, server
- garbage collection, workstation
- garbage collection, managed heap
ms.assetid: 67c5a20d-1be1-4ea7-8a9a-92b0b08658d2
ms.openlocfilehash: ea8aef03d2f5837f35ecb31209e57853c0c8257b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330423"
---
# <a name="fundamentals-of-garbage-collection"></a>Principi fondamentali di Garbage Collection

In the common language runtime (CLR), the garbage collector (GC) serves as an automatic memory manager. offrendo i seguenti vantaggi:

- Enables you to develop your application without having to manually free memory.

- Alloca gli oggetti nell'heap gestito in maniera efficiente.

- Recupera gli oggetti inutilizzati, ne cancella la memoria e tiene la memoria a disposizione per le future allocazioni. Gli oggetti gestiti ottengono automaticamente contenuto pulito con il quale iniziare, pertanto i costruttori non devono inizializzare ogni campo dati.

- Garantisce protezione per la memoria assicurando che un oggetto non possa usare il contenuto di un altro oggetto.

This article describes the core concepts of garbage collection.

## <a name="fundamentals-of-memory"></a>Nozioni fondamentali sulla memoria

Nell'elenco seguente sono riepilogati concetti importanti relativi alla memoria CLR.

- Ogni processo dispone di un proprio spazio degli indirizzi virtuali distinto. All processes on the same computer share the same physical memory and the page file, if there is one.

- Per impostazione predefinita, nei computer a 32 bit ogni processo dispone di uno spazio degli indirizzi virtuali in modalità utente da 2 GB.

- Uno sviluppatore di applicazioni usa solo lo spazio degli indirizzi virtuali e non modifica mai direttamente la memoria fisica. Il Garbage Collector alloca e libera automaticamente la memoria virtuale nell'heap gestito.

  If you are writing native code, you use Windows functions to work with the virtual address space. Queste funzioni allocano e liberano automaticamente la memoria virtuale negli heap nativi.

- La memoria virtuale può trovarsi in tre stati:

  - Libero. Non vi sono riferimenti al blocco di memoria, che è disponibile per l'allocazione.

  - Riservato. Il blocco di memoria è disponibile per l'utilizzo e non può essere usato da un'altra richiesta di allocazione. Non è tuttavia possibile archiviare i dati in questo blocco di memoria fino a quando non viene eseguito il commit.

  - Eseguito. Il blocco di memoria è assegnato all'archiviazione fisica.

- Lo spazio degli indirizzi virtuali può diventare frammentato. Ciò significa che sono presenti blocchi liberi, noti anche come buchi, nello spazio degli indirizzi. Quando viene richiesta un'allocazione della memoria virtuale, il gestore di memoria virtuale deve trovare un singolo blocco libero con dimensioni sufficienti per soddisfare la richiesta di allocazione. Anche se si hanno 2 GB di spazio disponibile, l'allocazione che richiede 2 GB avrà esito negativo a meno che tutto lo spazio disponibile si trovi in un unico blocco di indirizzi.

- You can run out of memory if there isn't enough virtual address space to reserve or physical space to commit.

  The page file is used even if physical memory pressure (that is, demand for physical memory) is low. The first time physical memory pressure is high, the operating system must make room in physical memory to store data, and it backs up some of the data that is in physical memory to the page file. That data is not paged until it's needed, so it's possible to encounter paging in situations where the physical memory pressure is low.

## <a name="conditions-for-a-garbage-collection"></a>Condizioni per un'operazione di Garbage Collection

Le operazioni di Garbage Collection vengono eseguite in presenza di una delle seguenti condizioni:

- La memoria fisica del sistema è insufficiente. This is detected by either the low memory notification from the OS or low memory as indicated by the host.

- La memoria usata dagli oggetti allocati nell'heap gestito supera una soglia accettabile. Questa soglia viene continuamente modificata durante l'esecuzione del processo.

- Viene chiamato il metodo <xref:System.GC.Collect%2A?displayProperty=nameWithType> . Nella quasi totalità dei casi non è necessario chiamare questo metodo, in quanto il Garbage Collector viene eseguito senza interruzioni. Il metodo viene usato principalmente in situazioni eccezionali e per scopi di test.

## <a name="the-managed-heap"></a>Heap gestito

Dopo essere stato inizializzato da CLR, il Garbage Collector alloca un segmento di memoria per archiviare e gestire oggetti. Questa memoria è definita heap gestito, in contrapposizione a un heap nativo presente nel sistema operativo.

Per ogni processo gestito esiste un heap gestito. Tutti i thread nel processo allocano memoria per gli oggetti sullo stesso heap.

To reserve memory, the garbage collector calls the Windows [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) function and reserves one segment of memory at a time for managed applications. The garbage collector also reserves segments, as needed, and releases segments back to the operating system (after clearing them of any objects) by calling the Windows [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) function.

> [!IMPORTANT]
> La dimensione dei segmenti allocati dal Garbage Collector è specifica dell'implementazione ed è soggetta a modifiche in qualsiasi momento, tra cui aggiornamenti periodici. L'applicazione non deve dare per scontata o dipendere da una particolare dimensione del segmento, né provare a configurare la quantità di memoria disponibile per le allocazioni di segmenti.

Minore è il numero di oggetti allocati nell'heap, minore sarà il lavoro del Garbage Collector. Quando si allocano oggetti, non usare valori arrotondati per eccesso che superino le proprie esigenze, ad esempio non allocare una matrice di 32 byte se sono necessari solo 15 byte.

Quando viene attivata un'operazione di Garbage Collection, il Garbage Collector recupera la memoria occupata dagli oggetti inutilizzati. Durante il processo di recupero, gli oggetti attivi vengono compattati in modo da poter essere spostati insieme e lo spazio inutilizzato viene rimosso, riducendo le dimensioni dell'heap. In questo modo si garantisce che gli oggetti allocati insieme restino uniti nell'heap gestito, preservandone la vicinanza.

L'impatto (frequenza e durata) delle operazioni di Garbage Collection è il risultato del volume di allocazioni e della quantità di memoria esclusa nell'heap gestito.

L'heap può essere considerato l'insieme di due heap: l'[heap degli oggetti grandi](large-object-heap.md) e l'heap degli oggetti piccoli.

L'[heap degli oggetti grandi](large-object-heap.md) contiene oggetti molto grandi di dimensioni pari o superiori a 85.000 byte. Gli oggetti sull'heap oggetti grandi sono in genere matrici. È raro che un oggetto istanza sia particolarmente grande.

> [!TIP]
> You can [configure the threshold size](../../core/run-time-config/garbage-collector.md#large-object-heap-threshold) for objects to go on the large object heap.

## <a name="generations"></a>Generazioni

L'heap è organizzato in generazioni, così da poter gestire oggetti di lunga durata e di breve durata. Durante un'operazione di Garbage Collection vengono recuperati per primi gli oggetti di breve durata, che in genere occupano solo una piccola parte dell'heap. Esistono tre generazioni di oggetti nell'heap:

- **Generazione 0**. È la generazione più recente e contiene oggetti di breve durata. Un esempio di oggetto di breve durata è una variabile temporanea. Le operazioni di Garbage Collection vengono eseguite il più delle volte in questa generazione.

  Newly allocated objects form a new generation of objects and are implicitly generation 0 collections. However, if they are large objects, they go on the large object heap in a generation 2 collection.

  Gran parte degli oggetti vengono recuperati tramite Garbage Collection nella generazione 0 e non passano alla generazione successiva.

- **Generazione 1**. Questa generazione contiene oggetti di breve durata e funge da buffer tra gli oggetti di breve durata e gli oggetti di lunga durata.

- **Generazione 2**. Questa generazione contiene oggetti di lunga durata. An example of a long-lived object is an object in a server application that contains static data that's live for the duration of the process.

Le operazioni di Garbage Collection vengono eseguite in generazioni specifiche a seconda delle condizioni. Raccogliere una generazione significa raccogliere gli oggetti in quella generazione e in tutte le generazioni più recenti. Un'operazione di Garbage Collection di generazione 2 viene definita completa, in quanto recupera tutti gli oggetti in tutte le generazioni, vale a dire tutti gli oggetti nell'heap gestito.

### <a name="survival-and-promotions"></a>Esclusione e promozioni

Objects that are not reclaimed in a garbage collection are known as survivors and are promoted to the next generation. Gli oggetti esclusi da un'operazione di Garbage Collection di generazione 0 vengono promossi alla generazione 1; gli oggetti esclusi da un'operazione di Garbage Collection di generazione 1 vengono promossi alla generazione 2; gli oggetti esclusi da un'operazione di Garbage Collection di generazione 2 restano nella generazione 2.

When the garbage collector detects that the survival rate is high in a generation, it increases the threshold of allocations for that generation. The next collection gets a substantial size of reclaimed memory. The CLR continually balances two priorities: not letting an application's working set get too large by delaying garbage collection and not letting the garbage collection run too frequently.

### <a name="ephemeral-generations-and-segments"></a>Generazioni e segmenti temporanei

Poiché gli oggetti nelle generazioni 0 e 1 sono di breve durata, queste vengono definite generazioni temporanee.

Le generazioni temporanee devono essere allocate nel segmento di memoria noto come segmento temporaneo. Ogni nuovo segmento acquisito dal Garbage Collector diventa il nuovo segmento temporaneo e contiene gli oggetti esclusi da un'operazione di Garbage Collection di generazione 0. Il segmento temporaneo precedente diventa il nuovo segmento di generazione 2.

The size of the ephemeral segment varies depending on whether a system is 32-bit or 64-bit, and on the type of garbage collector it is running. Nella tabella che segue sono riportati i valori predefiniti.

||32 bit|64 bit|
|-|-------------|-------------|
|GC workstation|16 MB|256 MB|
|GC server|64 MB|4 GB|
|GC server con > 4 CPU logiche|32 MB|2 GB|
|GC server con > 8 CPU logiche|16 MB|1 GB|

Il segmento temporaneo può includere oggetti di generazione 2, i quali possono usare più segmenti (nella misura richiesta dal processo e consentita dalla memoria).

La quantità di memoria liberata da un'operazione di Garbage Collection temporanea è limitata alla dimensione del segmento temporaneo. Tale quantità di memoria è proporzionale allo spazio occupato dagli oggetti inutilizzati.

## <a name="what-happens-during-a-garbage-collection"></a>Fasi di un'operazione di Garbage Collection

Un'operazione di Garbage Collection si compone delle seguenti fasi:

- Una fase di contrassegno in cui vengono individuati tutti gli oggetti attivi e ne viene creato un elenco.

- Una fase di rilocazione in cui vengono aggiornati i riferimenti agli oggetti che saranno compattati.

- Una fase di compattazione in cui lo spazio occupato dagli oggetti inutilizzati viene recuperato e gli oggetti esclusi compattati. Durante questa fase, gli oggetti rimasti dopo un'operazione di Garbage Collection vengono spostati verso l'estremità meno recente del segmento.

  Poiché le raccolte di generazione 2 possono occupare più segmenti, gli oggetti promossi alla generazione 2 possono essere spostati in un segmento meno recente. Gli oggetti esclusi di generazione 1 e 2 possono essere spostati in un segmento diverso, in quanto vengono promossi alla generazione 2.

  Ordinarily, the large object heap (LOH) is not compacted, because copying large objects imposes a performance penalty. However, in .NET Core and in .NET Framework 4.5.1 and later, you can use the <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> property to compact the large object heap on demand. In addition, the LOH is automatically compacted when a hard limit is set by specifying either:

  - a memory limit on a container, or
  - the [GCHeapHardLimit](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitcomplus_gcheaphardlimit) or [GCHeapHardLimitPercent](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) run-time configuration options

Per stabilire se gli oggetti sono attivi, il Garbage Collector usa le seguenti informazioni:

- **Radici dello stack**. Variabili dello stack fornite dal compilatore JIT e dal percorso di chiamate nello stack. JIT optimizations can lengthen or shorten regions of code within which stack variables are reported to the garbage collector.

- **Handle di Garbage Collection**. Handle che puntano agli oggetti gestiti e che possono essere allocati mediante codice utente o Common Language Runtime.

- **Dati statici**. Oggetti statici nei domini applicazione che possono fare riferimento ad altri oggetti. Ogni dominio applicazione tiene traccia dei rispettivi oggetti statici.

Prima di eseguire un'operazione di Garbage Collection, tutti i thread gestiti vengono sospesi, eccetto il thread che attiva l'operazione.

Nell'illustrazione seguente viene illustrato un thread che attiva un'operazione di Garbage Collection causando la sospensione degli altri thread.

![Thread che attiva un'operazione di Garbage Collection](./media/gc-triggered.png)

## <a name="manipulate-unmanaged-resources"></a>Manipulate unmanaged resources

If managed objects reference unmanaged objects by using their native file handles, you have to explicitly free the unmanaged objects, because the garbage collector only tracks memory on the managed heap.

Users of the managed object may not dispose the native resources used by the object. To perform the cleanup, you can make the managed object finalizable. Finalization consists of cleanup actions that execute when the object is no longer in use. When the managed object dies, it performs cleanup actions that are specified in its finalizer method.

Quando viene individuato un oggetto finalizzabile inutilizzato, il relativo finalizzatore viene inserito in una coda in modo che vengano eseguite le azioni di pulizia, mentre l'oggetto stesso viene promosso alla generazione successiva. Sarà pertanto necessario attendere l'operazione di Garbage Collection successiva eseguita in tale generazione, che non sarà necessariamente l'operazione immediatamente successiva, per stabilire se l'oggetto è stato recuperato.

For more information about finalization, see <xref:System.Object.Finalize?displayProperty=nameWithType>.

## <a name="workstation-and-server-garbage-collection"></a>Operazione di Garbage Collection per workstation e server

Il Garbage Collector si regola da sé e può funzionare in un'ampia varietà di scenari. You can use a [configuration file setting](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection) to set the type of garbage collection based on the characteristics of the workload. CLR fornisce i seguenti tipi di Garbage Collection:

- Workstation garbage collection (GC) is designed for client apps. It is the default GC flavor for standalone apps. For hosted apps, for example, those hosted by ASP.NET, the host determines the default GC flavor.

  Le operazioni di Garbage Collection per workstation possono essere eseguite in modalità simultanea o non simultanea. La modalità simultanea consente ai thread gestiti di continuare le operazioni durante un'operazione di Garbage Collection. [Background garbage collection](#background-workstation-garbage-collection) replaces [concurrent garbage collection](#concurrent-garbage-collection) in .NET Framework 4 and later versions.

- Garbage Collection per server, per le applicazioni server che richiedono scalabilità e velocità effettiva elevata.

  - In .NET Core, server garbage collection can be non-concurrent or background.

  - In .NET Framework 4.5 and later versions, server garbage collection can be non-concurrent or background (background garbage collection replaces concurrent garbage collection). In .NET Framework 4 and previous versions, server garbage collection is non-concurrent.

The following illustration shows the dedicated threads that perform the garbage collection on a server:

![Thread di Garbage Collection server](./media/gc-server.png)

### <a name="compare-workstation-and-server-garbage-collection"></a>Compare workstation and server garbage collection

Di seguito sono riportate alcune considerazioni su threading e prestazioni per l'operazione di Garbage Collection per workstation:

- La raccolta viene eseguita nel thread dell'utente che ha attivato l'operazione di Garbage Collection e mantiene la stessa priorità. Poiché i thread dell'utente vengono in genere eseguiti con priorità normale, il Garbage Collector (eseguito in un thread con priorità normale) deve competere con altri thread per il tempo CPU. (Threads that run native code are not suspended on either server or workstation garbage collection.)

- Workstation garbage collection is always used on a computer that has only one processor, regardless of the [configuration setting](../../core/run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).

Di seguito sono riportate alcune considerazioni su threading e prestazioni per l'operazione di Garbage Collection per server:

- La raccolta viene eseguita in più thread dedicati eseguiti con livello di priorità `THREAD_PRIORITY_HIGHEST` .

- Per ogni CPU vengono forniti un heap e un thread dedicato per l'esecuzione dell'operazione di Garbage Collection. Gli heap vengono raccolti contemporaneamente. Ogni heap contiene un heap degli oggetti piccoli e un heap degli oggetti grandi; è possibile accedere a tutti gli heap tramite codice utente. Gli oggetti contenuti in heap diversi possono fare riferimento l'un l'altro.

- Grazie all'utilizzo congiunto di più thread di Garbage Collection, le operazioni di Garbage Collection per server saranno più veloci delle operazioni per workstation in un heap di pari dimensioni.

- I segmenti di Garbage Collection per server sono spesso di dimensioni maggiori. However, this is only a generalization: segment size is implementation-specific and is subject to change. Don't make assumptions about the size of segments allocated by the garbage collector when tuning your app.

- Le operazioni di Garbage Collection per server possono richiedere un utilizzo di risorse elevato. For example, imagine that there are 12 processes that use server GC running on a computer that has 4 processors. If all the processes happen to collect garbage at the same time, they would interfere with each other, as there would be 12 threads scheduled on the same processor. If the processes are active, it's not a good idea to have them all use server GC.

If you're running hundreds of instances of an application, consider using workstation garbage collection with concurrent garbage collection disabled. Si avranno meno cambi di contesto e un possibile miglioramento delle prestazioni.

## <a name="background-workstation-garbage-collection"></a>Garbage Collection della workstation in background

In background workstation garbage collection, ephemeral generations (0 and 1) are collected as needed while the collection of generation 2 is in progress. Background workstation garbage collection is performed on a dedicated thread and applies only to generation 2 collections.

Background garbage collection is enabled by default and can be enabled or disabled with the [gcConcurrent](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration setting in .NET Framework apps or the [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) setting in .NET Core apps.

> [!NOTE]
> Background garbage collection replaces [concurrent garbage collection](#concurrent-garbage-collection) and is available in .NET Framework 4 and later versions. In .NET Framework 4, it's supported only for workstation garbage collection. Starting with .NET Framework 4.5, background garbage collection is available for both workstation and server garbage collection.

Una raccolta nelle generazioni temporanee durante un'operazione in background è definita Garbage Collection in primo piano. Durante l'esecuzione di un'operazione di Garbage Collection in primo piano, tutti i thread gestiti vengono sospesi.

When background garbage collection is in progress and you've allocated enough objects in generation 0, the CLR performs a generation 0 or generation 1 foreground garbage collection. Il thread di Garbage Collection in background dedicato esegue controlli in corrispondenza di punti sicuri frequenti per stabilire se vi sia una richiesta di Garbage Collection in primo piano. In caso affermativo, la raccolta in background si autosospende in modo che possa essere eseguita l'operazione in primo piano. Una volta completata tale operazione, si ha la ripresa del thread di Garbage Collection in background dedicato e dei thread dell'utente.

La modalità in background elimina le restrizioni di allocazione imposte dalla modalità simultanea, dal momento che durante un'operazione di Garbage Collection in background è possibile eseguire operazioni temporanee. Background garbage collection can remove dead objects in ephemeral generations. It can also expand the heap if needed during a generation 1 garbage collection.

La figura seguente illustra l'esecuzione in background di un'operazione di Garbage Collection in un thread dedicato separato su una workstation:

![Garbage Collection della workstation in background](./media/fundamentals/background-workstation-garbage-collection.png)

### <a name="background-server-garbage-collection"></a>Garbage Collection del server in background

Starting with .NET Framework 4.5, background server garbage collection is the default mode for server garbage collection.

Background server garbage collection functions similarly to background workstation garbage collection, described in the previous section, but there are a few differences:

- Background workstation garbage collection uses one dedicated background garbage collection thread, whereas background server garbage collection uses multiple threads. Typically, there's a dedicated thread for each logical processor.

- A differenza del thread di Garbage Collection in background per workstation, questi thread non scadono.

La figura seguente illustra l'esecuzione in background di un'operazione di Garbage Collection in un thread dedicato separato su un server:

![Garbage Collection del server in background](./media/fundamentals/background-server-garbage-collection.png)

## <a name="concurrent-garbage-collection"></a>Garbage Collection contemporanea

> [!TIP]
> This section applies to:
>
> - .NET Framework 3.5 and earlier for workstation garbage collection
> - .NET Framework 4 and earlier for server garbage collection
>
> Concurrent garbage is replaced by [background garbage collection](#background-workstation-garbage-collection) in later versions.

In workstation or server garbage collection, you can [enable concurrent garbage collection](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md), which enables threads to run concurrently with a dedicated thread that performs the garbage collection for most of the duration of the collection. Questa opzione riguarda solo le operazioni di Garbage Collection nella generazione 2; le generazioni 0 e 1 sono sempre non simultanee in quanto terminano molto velocemente.

La modalità simultanea consente alle applicazioni interattive una maggiore efficienza di risposta riducendo al minimo le pause di una raccolta. È possibile continuare a eseguire i thread gestiti per la maggior parte del tempo in cui viene eseguito il thread di Garbage Collection in modalità simultanea. Il risultato saranno pause più brevi durante l'esecuzione di un'operazione di Garbage Collection.

La modalità simultanea di Garbage Collection viene eseguita in un thread dedicato. Per impostazione predefinita, CLR esegue le operazioni di Garbage Collection per workstation con la modalità simultanea abilitata. Ciò vale tanto per i computer a processore singolo quanto per quelli multiprocessore.

Nell'illustrazione riportata di seguito viene mostrata l'esecuzione simultanea di un'operazione di Garbage Collection in un thread dedicato separato.

![Thread di Garbage Collection simultanei](./media/gc-concurrent.png)

## <a name="see-also"></a>Vedere anche

- [Configuration options for GC](../../core/run-time-config/garbage-collector.md)
- [Garbage collection](index.md)
