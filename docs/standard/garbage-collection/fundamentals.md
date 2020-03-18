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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79400540"
---
# <a name="fundamentals-of-garbage-collection"></a>Principi fondamentali di Garbage Collection

In Common Language Runtime (CLR), il Garbage Collector (GC) funge da gestore automatico della memoria. offrendo i seguenti vantaggi:

- Consente di sviluppare l'applicazione senza dover liberare manualmente memoria.

- Alloca gli oggetti nell'heap gestito in maniera efficiente.

- Recupera gli oggetti inutilizzati, ne cancella la memoria e tiene la memoria a disposizione per le future allocazioni. Gli oggetti gestiti ottengono automaticamente contenuto pulito con il quale iniziare, pertanto i costruttori non devono inizializzare ogni campo dati.

- Garantisce protezione per la memoria assicurando che un oggetto non possa usare il contenuto di un altro oggetto.

In questo articolo vengono descritti i concetti di base della procedura di Garbage Collection.This article describes the core concepts of garbage collection.

## <a name="fundamentals-of-memory"></a>Nozioni fondamentali sulla memoria

Nell'elenco seguente sono riepilogati concetti importanti relativi alla memoria CLR.

- Ogni processo dispone di un proprio spazio degli indirizzi virtuali distinto. Tutti i processi nello stesso computer condividono la stessa memoria fisica e il file di paging, se presente.

- Per impostazione predefinita, nei computer a 32 bit ogni processo dispone di uno spazio degli indirizzi virtuali in modalità utente da 2 GB.

- Uno sviluppatore di applicazioni usa solo lo spazio degli indirizzi virtuali e non modifica mai direttamente la memoria fisica. Il Garbage Collector alloca e libera automaticamente la memoria virtuale nell'heap gestito.

  Se si scrive codice nativo, utilizzare le funzioni di Windows per lavorare con lo spazio di indirizzi virtuali. Queste funzioni allocano e liberano automaticamente la memoria virtuale negli heap nativi.

- La memoria virtuale può trovarsi in tre stati:

  - Libero. Non vi sono riferimenti al blocco di memoria, che è disponibile per l'allocazione.

  - Riservato. Il blocco di memoria è disponibile per l'utilizzo e non può essere usato da un'altra richiesta di allocazione. Non è tuttavia possibile archiviare i dati in questo blocco di memoria fino a quando non viene eseguito il commit.

  - Eseguito. Il blocco di memoria è assegnato all'archiviazione fisica.

- Lo spazio degli indirizzi virtuali può diventare frammentato. Ciò significa che sono presenti blocchi liberi, noti anche come buchi, nello spazio degli indirizzi. Quando viene richiesta un'allocazione della memoria virtuale, il gestore di memoria virtuale deve trovare un singolo blocco libero con dimensioni sufficienti per soddisfare la richiesta di allocazione. Anche se si hanno 2 GB di spazio disponibile, l'allocazione che richiede 2 GB avrà esito negativo a meno che tutto lo spazio disponibile si trovi in un unico blocco di indirizzi.

- È possibile esaurire la memoria se lo spazio degli indirizzi virtuali non è sufficiente per riservare o spazio fisico di cui eseguire il commit.

  Il file di paging viene utilizzato anche se la pressione della memoria fisica, ovvero la richiesta di memoria fisica, è bassa. La prima volta che la pressione della memoria fisica è elevata, il sistema operativo deve lasciare spazio nella memoria fisica per archiviare i dati ed esegue il backup di alcuni dei dati che si trova nella memoria fisica nel file di paging. Tali dati non viene paginato fino a quando non è necessario, quindi è possibile incontrare il paging in situazioni in cui la pressione della memoria fisica è bassa.

## <a name="conditions-for-a-garbage-collection"></a>Condizioni per un'operazione di Garbage Collection

Le operazioni di Garbage Collection vengono eseguite in presenza di una delle seguenti condizioni:

- La memoria fisica del sistema è insufficiente. Questo viene rilevato dalla notifica di memoria insufficiente dal sistema operativo o dalla memoria insufficiente come indicato dall'host.

- La memoria usata dagli oggetti allocati nell'heap gestito supera una soglia accettabile. Questa soglia viene continuamente modificata durante l'esecuzione del processo.

- Viene chiamato il metodo <xref:System.GC.Collect%2A?displayProperty=nameWithType> . Nella quasi totalità dei casi non è necessario chiamare questo metodo, in quanto il Garbage Collector viene eseguito senza interruzioni. Il metodo viene usato principalmente in situazioni eccezionali e per scopi di test.

## <a name="the-managed-heap"></a>Heap gestito

Dopo essere stato inizializzato da CLR, il Garbage Collector alloca un segmento di memoria per archiviare e gestire oggetti. Questa memoria è definita heap gestito, in contrapposizione a un heap nativo presente nel sistema operativo.

Per ogni processo gestito esiste un heap gestito. Tutti i thread nel processo allocano memoria per gli oggetti sullo stesso heap.

Per riservare memoria, il Garbage Collector chiama la funzione [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) di Windows e riserva un segmento di memoria alla volta per le applicazioni gestite. Il Garbage Collector riserva anche i segmenti, se necessario, e rilascia i segmenti al sistema operativo (dopo averli cancellati da qualsiasi oggetto) chiamando la funzione [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) di Windows.

> [!IMPORTANT]
> La dimensione dei segmenti allocati dal Garbage Collector è specifica dell'implementazione ed è soggetta a modifiche in qualsiasi momento, tra cui aggiornamenti periodici. L'applicazione non deve dare per scontata o dipendere da una particolare dimensione del segmento, né provare a configurare la quantità di memoria disponibile per le allocazioni di segmenti.

Minore è il numero di oggetti allocati nell'heap, minore sarà il lavoro del Garbage Collector. Quando si allocano oggetti, non usare valori arrotondati per eccesso che superino le proprie esigenze, ad esempio non allocare una matrice di 32 byte se sono necessari solo 15 byte.

Quando viene attivata un'operazione di Garbage Collection, il Garbage Collector recupera la memoria occupata dagli oggetti inutilizzati. Durante il processo di recupero, gli oggetti attivi vengono compattati in modo da poter essere spostati insieme e lo spazio inutilizzato viene rimosso, riducendo le dimensioni dell'heap. In questo modo si garantisce che gli oggetti allocati insieme restino uniti nell'heap gestito, preservandone la vicinanza.

L'impatto (frequenza e durata) delle operazioni di Garbage Collection è il risultato del volume di allocazioni e della quantità di memoria esclusa nell'heap gestito.

L'heap può essere considerato l'insieme di due heap: l'[heap degli oggetti grandi](large-object-heap.md) e l'heap degli oggetti piccoli.

L'[heap degli oggetti grandi](large-object-heap.md) contiene oggetti molto grandi di dimensioni pari o superiori a 85.000 byte. Gli oggetti sull'heap oggetti grandi sono in genere matrici. È raro che un oggetto istanza sia particolarmente grande.

> [!TIP]
> È possibile [configurare la dimensione di soglia](../../core/run-time-config/garbage-collector.md#large-object-heap-threshold) per gli oggetti da utilizzare nell'heap oggetti grandi.

## <a name="generations"></a>Generazioni

L'heap è organizzato in generazioni, così da poter gestire oggetti di lunga durata e di breve durata. Durante un'operazione di Garbage Collection vengono recuperati per primi gli oggetti di breve durata, che in genere occupano solo una piccola parte dell'heap. Esistono tre generazioni di oggetti nell'heap:

- **Generazione 0**. È la generazione più recente e contiene oggetti di breve durata. Un esempio di oggetto di breve durata è una variabile temporanea. Le operazioni di Garbage Collection vengono eseguite il più delle volte in questa generazione.

  Gli oggetti appena allocati formano una nuova generazione di oggetti e sono implicitamente raccolte di generazione 0. Tuttavia, se sono oggetti di grandi dimensioni, vengono attivati nell'heap oggetti grandi in una raccolta di generazione 2.However, if they are large objects, they go on the large object heap in a generation 2 collection.

  Gran parte degli oggetti vengono recuperati tramite Garbage Collection nella generazione 0 e non passano alla generazione successiva.

- **Generazione 1**. Questa generazione contiene oggetti di breve durata e funge da buffer tra gli oggetti di breve durata e gli oggetti di lunga durata.

- **Generazione 2**. Questa generazione contiene oggetti di lunga durata. Un esempio di oggetto di lunga durata è un oggetto in un'applicazione server che contiene dati statici attivi per la durata del processo.

Le operazioni di Garbage Collection vengono eseguite in generazioni specifiche a seconda delle condizioni. Raccogliere una generazione significa raccogliere gli oggetti in quella generazione e in tutte le generazioni più recenti. Un'operazione di Garbage Collection di generazione 2 viene definita completa, in quanto recupera tutti gli oggetti in tutte le generazioni, vale a dire tutti gli oggetti nell'heap gestito.

### <a name="survival-and-promotions"></a>Esclusione e promozioni

Gli oggetti che non vengono recuperati in un'operazione di Garbage Collection sono noti come sopravvissuti e vengono promossi alla generazione successiva. Gli oggetti esclusi da un'operazione di Garbage Collection di generazione 0 vengono promossi alla generazione 1; gli oggetti esclusi da un'operazione di Garbage Collection di generazione 1 vengono promossi alla generazione 2; gli oggetti esclusi da un'operazione di Garbage Collection di generazione 2 restano nella generazione 2.

Quando il Garbage Collector rileva che il tasso di sopravvivenza è elevato in una generazione, aumenta la soglia delle allocazioni per tale generazione. La raccolta successiva ottiene una dimensione sostanziale della memoria recuperata. CLR bilancia continuamente due priorità: non lasciare che il working set di un'applicazione sia troppo grande ritardando l'operazione di Garbage Collection e non lasciando che l'operazione di Garbage Collection venga eseguita troppo frequentemente.

### <a name="ephemeral-generations-and-segments"></a>Generazioni e segmenti temporanei

Poiché gli oggetti nelle generazioni 0 e 1 sono di breve durata, queste vengono definite generazioni temporanee.

Le generazioni temporanee devono essere allocate nel segmento di memoria noto come segmento temporaneo. Ogni nuovo segmento acquisito dal Garbage Collector diventa il nuovo segmento temporaneo e contiene gli oggetti esclusi da un'operazione di Garbage Collection di generazione 0. Il segmento temporaneo precedente diventa il nuovo segmento di generazione 2.

La dimensione del segmento temporaneo varia a seconda che un sistema sia a 32 bit o a 64 bit e dal tipo di Garbage Collector in esecuzione. Nella tabella che segue sono riportati i valori predefiniti.

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

  In genere, l'heap oggetti grandi (LOH) non viene compattato, perché la copia di oggetti di grandi dimensioni comporta una riduzione delle prestazioni. Tuttavia, in .NET Core e in.NET Framework 4.5.1 e versioni successive, è possibile utilizzare la <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> proprietà per compattare l'heap oggetti grandi su richiesta. Inoltre, il LOH viene compattato automaticamente quando viene impostato un limite rigido specificando:

  - un limite di memoria su un contenitore, o
  - Le opzioni di configurazione di runtime [GCHeapHardLimit](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitcomplus_gcheaphardlimit) o [GCHeapHardLimitPercent](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent)

Per stabilire se gli oggetti sono attivi, il Garbage Collector usa le seguenti informazioni:

- **Radici dello stack**. Variabili dello stack fornite dal compilatore JIT e dal percorso di chiamate nello stack. Le ottimizzazioni JIT possono allungare o accorciare le aree del codice all'interno delle quali le variabili dello stack vengono segnalate al Garbage Collector.

- **Maniglie di Garbage Collection**. Handle che puntano agli oggetti gestiti e che possono essere allocati mediante codice utente o Common Language Runtime.

- **Dati statici**. Oggetti statici nei domini applicazione che possono fare riferimento ad altri oggetti. Ogni dominio applicazione tiene traccia dei rispettivi oggetti statici.

Prima di eseguire un'operazione di Garbage Collection, tutti i thread gestiti vengono sospesi, eccetto il thread che attiva l'operazione.

Nell'illustrazione seguente viene illustrato un thread che attiva un'operazione di Garbage Collection causando la sospensione degli altri thread.

![Thread che attiva un'operazione di Garbage Collection](./media/gc-triggered.png)

## <a name="manipulate-unmanaged-resources"></a>Manipolare le risorse non gestite

Se gli oggetti gestiti fanno riferimento a oggetti non gestiti utilizzando i relativi handle di file nativi, è necessario liberare in modo esplicito gli oggetti non gestiti, poiché il Garbage Collector tiene traccia solo della memoria nell'heap gestito.

Gli utenti dell'oggetto gestito non possono eliminare le risorse native utilizzate dall'oggetto. Per eseguire la pulizia, è possibile rendere finalizzabile l'oggetto gestito. La finalizzazione è costituita da azioni di pulitura che vengono eseguite quando l'oggetto non è più in uso. Quando l'oggetto gestito muore, esegue le azioni di pulizia specificate nel relativo metodo finalizzatore.

Quando viene individuato un oggetto finalizzabile inutilizzato, il relativo finalizzatore viene inserito in una coda in modo che vengano eseguite le azioni di pulizia, mentre l'oggetto stesso viene promosso alla generazione successiva. Sarà pertanto necessario attendere l'operazione di Garbage Collection successiva eseguita in tale generazione, che non sarà necessariamente l'operazione immediatamente successiva, per stabilire se l'oggetto è stato recuperato.

Per ulteriori informazioni sulla <xref:System.Object.Finalize?displayProperty=nameWithType>finalizzazione, vedere .

## <a name="workstation-and-server-garbage-collection"></a>Operazione di Garbage Collection per workstation e server

Il Garbage Collector si regola da sé e può funzionare in un'ampia varietà di scenari. È possibile utilizzare [un'impostazione](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection) del file di configurazione per impostare il tipo di Garbage Collection in base alle caratteristiche del carico di lavoro. CLR fornisce i seguenti tipi di Garbage Collection:

- La raccolta di rifiuti per workstation (GC) è progettata per le app client. È la versione GC predefinita per le app autonome. Per le app ospitate, ad esempio quelle ospitate da ASP.NET, l'host determina la versione GC predefinita.

  Le operazioni di Garbage Collection per workstation possono essere eseguite in modalità simultanea o non simultanea. La modalità simultanea consente ai thread gestiti di continuare le operazioni durante un'operazione di Garbage Collection. [L'operazione di Garbage Collection](#background-workstation-garbage-collection) in background sostituisce la [garbage collection simultanea](#concurrent-garbage-collection) in .NET Framework 4 e versioni successive.

- Garbage Collection per server, per le applicazioni server che richiedono scalabilità e velocità effettiva elevata.

  - In .NET Core la procedura di Garbage Collection per server può essere non simultanea o in background.

  - In .NET Framework 4.5.NET Framework 4.5 e versioni successive, l'operazione di Garbage Collection per server può essere non simultanea o in background (l'operazione di Garbage Collection in background sostituisce l'operazione di Garbage Collection simultanea). In .NET Framework 4 e versioni precedenti, la procedura di Garbage Collection per server non è simultanea.

Nella figura seguente vengono illustrati i thread dedicati che eseguono l'operazione di Garbage Collection in un server:The following illustration shows the dedicated threads that perform the garbage collection on a server:

![Thread di Garbage Collection server](./media/gc-server.png)

### <a name="compare-workstation-and-server-garbage-collection"></a>Confrontare le operazioni di Garbage Collection per workstation e server

Di seguito sono riportate alcune considerazioni su threading e prestazioni per l'operazione di Garbage Collection per workstation:

- La raccolta viene eseguita nel thread dell'utente che ha attivato l'operazione di Garbage Collection e mantiene la stessa priorità. Poiché i thread dell'utente vengono in genere eseguiti con priorità normale, il Garbage Collector (eseguito in un thread con priorità normale) deve competere con altri thread per il tempo CPU. I thread che eseguono codice nativo non vengono sospesi in caso di Garbage Collection per server o workstation.

- La procedura di Garbage Collection per workstation viene sempre utilizzata in un computer che dispone di un solo processore, indipendentemente [dall'impostazione](../../core/run-time-config/garbage-collector.md#systemgcservercomplus_gcserver)di configurazione.

Di seguito sono riportate alcune considerazioni su threading e prestazioni per l'operazione di Garbage Collection per server:

- La raccolta viene eseguita in più thread dedicati eseguiti con livello di priorità `THREAD_PRIORITY_HIGHEST` .

- Per ogni CPU vengono forniti un heap e un thread dedicato per l'esecuzione dell'operazione di Garbage Collection. Gli heap vengono raccolti contemporaneamente. Ogni heap contiene un heap degli oggetti piccoli e un heap degli oggetti grandi; è possibile accedere a tutti gli heap tramite codice utente. Gli oggetti contenuti in heap diversi possono fare riferimento l'un l'altro.

- Grazie all'utilizzo congiunto di più thread di Garbage Collection, le operazioni di Garbage Collection per server saranno più veloci delle operazioni per workstation in un heap di pari dimensioni.

- I segmenti di Garbage Collection per server sono spesso di dimensioni maggiori. Tuttavia, questa è solo una generalizzazione: la dimensione del segmento è specifica dell'implementazione ed è soggetta a modifiche. Non fare supposizioni sulle dimensioni dei segmenti allocati dal Garbage Collector durante l'ottimizzazione dell'app.

- Le operazioni di Garbage Collection per server possono richiedere un utilizzo di risorse elevato. Si supponga, ad esempio, che siano presenti 12 processi che utilizzano il catalogo globale del server in esecuzione in un computer con 4 processori. Se tutti i processi si verificano per raccogliere spazzatura allo stesso tempo, avrebbero interferire con l'altro, come ci sarebbero 12 thread pianificati sullo stesso processore. Se i processi sono attivi, non è una buona idea che tutti utilizzino il catalogo globale del server.

Se si eseguono centinaia di istanze di un'applicazione, prendere in considerazione l'utilizzo di Garbage Collection per workstation con l'operazione di Garbage Collection simultanea disabilitata. Si avranno meno cambi di contesto e un possibile miglioramento delle prestazioni.

## <a name="background-workstation-garbage-collection"></a>Garbage Collection della workstation in background

Nelle operazioni di Garbage Collection per workstation in background, le generazioni effimere (0 e 1) vengono raccolte in base alle esigenze mentre è in corso la raccolta della generazione 2. L'operazione di Garbage Collection per workstation in background viene eseguita su un thread dedicato e si applica solo alle raccolte di generazione 2.Background workstation garbage collection is performed on a dedicated thread and applies only to generation 2 collections.

L'operazione di Garbage Collection in background è abilitata per impostazione predefinita e può essere abilitata o disabilitata con l'impostazione di configurazione [gcConcurrent](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) nelle app di .NET Framework o l'impostazione [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) nelle app .NET Core.

> [!NOTE]
> L'operazione di Garbage Collection in background sostituisce [l'operazione di Garbage Collection simultanea](#concurrent-garbage-collection) ed è disponibile in .NET Framework 4 e versioni successive. In .NET Framework 4 è supportato solo per l'operazione di Garbage Collection per workstation. A partire da .NET Framework 4.5.NET Framework 4.5, l'operazione di Garbage Collection in background è disponibile sia per le operazioni di Garbage Collection per workstation che per i server.

Una raccolta nelle generazioni temporanee durante un'operazione in background è definita Garbage Collection in primo piano. Durante l'esecuzione di un'operazione di Garbage Collection in primo piano, tutti i thread gestiti vengono sospesi.

Quando è in corso un'operazione di Garbage Collection in background e sono stati allocati un numero sufficiente di oggetti nella generazione 0, CLR esegue un'operazione di Garbage Collection in primo piano di generazione 0 o generazione 1.When background garbage collection is in progress and you've allocated enough objects in generation 0, the CLR performs a generation 0 or generation 1 foreground garbage collection. Il thread di Garbage Collection in background dedicato esegue controlli in corrispondenza di punti sicuri frequenti per stabilire se vi sia una richiesta di Garbage Collection in primo piano. In caso affermativo, la raccolta in background si autosospende in modo che possa essere eseguita l'operazione in primo piano. Una volta completata tale operazione, si ha la ripresa del thread di Garbage Collection in background dedicato e dei thread dell'utente.

La modalità in background elimina le restrizioni di allocazione imposte dalla modalità simultanea, dal momento che durante un'operazione di Garbage Collection in background è possibile eseguire operazioni temporanee. La procedura di Garbage Collection in background può rimuovere oggetti morti in generazioni effimere. Può anche espandere l'heap se necessario durante un'operazione di Garbage Collection di generazione 1.It can also expand the heap if needed during a generation 1 garbage collection.

La figura seguente illustra l'esecuzione in background di un'operazione di Garbage Collection in un thread dedicato separato su una workstation:

![Garbage Collection della workstation in background](./media/fundamentals/background-workstation-garbage-collection.png)

### <a name="background-server-garbage-collection"></a>Garbage Collection del server in background

A partire da .NET Framework 4.5.NET Framework 4.5.NET Framework 4.5.NET Framework 4.5.NET Framework 4.5.NET Framework 4.5.NET Framework 4.5, background server garbage collection è la modalità predefinita per l'operazione di Garbage Collection per server.

L'operazione di Garbage Collection per server in background funziona in modo simile all'operazione di Garbage Collection per workstation in background, descritta nella sezione precedente, ma esistono alcune differenze:

- L'operazione di Garbage Collection per workstation in background utilizza un thread di Garbage Collection in background dedicato, mentre l'operazione di Garbage Collection per server in background utilizza più thread. In genere, è presente un thread dedicato per ogni processore logico.

- A differenza del thread di Garbage Collection in background per workstation, questi thread non scadono.

La figura seguente illustra l'esecuzione in background di un'operazione di Garbage Collection in un thread dedicato separato su un server:

![Garbage Collection del server in background](./media/fundamentals/background-server-garbage-collection.png)

## <a name="concurrent-garbage-collection"></a>Garbage Collection contemporanea

> [!TIP]
> Questa sezione si applica a:
>
> - .NET Framework 3.5 e versioni precedenti per l'operazione di Garbage Collection per workstation
> - .NET Framework 4 e versioni precedenti per l'operazione di Garbage Collection per server
>
> I rifiuti simultanei vengono sostituiti da [garbage collection](#background-workstation-garbage-collection) in background nelle versioni successive.

Nell'operazione di Garbage Collection per workstation o server è possibile [abilitare l'operazione](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)di Garbage Collection simultanea, che consente l'esecuzione simultanea dei thread con un thread dedicato che esegue l'operazione di Garbage Collection per la maggior parte della durata dell'operazione. Questa opzione riguarda solo le operazioni di Garbage Collection nella generazione 2; le generazioni 0 e 1 sono sempre non simultanee in quanto terminano molto velocemente.

La modalità simultanea consente alle applicazioni interattive una maggiore efficienza di risposta riducendo al minimo le pause di una raccolta. È possibile continuare a eseguire i thread gestiti per la maggior parte del tempo in cui viene eseguito il thread di Garbage Collection in modalità simultanea. Il risultato saranno pause più brevi durante l'esecuzione di un'operazione di Garbage Collection.

La modalità simultanea di Garbage Collection viene eseguita in un thread dedicato. Per impostazione predefinita, CLR esegue le operazioni di Garbage Collection per workstation con la modalità simultanea abilitata. Ciò vale tanto per i computer a processore singolo quanto per quelli multiprocessore.

Nell'illustrazione riportata di seguito viene mostrata l'esecuzione simultanea di un'operazione di Garbage Collection in un thread dedicato separato.

![Thread di Garbage Collection simultanei](./media/gc-concurrent.png)

## <a name="see-also"></a>Vedere anche

- [Opzioni di configurazione per GC](../../core/run-time-config/garbage-collector.md)
- [Garbage Collection](index.md)
