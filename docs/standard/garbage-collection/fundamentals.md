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
ms.openlocfilehash: d59f368f21964c07d371df604f0728fa6ca8ac00
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307033"
---
# <a name="fundamentals-of-garbage-collection"></a>Principi fondamentali di Garbage Collection

Nel Common Language Runtime (CLR), il Garbage Collector (GC) funge da gestore di memoria automatico. Il Garbage Collector gestisce l'allocazione e il rilascio di memoria per un'applicazione. Per gli sviluppatori che utilizzano codice gestito, questo significa che non è necessario scrivere codice per eseguire attività di gestione della memoria. La gestione automatica della memoria può eliminare i problemi comuni, ad esempio dimenticando di liberare un oggetto e causando una perdita di memoria o provando ad accedere alla memoria per un oggetto già liberato.

Questo articolo descrive i concetti di base di Garbage Collection.

## <a name="benefits"></a>Vantaggi

Il Garbage Collector offre i vantaggi seguenti:

- Consente agli sviluppatori di liberare manualmente la memoria.

- Alloca gli oggetti nell'heap gestito in maniera efficiente.

- Recupera gli oggetti inutilizzati, ne cancella la memoria e tiene la memoria a disposizione per le future allocazioni. Gli oggetti gestiti ottengono automaticamente contenuto pulito da cui iniziare, pertanto i costruttori non devono inizializzare ogni campo dati.

- Garantisce protezione per la memoria assicurando che un oggetto non possa usare il contenuto di un altro oggetto.

## <a name="fundamentals-of-memory"></a>Nozioni fondamentali sulla memoria

Nell'elenco seguente sono riepilogati concetti importanti relativi alla memoria CLR.

- Ogni processo dispone di un proprio spazio degli indirizzi virtuali distinto. Tutti i processi nello stesso computer condividono la stessa memoria fisica e il file di paging, se presente.

- Per impostazione predefinita, nei computer a 32 bit ogni processo dispone di uno spazio degli indirizzi virtuali in modalità utente da 2 GB.

- Uno sviluppatore di applicazioni usa solo lo spazio degli indirizzi virtuali e non modifica mai direttamente la memoria fisica. Il Garbage Collector alloca e libera automaticamente la memoria virtuale nell'heap gestito.

  Se si sta scrivendo codice nativo, si usano le funzioni di Windows per lavorare con lo spazio degli indirizzi virtuali. Queste funzioni allocano e liberano automaticamente la memoria virtuale negli heap nativi.

- La memoria virtuale può trovarsi in tre stati:

  | State | Descrizione |
  |---------|---------|
  | Gratuito | Non vi sono riferimenti al blocco di memoria, che è disponibile per l'allocazione. |
  | Riservato | Il blocco di memoria è disponibile per l'utilizzo e non può essere usato da un'altra richiesta di allocazione. Non è tuttavia possibile archiviare i dati in questo blocco di memoria fino a quando non viene eseguito il commit. |
  | Impegnato | Il blocco di memoria è assegnato all'archiviazione fisica. |

- Lo spazio degli indirizzi virtuali può diventare frammentato. Ciò significa che sono presenti blocchi liberi, noti anche come buchi, nello spazio degli indirizzi. Quando viene richiesta un'allocazione della memoria virtuale, il gestore di memoria virtuale deve trovare un singolo blocco libero con dimensioni sufficienti per soddisfare la richiesta di allocazione. Anche se si dispone di 2 GB di spazio libero, un'allocazione che richiede 2 GB avrà esito negativo a meno che tutto lo spazio libero non si trovi in un unico blocco di indirizzi.

- Se lo spazio degli indirizzi virtuali da riservare o lo spazio fisico di cui eseguire il commit non è sufficiente, è possibile che si esaurisca la memoria.

  Il file di paging viene utilizzato anche se la pressione della memoria fisica (ovvero la richiesta di memoria fisica) è bassa. La prima volta che la quantità di memoria fisica è elevata, il sistema operativo deve fare spazio nella memoria fisica per archiviare i dati e quindi eseguire il backup di alcuni dei dati presenti nella memoria fisica nel file di paging. I dati non vengono sottoposto a paging fino a quando non sono necessari, quindi è possibile che si verifichi il paging in situazioni in cui la pressione della memoria fisica è insufficiente.
  
### <a name="memory-allocation"></a>Allocazione di memoria

Quando si inizializza un nuovo processo, per tale processo viene riservata una regione contigua di spazio degli indirizzi. Lo spazio degli indirizzi riservato viene definito heap gestito. Nell'heap gestito viene conservato un puntatore all'indirizzo in cui verrà allocato il successivo oggetto dell'heap. Le impostazioni iniziali del puntatore corrispondono all'indirizzo di base dell'heap gestito. Tutti i tipi di riferimento vengono allocati nell'heap gestito. Quando il primo tipo di riferimento viene creato da un'applicazione, per tale tipo viene allocata memoria nell'indirizzo di base dell'heap gestito. Quando l'oggetto successivo viene creato dall'applicazione, la memoria destinata a tale oggetto viene allocata dal Garbage Collector nello spazio degli indirizzi immediatamente successivo al primo oggetto. Lo spazio per i nuovi oggetti verrà allocato in questo modo dal Garbage Collector fino all'esaurimento dello spazio degli indirizzi.

L'allocazione della memoria dall'heap gestito risulta più veloce dell'allocazione di memoria non gestita. Poiché il runtime alloca memoria per un oggetto aggiungendo un valore a un puntatore, è quasi altrettanto veloce dell'allocazione di memoria dallo stack. Poiché inoltre i nuovi oggetti allocati consecutivamente vengono archiviati in modo contiguo nell'heap gestito, un'applicazione può accedere rapidamente agli oggetti.

### <a name="memory-release"></a>Versione memoria

Il modulo di ottimizzazione del Garbage Collector consente di determinare il momento migliore per l'esecuzione di una raccolta sulla base delle allocazioni in corso. Durante l'esecuzione di una raccolta, la memoria per gli oggetti non più utilizzati dall'applicazione viene rilasciata dal Garbage Collector. Determina quali oggetti non vengono più utilizzati esaminando le *radici*dell'applicazione. Le radici di un'applicazione includono campi statici, variabili e parametri locali su uno stack di thread e registri della CPU. Ogni radice fa riferimento a un oggetto dell'heap gestito o è impostata su null. Garbage Collector ha accesso all'elenco delle radici attive mantenute dal compilatore JIT e dal runtime. Utilizzando questo elenco, il Garbage Collector crea un grafico contenente tutti gli oggetti raggiungibili dalle radici.

Gli oggetti non inclusi nel grafo non sono raggiungibili dalle radici dell'applicazione. Il Garbage Collector considera gli oggetti non raggiungibili Garbage Collection e rilascia la memoria allocata per tali oggetti. Nel corso di una raccolta, l'heap gestito viene esaminato dal Garbage Collector, alla ricerca dei blocchi di spazi degli indirizzi occupati da oggetti non raggiungibili. Quando un oggetto non raggiungibile viene rilevato, viene utilizzata una funzione di copia della memoria che consente di ricompattare lo spazio allocato per gli oggetti ancora raggiungibili nella memoria, liberando i blocchi di spazi degli indirizzi allocati per oggetti non raggiungibili. Una volta compattata la memoria per gli oggetti non raggiungibili, il Garbage Collector aggiorna i puntatori agli oggetti ai rispettivi nuovi indirizzi, in modo che le radici dell'applicazione puntino agli oggetti nelle rispettive nuove posizioni. Il puntatore relativo all'heap gestito viene inoltre posizionato dopo l'ultimo oggetto non raggiungibile.

La memoria viene compattata solo se una raccolta rileva un numero significativo di oggetti non raggiungibili. Se tutti gli oggetti dell'heap gestito superano la raccolta, non è necessaria alcuna compressione della memoria.

Per migliorare le prestazioni, la memoria per oggetti di grandi dimensioni viene allocata da Common Language Runtime in un heap separato. La memoria per oggetti di grandi dimensioni viene rilasciata automaticamente dal Garbage Collector. Tuttavia, per evitare lo trasferimento di oggetti di grandi dimensioni in memoria, questa memoria non viene in genere compattata.

## <a name="conditions-for-a-garbage-collection"></a>Condizioni per un'operazione di Garbage Collection

Le operazioni di Garbage Collection vengono eseguite in presenza di una delle seguenti condizioni:

- La memoria fisica del sistema è insufficiente. Questa condizione viene rilevata dalla notifica di memoria insufficiente dal sistema operativo o da una memoria insufficiente come indicato dall'host.

- La memoria usata dagli oggetti allocati nell'heap gestito supera una soglia accettabile. Questa soglia viene continuamente modificata durante l'esecuzione del processo.

- Viene chiamato il metodo <xref:System.GC.Collect%2A?displayProperty=nameWithType> . In quasi tutti i casi, non è necessario chiamare questo metodo, perché il Garbage Collector viene eseguito in modo continuo. Il metodo viene usato principalmente in situazioni eccezionali e per scopi di test.

## <a name="the-managed-heap"></a>Heap gestito

Dopo essere stato inizializzato da CLR, il Garbage Collector alloca un segmento di memoria per archiviare e gestire oggetti. Questa memoria è definita heap gestito, in contrapposizione a un heap nativo presente nel sistema operativo.

Per ogni processo gestito esiste un heap gestito. Tutti i thread nel processo allocano memoria per gli oggetti sullo stesso heap.

Per riservare memoria, il Garbage Collector chiama la funzione [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) di Windows e riserva un segmento di memoria alla volta per le applicazioni gestite. Il Garbage Collector riserva inoltre i segmenti, se necessario, e rilascia i segmenti al sistema operativo (dopo aver cancellato tutti gli oggetti) chiamando la funzione [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) di Windows.

> [!IMPORTANT]
> La dimensione dei segmenti allocati dal Garbage Collector è specifica dell'implementazione ed è soggetta a modifiche in qualsiasi momento, tra cui aggiornamenti periodici. L'applicazione non deve dare per scontata o dipendere da una particolare dimensione del segmento, né provare a configurare la quantità di memoria disponibile per le allocazioni di segmenti.

Minore è il numero di oggetti allocati nell'heap, minore sarà il lavoro del Garbage Collector. Quando si allocano oggetti, non usare valori arrotondati per eccesso che superino le proprie esigenze, ad esempio l'allocazione di una matrice di 32 byte quando sono necessari solo 15 byte.

Quando viene attivata una Garbage Collection, il Garbage Collector recupera la memoria occupata dagli oggetti inattivi. Durante il processo di recupero, gli oggetti attivi vengono compattati in modo da poter essere spostati insieme e lo spazio inutilizzato viene rimosso, riducendo le dimensioni dell'heap. In questo modo si garantisce che gli oggetti allocati insieme restino insieme nell'heap gestito per conservarne la località.

L'impatto (frequenza e durata) delle operazioni di Garbage Collection è il risultato del volume di allocazioni e della quantità di memoria esclusa nell'heap gestito.

L'heap può essere considerato l'insieme di due heap: l'[heap degli oggetti grandi](large-object-heap.md) e l'heap degli oggetti piccoli. L'heap degli oggetti grandi contiene oggetti di 85.000 byte e più grandi, che sono in genere matrici. È raro che un oggetto istanza sia estremamente grande.

> [!TIP]
> È possibile [configurare le dimensioni della soglia](../../core/run-time-config/garbage-collector.md#large-object-heap-threshold) per gli oggetti da usare nell'heap degli oggetti grandi.

## <a name="generations"></a>Generazioni

L'algoritmo GC si basa su diverse considerazioni:

- È più veloce compattare la memoria per una parte dell'heap gestito rispetto all'intero heap gestito.
- Gli oggetti più recenti hanno una durata più breve e gli oggetti meno recenti hanno una durata maggiore.
- Gli oggetti più recenti tendono a essere correlati gli uni agli altri e a cui l'applicazione accede più a lungo.

Il processo di Garbage Collection si verifica principalmente con il recupero di oggetti di breve durata. Per ottimizzare le prestazioni dell'Garbage Collector, l'heap gestito è diviso in tre generazioni, 0, 1 e 2, in modo da poter gestire oggetti di lunga durata e di breve durata separatamente. Il Garbage Collector archivia nuovi oggetti nella generazione 0. Gli oggetti creati nelle prime fasi della durata dell'applicazione che non vengono raccolti vengono promossi e archiviati nelle generazioni 1 e 2. Poiché è più veloce comprimere una parte dell'heap gestito rispetto all'intero heap, questo schema consente al Garbage Collector di rilasciare la memoria in una determinata generazione anziché rilasciare la memoria per l'intero heap gestito ogni volta che viene eseguita una raccolta.

- **Generazione 0**. È la generazione più recente e contiene oggetti di breve durata. Un esempio di oggetto di breve durata è una variabile temporanea. Le operazioni di Garbage Collection vengono eseguite il più delle volte in questa generazione.

  Gli oggetti appena allocati formano una nuova generazione di oggetti e sono implicitamente raccolte di generazione 0. Tuttavia, se si tratta di oggetti di grandi dimensioni, vengono inseriti nell'heap degli oggetti grandi (LOH), a volte definito *generazione 3*. Generazione 3 è una generazione fisica che viene raccolta logicamente come parte della generazione 2.

  La maggior parte degli oggetti vengono recuperati per Garbage Collection nella generazione 0 e non sopravvivono alla prossima generazione.
  
  Se un'applicazione tenta di creare un nuovo oggetto quando la generazione 0 è piena, il Garbage Collector esegue una raccolta in un tentativo di liberare spazio degli indirizzi per l'oggetto. Il Garbage Collector esamina prima di tutto gli oggetti presenti nella generazione 0, anziché tutti gli oggetti presenti nell'heap gestito. Una raccolta di sola generazione 0 recupera spesso memoria sufficiente per consentire all'applicazione di continuare a creare nuovi oggetti.

- **Generazione 1**. Questa generazione contiene oggetti di breve durata e funge da buffer tra gli oggetti di breve durata e gli oggetti di lunga durata.

  Dopo che il Garbage Collector esegue una raccolta della generazione 0, comprime la memoria per gli oggetti raggiungibili e li promuove alla generazione 1. Poiché la durata degli oggetti non raccolti è solitamente più lunga, la promozione a una generazione superiore risulta opportuna. Il Garbage Collector non deve riesaminare gli oggetti nelle generazioni 1 e 2 ogni volta che viene eseguita una raccolta di generazione 0.
  
  Se una raccolta di generazione 0 non recupera memoria sufficiente per l'applicazione per la creazione di un nuovo oggetto, il Garbage Collector può eseguire una raccolta di generazione 1, quindi generazione 2. Gli oggetti presenti nella generazione 1 non raccolti vengono promossi alla generazione 2.

- **Generazione 2**. Questa generazione contiene oggetti di lunga durata. Un esempio di oggetto di lunga durata è un oggetto in un'applicazione server contenente dati statici attivi per tutta la durata del processo.

  Gli oggetti della generazione 2 che sopravvivono a una raccolta rimangono nella generazione 2 fino a quando non vengono determinati come irraggiungibili in una raccolta futura.
  
  Gli oggetti nell'heap degli oggetti grandi (a volte definito *generazione 3*) vengono raccolti anche nella generazione 2.

Le operazioni di Garbage Collection vengono eseguite in generazioni specifiche a seconda delle condizioni. Raccogliere una generazione significa raccogliere gli oggetti in quella generazione e in tutte le generazioni più recenti. Una Garbage Collection di generazione 2 è nota anche come Garbage Collection completa, in quanto recupera gli oggetti in tutte le generazioni, ovvero tutti gli oggetti nell'heap gestito.

### <a name="survival-and-promotions"></a>Esclusione e promozioni

Gli oggetti che non vengono recuperati in una Garbage Collection sono noti come superstiti e vengono promossi alla generazione successiva:

- Gli oggetti che sopravvivono a un Garbage Collection di generazione 0 vengono promossi alla generazione 1.
- Gli oggetti che sopravvivono a un Garbage Collection di generazione 1 vengono promossi alla generazione 2.
- Gli oggetti che sopravvivono a una generazione 2 Garbage Collection rimangono nella generazione 2.

Quando il Garbage Collector rileva che il tasso di sopravvivenza è elevato in una generazione, aumenta la soglia delle allocazioni per tale generazione. La raccolta successiva ottiene una dimensione sostanziale della memoria recuperata. CLR bilancia continuamente due priorità: non consentire a un working set di un'applicazione di essere troppo grande ritardando Garbage Collection e non consentendo l'esecuzione troppo frequente dei Garbage Collection.

### <a name="ephemeral-generations-and-segments"></a>Generazioni e segmenti temporanei

Poiché gli oggetti nelle generazioni 0 e 1 sono di breve durata, queste generazioni sono note come *generazioni effimere*.

Le generazioni effimere vengono allocate nel segmento di memoria noto come segmento temporaneo. Ogni nuovo segmento acquisito dal Garbage Collector diventa il nuovo segmento temporaneo e contiene gli oggetti esclusi da un'operazione di Garbage Collection di generazione 0. Il segmento temporaneo precedente diventa il nuovo segmento di generazione 2.

La dimensione del segmento temporaneo varia a seconda che un sistema sia a 32 bit o a 64 bit e sul tipo di Garbage Collector in esecuzione ([GC workstation o server](workstation-server-gc.md)). La tabella seguente mostra le dimensioni predefinite del segmento temporaneo.

|GC workstation/server|32 bit|64 bit|
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

  In genere, l'heap degli oggetti grandi (LOH) non viene compattato, perché la copia di oggetti di grandi dimensioni impone una riduzione delle prestazioni. Tuttavia, in .NET Core e in .NET Framework 4.5.1 e versioni successive, è possibile usare la <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> proprietà per comprimere l'heap oggetti grandi su richiesta. Inoltre, l'heap oggetti grandi viene compattato automaticamente quando si imposta un limite rigido specificando uno dei seguenti valori:

  - Limite di memoria per un contenitore.
  - Opzioni di configurazione della fase di esecuzione [GCHeapHardLimit](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitcomplus_gcheaphardlimit) o [GCHeapHardLimitPercent](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) .

Per stabilire se gli oggetti sono attivi, il Garbage Collector usa le seguenti informazioni:

- **Radici dello stack**. Variabili dello stack fornite dal compilatore JIT e dal percorso di chiamate nello stack. Le ottimizzazioni JIT possono allungare o ridurre le aree di codice in cui vengono segnalate le variabili dello stack al Garbage Collector.

- **Handle di Garbage Collection**. Handle che puntano agli oggetti gestiti e che possono essere allocati mediante codice utente o Common Language Runtime.

- **Dati statici**. Oggetti statici nei domini applicazione che possono fare riferimento ad altri oggetti. Ogni dominio applicazione tiene traccia dei rispettivi oggetti statici.

Prima di eseguire un'operazione di Garbage Collection, tutti i thread gestiti vengono sospesi, eccetto il thread che attiva l'operazione.

Nell'illustrazione seguente viene illustrato un thread che attiva un'operazione di Garbage Collection causando la sospensione degli altri thread.

![Thread che attiva un'operazione di Garbage Collection](media/gc-triggered.png)

## <a name="unmanaged-resources"></a>Risorse non gestite

Per la maggior parte degli oggetti creati dall'applicazione, è possibile fare affidamento su Garbage Collection per eseguire automaticamente le attività di gestione della memoria necessarie. Per le risorse non gestite è tuttavia necessario il rilascio esplicito. Il tipo più comune di risorsa non gestita è rappresentato da un oggetto che esegue il wrapping di una risorsa del sistema operativo, quale un handle di file, un handle di finestra o una connessione di rete. Sebbene il Garbage Collector sia in grado di tenere traccia della durata di un oggetto gestito che incapsula una risorsa non gestita, non ha informazioni specifiche su come pulire la risorsa.

Quando si crea un oggetto che incapsula una risorsa non gestita, è consigliabile specificare il codice necessario per pulire la risorsa non gestita in un `Dispose` Metodo pubblico. Specificando un metodo `Dispose` si consente agli utenti dell'oggetto di liberarne esplicitamente la memoria dopo l'uso dell'oggetto. Quando si usa un oggetto che incapsula una risorsa non gestita, assicurarsi di chiamare `Dispose` se necessario.

È inoltre necessario fornire un modo per rilasciare le risorse non gestite nel caso in cui un consumer del tipo dimentichi di chiamare `Dispose` . È possibile utilizzare un handle sicuro per eseguire il wrapping della risorsa non gestita oppure eseguire l'override del <xref:System.Object.Finalize?displayProperty=nameWithType> metodo.

Per altre informazioni sulla pulizia di risorse non gestite, vedere [pulire le risorse non gestite](unmanaged.md).

## <a name="see-also"></a>Vedere anche

- [Operazione di Garbage Collection per workstation e server](workstation-server-gc.md)
- [Garbage Collection in background](background-gc.md)
- [Opzioni di configurazione per GC](../../core/run-time-config/garbage-collector.md)
- [Garbage Collection](index.md)
