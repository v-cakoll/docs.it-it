---
title: Raccolte thread-safe
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- thread-safe collections, overview
ms.assetid: 2e7ca21f-786c-4367-96be-0cf3f3dcc6bd
ms.openlocfilehash: 30660c2fb89fd3738abb05122a5daf175677265c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711246"
---
# <a name="thread-safe-collections"></a>Raccolte thread-safe
.NET Framework 4 introduce lo spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType> che include diverse classi di raccolta thread-safe e scalabili. Più thread possono aggiungere o rimuovere elementi da queste raccolte in modo sicuro ed efficiente, senza richiedere una sincronizzazione aggiuntiva nel codice utente. Quando si scrive nuovo codice, usare le classi di raccolta simultanee ogni volta che più thread scriveranno nella raccolta contemporaneamente. Se si prevede di leggere solo da una raccolta condivisa, è possibile usare le classi dello spazio dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType>. È consigliabile evitare di usare le classi di raccolta 1.0 a meno che non sia necessario definire come destinazione il runtime di .NET Framework versione 1.1 o precedente.  
  
## <a name="thread-synchronization-in-the-net-framework-10-and-20-collections"></a>Sincronizzazione dei thread nelle raccolte di .NET Framework 1.0 e 2.0  
 Le raccolte introdotte in .NET Framework 1.0 sono reperibili nello spazio dei nomi <xref:System.Collections?displayProperty=nameWithType>. Queste raccolte, incluse le raccolte <xref:System.Collections.ArrayList> e <xref:System.Collections.Hashtable> usate normalmente, supportano la thread safety con la proprietà `Synchronized`, che restituisce un wrapper thread-safe per la raccolta. Il wrapper funziona bloccando l'intera raccolta in ogni operazione di aggiunta o rimozione. Pertanto, ogni thread che tenta di accedere alla raccolta deve attendere il proprio turno per acquisire l'unico blocco. Questa caratteristica non è scalabile e può causare un peggioramento delle prestazioni per le raccolte di grandi dimensioni. Inoltre, la progettazione non è completamente protetta da race condition. Per altre informazioni, vedere la pagina relativa alla [sincronizzazione nelle raccolte generiche](https://blogs.msdn.microsoft.com/bclteam/2005/03/15/synchronization-in-generic-collections-brian-grunkemeyer/).  
  
 Le classi di raccolta introdotte in .NET Framework 2.0 sono reperibili nello spazio dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType>. Sono incluse <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602> e così via. che forniscono maggiore indipendenza dai tipi e migliori prestazioni rispetto alle classi di .NET Framework 1.0. Tuttavia, le classi di raccolta di .NET Framework 2.0 non forniscono la sincronizzazione dei thread. Quando gli elementi vengono aggiunti o rimossi contemporaneamente su più thread, la sincronizzazione deve essere gestita dal codice utente.  
  
 È quindi consigliabile usare le classi di raccolta simultanea disponibili in .NET Framework 4 perché offrono non solo l'indipendenza dai tipi delle classi di raccolta .NET Framework 2.0, ma anche una thread safety più efficiente e completa rispetto alle raccolte di .NET Framework 1.0.  
  
## <a name="fine-grained-locking-and-lock-free-mechanisms"></a>Blocco con granularità fine e meccanismi senza blocco  
 Alcuni tipi di raccolta simultanea usano meccanismi di sincronizzazione leggeri, ad esempio <xref:System.Threading.SpinLock>, <xref:System.Threading.SpinWait>, <xref:System.Threading.SemaphoreSlim> e <xref:System.Threading.CountdownEvent>, che sono una novità di .NET Framework 4. Questi tipi di sincronizzazione usano in genere la rotazione con *stato occupato* per breve periodi di tempo prima di impostare il thread in uno stato di attesa effettivo. Quando si prevedono tempi di attesa molto brevi, la rotazione è molto meno dispendiosa a livello di elaborazione rispetto all'attesa, che implica una transizione del kernel complessa. Per le classi di raccolta che usano la rotazione, questo livello di efficienza significa che più thread possono aggiungere e rimuovere elementi con una frequenza molto elevata. Per altre informazioni sul confronto tra spin e blocco, vedere [SpinLock](../../../../docs/standard/threading/spinlock.md) e [SpinWait](../../../../docs/standard/threading/spinwait.md).  
  
 Le classi <xref:System.Collections.Concurrent.ConcurrentQueue%601> e <xref:System.Collections.Concurrent.ConcurrentStack%601> non usano alcun blocco. Al contrario, si basano sulle operazioni <xref:System.Threading.Interlocked> per ottenere la thread safety.  
  
> [!NOTE]
> Poiché supportano <xref:System.Collections.ICollection>, le classi di raccolta simultanee offrono implementazioni per le proprietà <xref:System.Collections.ICollection.IsSynchronized%2A> e <xref:System.Collections.ICollection.SyncRoot%2A>, anche se queste sono irrilevanti. `IsSynchronized` restituisce sempre `false` e `SyncRoot` è sempre `null` (`Nothing` in Visual Basic).  
  
 Nella tabella seguente sono elencati i tipi di raccolta dello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType>.  
  
|Tipo di|Descrizione|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601>|Offre la funzionalità di delimitazione e blocco per qualsiasi tipo che implementa <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>. Per altre informazioni, vedere [Panoramica di BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602>|Implementazione thread-safe di un dizionario di coppie chiave-valore.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601>|Implementazione thread-safe di una coda FIFO (First-In, First-Out).|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601>|Implementazione thread-safe di una coda LIFO (Last-In, First-Out).|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601>|Implementazione thread-safe di una raccolta non ordinata di elementi.|  
|<xref:System.Collections.Concurrent.IProducerConsumerCollection%601>|Interfaccia che un tipo deve implementare per essere usato in un oggetto `BlockingCollection`.|  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Panoramica di BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)|Descrive la funzionalità fornita dal tipo <xref:System.Collections.Concurrent.BlockingCollection%601>.|  
|[Procedura: aggiungere e rimuovere elementi da un oggetto ConcurrentDictionary](../../../../docs/standard/collections/thread-safe/how-to-add-and-remove-items.md)|Descrive come aggiungere e rimuovere elementi da un oggetto <xref:System.Collections.Concurrent.ConcurrentDictionary%602>|  
|[Procedura: Aggiungere e rimuovere singoli elementi di un oggetto BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)|Descrive come aggiungere e recuperare elementi da una raccolta di blocco senza usare l'enumeratore di sola lettura.|  
|[Procedura: Aggiungere funzionalità di delimitazione e blocco a una raccolta](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md)|Descrive come usare una classe di raccolta come meccanismo di archiviazione sottostante per una raccolta <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>.|  
|[Procedura: utilizzare ForEach per rimuovere elementi in un oggetto BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)|Descrive come usare `foreach` (`For Each` in Visual Basic) per rimuovere tutti gli elementi in una raccolta di blocco.|  
|[Procedura: utilizzare matrici di raccolte di blocco in una pipeline](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md)|Descrive come usare più raccolte di blocco contemporaneamente per implementare una pipeline.|  
|[Procedura: Creare un pool di oggetti con un oggetto ConcurrentBag](../../../../docs/standard/collections/thread-safe/how-to-create-an-object-pool.md)|Illustra come usare un contenitore simultaneo per migliorare le prestazioni negli scenari in cui è possibile riutilizzare gli oggetti anziché crearne continuamente di nuovi.|  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>
