---
title: Heap oggetti grandi (LOH) in Windows
ms.date: 05/02/2018
helpviewer_keywords:
- large object heap (LOH)"
- LOH
- garbage collection, large object heap
- GC [.NET ], large object heap
ms.openlocfilehash: ab9beca58b3d6118bc0f5121b6f5dec71a9f9f36
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102268"
---
# <a name="the-large-object-heap-on-windows-systems"></a>Heap oggetti grandi nei sistemi Windows

Il Garbage Collector (GC) di .NET divide gli oggetti in oggetti di piccole e grandi dimensioni. Nel caso di un oggetto grande, alcuni attributi associati assumono un'importanza maggiore rispetto a quando sono associati a un oggetto piccolo. Ad esempio, compattarlo&mdash;in questo modo, copiarlo&mdash;in memoria in un altro punto dell'heap può essere costoso. Per questo motivo, il Garbage Collector inserisce oggetti di grandi dimensioni nell'heap oggetti grandi (LOH). In questo articolo viene illustrato che cosa qualifica un oggetto come un oggetto di grandi dimensioni, come vengono raccolti gli oggetti di grandi dimensioni e che tipo di prestazioni implicazioni comporta oggetti di grandi dimensioni impliche.

> [!IMPORTANT]
> In questo articolo viene illustrato l'heap oggetti grandi in .NET Framework e .NET Core in esecuzione solo su sistemi Windows. Non riguarda l'heap oggetti grandi in esecuzione in implementazioni di .NET su altre piattaforme.

## <a name="how-an-object-ends-up-on-the-loh"></a>Come un oggetto finisce sul LOH

Se un oggetto è maggiore o uguale a 85.000 byte, viene considerato un oggetto di grandi dimensioni. Questo valore è stato determinato dall'ottimizzazione delle prestazioni. Quando la richiesta di allocazione di un oggetto supera gli 85.000 byte, il runtime destina l'oggetto all'heap oggetti grandi.

Per comprendere il significato di questo, è utile esaminare alcuni aspetti fondamentali relativi al Garbage Collector.

Il Garbage Collector è un agente di raccolta generazionale. Le generazioni sono tre: generazione 0, generazione 1 e generazione 2. La presenza di 3 generazioni deriva dal fatto che in un'app ottimizzata la maggior parte degli oggetti viene eliminata nella generazione 0. In un'applicazione server, ad esempio, le allocazioni associate a ogni richiesta dovrebbero essere eliminate al termine della richiesta. Le richieste di allocazione durante l'esecuzione raggiungono la generazione 1 e vengono eliminate in questa generazione. In pratica la generazione 1 fa da buffer tra le aree degli oggetti recenti e quelle degli oggetti con durata maggiore.

Gli oggetti piccoli vengono sempre allocati nella generazione 0 e a seconda della loro ciclo di vita possono passare alla generazione 1 o alla generazione 2. Gli oggetti grandi vengono sempre allocati nella generazione 2.

Gli oggetti grandi appartengono alla generazione 2 perché vengono raccolti solo durante una raccolta di generazione 2. Quando viene raccolta una generazione, vengono raccolte anche le generazioni più giovani corrispondenti. Ad esempio quando si verifica un'operazione GC di generazione 1 vengono raccolte sia la generazione 1 che la generazione 0. Quando si verifica un'operazione GC di generazione 2 viene raccolto l'intero heap. Per questo motivo un'operazione GC di generazione 2 è anche detta *operazione GC completa*. L'articolo cita l'operazione GC di generazione 2 anziché l'operazione GC completa, ma i termini sono intercambiabili.

Le generazioni offrono una visualizzazione logica dell'heap GC. A livello fisico gli oggetti si trovano in segmenti gestiti dell'heap. Un *segmento gestito dell'heap* è una parte di memoria che l'operazione GC riserva nel sistema operativo (chiamando la [funzione VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc)) per conto del codice gestito. Quando CLR viene caricato, il Garbage Collector alloca due segmenti di heap iniziali: uno per gli oggetti di piccole dimensioni (l'heap oggetti piccoli o SOH) e uno per gli oggetti di grandi dimensioni (l'heap oggetti grandi).

Le richieste di allocazione vengono quindi soddisfatte inserendo gli oggetti gestiti in uno di questi segmenti di heap gestiti. Se l'oggetto ha dimensioni inferiori a 85.000 byte viene inserito in un segmento SOH; in caso contrario viene inserito in un segmento LOH. Man mano che nei segmenti vengono allocati gli oggetti, tali segmenti vengono impegnati (in blocchi più piccoli).
Per l'heap oggetti piccoli, gli oggetti ancora attivi dopo un'operazione GC vengono promossi alla generazione successiva. Gli oggetti esclusi da una raccolta di generazione 0 sono ora considerati oggetti di generazione 1 e così via. Gli oggetti che raggiungono la generazione di grado superiore si considerano come appartenenti a tale generazione. In altri termini gli oggetti che rimangono nella generazione 2 sono oggetti di generazione 2 e gli oggetti che rimangono nel segmento LOH sono oggetti LOH (raccolti con la generazione 2).

Il codice utente può effettuare allocazioni solo nella generazione 0 (oggetti piccoli) o nell'heap oggetti grandi (LOH). Soltanto l'operazione GC può "allocare" gli oggetti nella generazione 1 (promuovendo i superstiti della generazione 0) e nella generazione 2 (promuovendo i superstiti delle generazioni 1 e 2).

Quando viene attivata una Garbage Collection, il Garbage Collector rintraccia gli oggetti ancora attivi e li compatta. Tuttavia, dato che la compattazione è dispendiosa in termini di risorse, il GC *effettua lo sweep* dell'heap oggetti grandi e crea un elenco degli oggetti inattivi che possono essere riusati successivamente per soddisfare le richieste di allocazione di oggetti grandi. Gli oggetti inattivi adiacenti vengono trasformati in un unico oggetto libero.

.NET core e .NET Framework (a partire da .NET Framework 4.5.1) includono la proprietà <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?displayProperty=nameWithType> che consente agli utenti di specificare che l'heap oggetti grandi dovrà essere compresso durante la successiva operazione GC completa e bloccante. In futuro è possibile che .NET scelga di compattare automaticamente l'heap oggetti grandi. Quindi se si allocano oggetti grandi e si vuole essere certi che non verranno spostati, è ancora necessario bloccarli.

La figura 1 illustra uno scenario in cui GC forma la generazione 1 dopo la prima operazione GC di generazione 0 in cui `Obj1` e `Obj3` sono inattivi e forma la generazione 2 dopo la prima operazione GC di generazione 1 in cui `Obj2` e `Obj5` sono inattivi. Si noti che questa figura e le successive sono incluse a semplice scopo illustrativo e contengono pochissimi oggetti per illustrare meglio cosa accade nell'heap. In realtà un'operazione GC include in genere un numero di oggetti molto più elevato.

![Figura 1: GC generazione 0 e GC generazione 1](media/loh/loh-figure-1.jpg)\
Figura 1: GC generazione 0 e GC generazione 1.

Nella figura 2, dopo un'operazione GC di generazione 2 in cui viene rilevato che `Obj1` e `Obj2` sono inattivi, il Garbage Collector crea spazio libero contiguo con la memoria occupata in precedenza da `Obj1` e `Obj2` e tale memoria viene usata per soddisfare una richiesta di allocazione per `Obj4`. Anche lo spazio dopo l'ultimo oggetto, `Obj3`, e fino alla fine del segmento può essere usato per soddisfare richieste di allocazione.

![Figura 2: Dopo un'operazione GC di generazione 2](media/loh/loh-figure-2.jpg)\
Figura 2: Dopo un'operazione GC di generazione 2

Se lo spazio libero non è sufficiente ad accogliere le richieste di allocazione di oggetti grandi, inizialmente GC prova a ottenere altri segmenti dal sistema operativo. Se il problema persiste, attiva un'operazione GC di generazione 2 per liberare spazio.

Durante un'operazione GC di generazione 1 o 2 il Garbage Collector rilascia i segmenti privi di oggetti attivi al sistema operativo chiamando la [funzione VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree). Viene annullato il commit dello spazio dopo l'ultimo oggetto attivo alla fine del segmento (salvo per il segmento effimero in cui risiedono gen0/gen1 e dove il Garbage Collector mantiene spazio con commit, perché l'applicazione lo alloca quasi immediatamente). Gli spazi liberi mantengono il commit anche se vengono reimpostati, a indicare che il sistema operativo non ha bisogno di riscrivere su disco i dati in essi contenuti.

Dato che l'heap oggetti grandi viene raccolto solo durante operazioni GC di generazione 2, il segmento LOH può essere liberato solo durante un' operazione GC di questo tipo. La figura 3 illustra uno scenario in cui il Garbage Collector rilascia un segmento (segmento 2) al sistema operativo e annulla il commit di altro spazio nei segmenti rimanenti. Se il Garbage Collector deve usare lo spazio liberato alla fine del segmento per soddisfare nuove richieste di allocazione di oggetti grandi, esegue di nuovo il commit della memoria. Per una spiegazione del commit e dell'annullamento del commit, vedere la documentazione relativa a [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc).

![Figura 3: LOH dopo un'operazione GC di generazione 2](media/loh/loh-figure-3.jpg)\
Figura 3: LOH dopo un'operazione GC di generazione 2

## <a name="when-is-a-large-object-collected"></a>Quando viene raccolto un oggetto di grandi dimensioni?

In generale, un GC si verifica in una delle seguenti tre condizioni:

- L'allocazione supera la soglia della generazione 0 o degli oggetti grandi.

  La soglia è una proprietà di una generazione. Una soglia per una generazione viene impostata quando il Garbage Collector alloca oggetti al suo interno. Quando la soglia viene superata viene attivata un'operazione GC su questa generazione. Pertanto, quando si allocano oggetti piccoli o grandi, si consumano rispettivamente le soglie della generazione 0 e dell'heap oggetti grandi. Quando il Garbage Collector effettua allocazioni nelle generazioni 1 e 2, consuma le soglie di queste generazioni. Queste soglie vengono regolate dinamicamente mentre viene eseguito il programma.

  Questo è lo scenario tipico: la maggior parte delle operazioni GC si verifica come conseguenza delle allocazioni nell'heap gestito.

- Viene chiamato il metodo <xref:System.GC.Collect%2A?displayProperty=nameWithType> .

  Se viene chiamato il metodo senza parametri <xref:System.GC.Collect?displayProperty=nameWithType> o se <xref:System.GC.MaxGeneration?displayProperty=nameWithType> viene passato come argomento a un altro overload, l'heap oggetti grandi viene raccolto insieme al resto dell'heap gestito.

- La memoria del sistema è insufficiente.

  Questo si verifica quando il Garbage Collector riceve una notifica di uso di memoria elevato dal sistema operativo. Se il Garbage Collector rileva condizioni produttive per un'operazione GC di generazione 2, attiva tale operazione.

## <a name="loh-performance-implications"></a>Implicazioni delle prestazioni LOH

Le allocazioni nell'heap oggetti grandi influiscono sulle prestazioni nei modi seguenti.

- Costo di allocazione.

  Il CLR garantisce che la memoria per ogni nuovo oggetto inattivo venga liberata. Ciò significa che il costo di allocazione di un oggetto grande è totalmente determinato dalla liberazione della memoria (a meno che non attivi un'operazione GC). Mentre per liberare un byte sono sufficienti due cicli, per liberare il più piccolo degli oggetti grandi sono necessari 170.000 cicli. La cancellazione dalla memoria di un oggetto di 16 MB in un computer a 2 GHz richiede circa 16 ms. Si tratta di un costo operativo elevato.

- Costo dell'operazione di raccolta.

  Poiché le operazioni GC per l'heap oggetti grandi e la generazione 2 avvengono insieme, se una delle due soglie viene superata si attiva una raccolta di generazione 2. Se la raccolta di generazione 2 viene attivata a causa dell'heap oggetti grandi, il volume della generazione 2 potrebbe non risultare di molto ridotto dopo l'operazione GC. Se la generazione 2 non contiene molti dati l'impatto è minimo. Se tuttavia il volume di dati di generazione 2 è importante, può causare problemi di prestazioni se vengono attivate varie operazioni GC di generazione 2. Se molti oggetti grandi vengono allocati su base molto volatile e l'heap oggetti piccoli è molto grande, le operazioni GC potrebbero richiedere un tempo eccessivo. Il costo in termini di allocazione può diventare importante se si allocano e rilasciano continuamente oggetti molto grandi.

- Elementi di matrice con tipi di riferimento.

  Gli oggetti molto grandi dell'heap oggetti grandi sono normalmente costituiti da matrici (è poco comune che un oggetto istanza sia davvero molto grande). Se gli elementi della matrice hanno molti riferimenti, questo comporta un costo che non è presente se gli elementi non includono tali riferimenti. Se l'elemento non contiene nessun riferimento, il Garbage Collector non analizza la matrice. Se ad esempio si usa una matrice per memorizzare nodi in un albero binario, un metodo di implementazione è la creazione di un riferimento tra i nodi destro e sinistro di un nodo in base ai nodi effettivi:

  ```csharp
  class Node
  {
     Data d;
     Node left;
     Node right;
  };

  Node[] binary_tr = new Node [num_nodes];
  ```

  Se `num_nodes` è molto grande, il Garbage Collector deve elaborare almeno due riferimenti per ogni elemento. Un approccio alternativo è la memorizzazione dell'indice dei nodi destro e sinistro:

  ```csharp
  class Node
  {
     Data d;
     uint left_index;
     uint right_index;
  } ;
  ```

  Anziché fare riferimento ai dati del nodo sinistro come `left.d` si fa riferimento a tali dati come `binary_tr[left_index].d`. Il Garbage Collector non deve verificare riferimenti per i nodi sinistro e destro.

Fra i tre fattori, i primi due sono in genere più significativi del terzo. Per questo motivo è consigliabile allocare un pool di oggetti grandi da usare più volte anziché allocare oggetti temporanei.

## <a name="collect-performance-data-for-the-loh"></a>Raccogliere i dati sulle prestazioni per il LaOHCollect performance data for the LOH

Prima di raccogliere dati sulle prestazioni per un'area specifica, è necessario aver eseguito le operazioni seguenti:

1. Dimostrare che è necessario analizzare l'area in questione.

2. Esaminare altre aree note senza trovare elementi che possono spiegare il problema di prestazioni rilevato.

Vedere il blog [Understand the problem before you try to find a solution](https://devblogs.microsoft.com/dotnet/understand-the-problem-before-you-try-to-find-a-solution/) (Comprendere il problema prima di cercare una soluzione) per altre informazioni sui concetti fondamentali della memoria e della CPU.

Per raccogliere dati sulle prestazioni dell'heap oggetti grandi è possibile usare gli strumenti seguenti:

- [Contatori delle prestazioni della memoria CLR .NET](#net-clr-memory-performance-counters)

- [eventi ETW](#etw-events)

- [Un debugger](#a-debugger)

### <a name="net-clr-memory-performance-counters"></a>Contatori delle prestazioni della memoria CLR .NET

Questi contatori delle prestazioni sono in genere un buon primo passo nell'analisi dei problemi di prestazioni (anche se Microsoft consiglia l'uso degli [eventi ETW](#etw-events)). Configurare Performance Monitor aggiungendo i contatori desiderati, come illustrato nella figura 4. I contatori importanti per l'heap oggetti grandi sono:

- **Collezioni Gen 2**

   Visualizza il numero di operazioni GC di generazione 2 eseguite dall'avvio del processo. Il contatore viene incrementato alla fine di una raccolta di generazione 2 (denominata anche Garbage Collection completa). Questo contatore visualizza 'ultimo valore osservato.

- **Dimensione heap Large Object**

   Visualizza la dimensione corrente in byte dell'heap oggetti grandi, incluso lo spazio disponibile. Questo contatore viene aggiornato alla fine di una Garbage Collection, non a ogni allocazione.

Un metodo molto comune per il controllo dei contatori è Performance Monitor (perfmon.exe). Usare "Aggiungi contatori" per aggiungere il contatore corrispondente ai processi che interessano. I dati del contatore delle prestazioni possono essere salvati in un file di registro, come indicato nella figura 4:

![Screenshot che mostra l'aggiunta di contatori delle prestazioni.](media/large-object-heap/add-performance-counter.png)
Figura 4: LOH dopo un'operazione GC di generazione 2

È anche possibile eseguire query sui contatori delle prestazioni a livello di codice. Molti utenti raccolgono i dati con questa modalità come parte del processo di test di routine. Se vengono identificati contatori con valori anomali, è possibile usare altri mezzi per ottenere dati più dettagliati ai fini dell'analisi.

> [!NOTE]
> È consigliabile usare gli eventi ETW anziché i contatori delle prestazioni, poiché ETW offre informazioni molto più complete.

### <a name="etw-events"></a>eventi ETW

Il Garbage Collector offre vari eventi ETW che favoriscono la comprensione delle operazioni dell'heap e del loro scopo. I post di blog seguenti illustrano come raccogliere e interpretare gli eventi GC con ETW:

- [Eventi ETW GC - 1](https://devblogs.microsoft.com/dotnet/gc-etw-events-1/)

- [Eventi ETW - GC - 2](https://devblogs.microsoft.com/dotnet/gc-etw-events-2/)

- [Eventi ETW - GC - 3](https://devblogs.microsoft.com/dotnet/gc-etw-events-3/)

- [Eventi ETW - GC - 4](https://devblogs.microsoft.com/dotnet/gc-etw-events-4/)

Per identificare un numero eccessivo di operazioni GC di generazione 2 causate da allocazioni di heap oggetti grandi temporanee, esaminare la colonna Motivo trigger per le operazioni GC. Per un test semplice che consente di allocare solo oggetti di grandi dimensioni temporanei, è possibile raccogliere informazioni sugli eventi ETW con la riga di comando [PerfView](https://www.microsoft.com/download/details.aspx?id=28567) seguente:

```console
perfview /GCCollectOnly /AcceptEULA /nogui collect
```

Il risultato è simile al seguente:

![Screenshot che mostra gli eventi ETW in PerfView.](media/large-object-heap/event-tracing-windows-perfview.png)
Figura 5: Eventi ETW visualizzati mediante PerfView

Si osservi che tutte le operazioni GCs sono di generazione 2 e tutte sono attivate da AllocLarge. Ciò significa che l'operazione GC è stata attivata da un oggetto grande. Il fatto che si tratti di allocazioni temporanee è indicato dal valore 1% nella colonna **LOH Survival Rate %** (% heap oggetti grandi attivi).

È possibile raccogliere altri eventi ETW che indicano l'origine di allocazione di questi oggetti grandi. La riga di comando seguente:

```console
perfview /GCOnly /AcceptEULA /nogui collect
```

registra un evento AllocationTick ogni 100 KB circa di allocazione. In altre parole viene generato un evento ogni volta che viene allocato un oggetto grande. È quindi possibile esaminare una delle visualizzazioni di allocazione heap GC che includono gli stack di chiamate che hanno allocato oggetti grandi:

![Screenshot che mostra una visualizzazione heap Garbage Collector.](media/large-object-heap/garbage-collector-heap.png)
Figura 6: Visualizzazione di allocazione heap GC

Questo test molto semplice esegue solo l'allocazione di oggetti grandi dal relativo metodo `Main`.

### <a name="a-debugger"></a>Un debugger

Se è presente solo di un dump di memoria ed è necessario esaminare quali oggetti sono effettivamente inclusi nell'heap oggetti grandi, è possibile usare l'[estensione del debugger SoS](../../../docs/framework/tools/sos-dll-sos-debugging-extension.md) disponibile in .NET.

> [!NOTE]
> I comandi di debug indicati in questa sezione sono applicabili ai [debugger di Windows](https://www.microsoft.com/whdc/devtools/debugging/default.mspx).

Il codice seguente visualizza un output di esempio dell'analisi dell'heap oggetti grandi:

```console
0:003> .loadby sos mscorwks
0:003> !eeheap -gc
Number of GC Heaps: 1
generation 0 starts at 0x013e35ec
sdgeneration 1 starts at 0x013e1b6c
generation 2 starts at 0x013e1000
ephemeral segment allocation context: none
segment   begin allocated     size
0018f2d0 790d5588 790f4b38 0x0001f5b0(128432)
013e0000 013e1000 013e35f8 0x000025f8(9720)
Large object heap starts at 0x023e1000
segment   begin allocated     size
023e0000 023e1000 033db630 0x00ffa630(16754224)
033e0000 033e1000 043cdf98 0x00fecf98(16699288)
043e0000 043e1000 05368b58 0x00f87b58(16284504)
Total Size 0x2f90cc8(49876168)
------------------------------
GC Heap Size 0x2f90cc8(49876168)
0:003> !dumpheap -stat 023e1000 033db630
total 133 objects
Statistics:
MT   Count   TotalSize Class Name
001521d0       66     2081792     Free
7912273c       63     6663696 System.Byte[]
7912254c       4     8008736 System.Object[]
Total 133 objects
```

Le dimensioni dell'heap oggetti grandi sono (16.754.224 + 16.699.288 + 16.284.504) = 49.738.016 byte. Tra gli indirizzi 023e1000 e 033db630, 8.008.736 byte sono occupati da una matrice di oggetti <xref:System.Object?displayProperty=nameWithType>, 6.663.696 byte sono occupati da una matrice di oggetti <xref:System.Byte?displayProperty=nameWithType> e 2.081.792 byte sono occupati da spazio libero.

A volte il debugger indica che le dimensioni totali dell'heap oggetti grandi sono inferiori a 85.000 byte. Il motivo è che il runtime stesso usa l'heap oggetti grandi per allocare alcuni oggetti di dimensioni inferiori a quelle di un oggetto grande.

Poiché l'heap degli oggetti grandi non è compattato, si può pensare che sia all'origine della frammentazione. Frammentazione significa:

- Frammentazione dell'heap gestito, indicata dalla quantità di spazio disponibile tra gli oggetti gestiti. In SoS il comando `!dumpheap –type Free` visualizza la quantità di spazio disponibile tra gli oggetti gestiti.

- Frammentazione dello spazio indirizzi della memoria virtuale (VM), la memoria contrassegnata come `MEM_FREE`. È possibile ottenerla con vari comandi del debugger in windbg.

   L'esempio seguente visualizza la frammentazione nello spazio della memoria virtuale:

   ```console
   0:000> !address
   00000000 : 00000000 - 00010000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   00010000 : 00010000 - 00002000
   Type     00020000 MEM_PRIVATE
   Protect 00000004 PAGE_READWRITE
   State   00001000 MEM_COMMIT
   Usage   RegionUsageEnvironmentBlock
   00012000 : 00012000 - 0000e000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   … [omitted]
   -------------------- Usage SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Pct(Busy)   Usage
   701000 (   7172) : 00.34%   20.69%   : RegionUsageIsVAD
   7de15000 ( 2062420) : 98.35%   00.00%   : RegionUsageFree
   1452000 (   20808) : 00.99%   60.02%   : RegionUsageImage
   300000 (   3072) : 00.15%   08.86%   : RegionUsageStack
   3000 (     12) : 00.00%   00.03%   : RegionUsageTeb
   381000 (   3588) : 00.17%   10.35%   : RegionUsageHeap
   0 (       0) : 00.00%   00.00%   : RegionUsagePageHeap
   1000 (       4) : 00.00%   00.01%   : RegionUsagePeb
   1000 (       4) : 00.00%   00.01%   : RegionUsageProcessParametrs
   2000 (       8) : 00.00%   00.02%   : RegionUsageEnvironmentBlock
   Tot: 7fff0000 (2097088 KB) Busy: 021db000 (34668 KB)

   -------------------- Type SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   7de15000 ( 2062420) : 98.35%   : <free>
   1452000 (   20808) : 00.99%   : MEM_IMAGE
   69f000 (   6780) : 00.32%   : MEM_MAPPED
   6ea000 (   7080) : 00.34%   : MEM_PRIVATE

   -------------------- State SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   1a58000 (   26976) : 01.29%   : MEM_COMMIT
   7de15000 ( 2062420) : 98.35%   : MEM_FREE
   783000 (   7692) : 00.37%   : MEM_RESERVE

   Largest free region: Base 01432000 - Size 707ee000 (1843128 KB)
   ```

È più comune osservare la frammentazione della memoria virtuale causata da oggetti grandi temporanei, che richiedono a Garbage Collector di acquisire frequentemente nuovi segmenti di heap gestiti dal sistema operativo e di restituire quelli vuoti e liberati.

Per verificare se l'heap oggetti grandi è la causa della frammentazione della memoria virtuale, è possibile impostare un punto di interruzione su [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) e [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) per vedere quale entità chiama questi processi. Ad esempio, per vedere quale entità ha provato ad allocare blocchi di memoria virtuale del sistema operativo di dimensioni superiori a 8 MB, è possibile impostare un punto di interruzione simile al seguente:

```console
bp kernel32!virtualalloc "j (dwo(@esp+8)>800000) 'kb';'g'"
```

Questo comando viene interrotto nel debugger e mostra lo stack di chiamate solo se [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) viene chiamato con una dimensione di allocazione maggiore di 8 MB (0x800000).

In CLR 2.0 la nuova funzionalità *VM Hoarding* (Accumulo in memoria virtuale) può essere utile in situazioni con acquisizione e rilascio frequenti di segmenti, ad esempio nell'heap degli oggetti piccoli e nell'heap degli oggetti grandi. Per impostare VM Hoarding si specifica un flag di avvio chiamato `STARTUP_HOARD_GC_VM` tramite l'API di hosting. Invece di rilasciare i segmenti vuoti per restituirli al sistema operativo, CLR libera la memoria in questi segmenti e li inserisce in un elenco di standby. (Si noti che CLR non esegue questa operazione per i segmenti che sono troppo grandi.) CLR utilizza in seguito tali segmenti per soddisfare le nuove richieste di segmento. Quando l'app torna a richiedere un nuovo segmento, CLR usa un segmento di questo elenco di standby, se è disponibile un segmento abbastanza grande.

L'accumulo di macchine virtuali è utile anche per le applicazioni che desiderano mantenere i segmenti già acquisiti, ad esempio alcune app server che sono le app dominanti in esecuzione nel sistema, per evitare eccezioni di memoria insufficiente.

Quando si usa questa funzionalità è consigliabile sottoporre a test accurati l'applicazione, per garantire che l'uso della memoria sia sufficientemente stabile.
