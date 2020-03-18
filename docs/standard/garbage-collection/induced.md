---
title: Raccolte indotte
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, forced
ms.assetid: 019008fe-4708-4e65-bebf-04fd9941e149
ms.openlocfilehash: 604b49ef577a46204b523ebf5a8575a30b81635e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73120925"
---
# <a name="induced-collections"></a>Raccolte indotte
Nella maggior parte dei casi, tramite il Garbage Collector è possibile determinare il momento migliore per eseguire una raccolta ed è consigliabile consentire l'esecuzione in modo indipendente. In rari casi una raccolta forzata può migliorare le prestazioni dell'applicazione. In questi casi, è possibile indurre un'operazione di Garbage Collection usando il metodo <xref:System.GC.Collect%2A?displayProperty=nameWithType> per forzarla.  
  
 Usare il metodo <xref:System.GC.Collect%2A?displayProperty=nameWithType> quando si verifica una riduzione significativa della quantità di memoria usata in un momento specifico nel codice dell'applicazione. Se, ad esempio, l'applicazione usa una finestra di dialogo complessa con numerosi controlli, chiamando il metodo <xref:System.GC.Collect%2A> quando la finestra di dialogo è chiusa è possibile migliorare le prestazioni, recuperando immediatamente la memoria usata dalla finestra di dialogo. Assicurarsi che l'applicazione non induca troppo spesso l'operazione di Garbage Collection, in quanto può causare una riduzione delle prestazioni se il Garbage Collector tenta di recuperare oggetti in momenti non ottimali. È possibile fornire un valore di enumerazione <xref:System.GCCollectionMode.Optimized?displayProperty=nameWithType> al metodo <xref:System.GC.Collect%2A> in modo che la raccolta venga eseguita solo quando l'operazione è produttiva, come descritto nella sezione seguente.  
  
## <a name="gc-collection-mode"></a>Modalità di raccolta Garbage Collection  
 È possibile usare uno degli overload del metodo <xref:System.GC.Collect%2A?displayProperty=nameWithType> che include un valore <xref:System.GCCollectionMode> per specificare il comportamento di una raccolta forzata, come indicato di seguito.  
  
|Valore della proprietà `GCCollectionMode`|Descrizione|  
|------------------------------|-----------------|  
|<xref:System.GCCollectionMode.Default>|Usa l'impostazione di Garbage Collection predefinita per la versione di .NET in esecuzione.|  
|<xref:System.GCCollectionMode.Forced>|Forza l'esecuzione immediata dell'operazione di Garbage Collection. Equivale alla chiamata dell'overload di <xref:System.GC.Collect?displayProperty=nameWithType>. Restituisce una raccolta di blocco completa di tutte le generazioni.<br /><br /> È anche possibile compattare l'heap di oggetti di grandi dimensioni impostando la proprietà <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> su <xref:System.Runtime.GCLargeObjectHeapCompactionMode.CompactOnce?displayProperty=nameWithType> prima di forzare una procedura completa immediata di Garbage Collection di blocco.|  
|<xref:System.GCCollectionMode.Optimized>|Consente al Garbage Collector di determinare se il momento corrente è ottimale per recuperare oggetti.<br /><br /> Il Garbage Collector può determinare che una raccolta non è sufficientemente produttiva per giustificarne l'esecuzione, nel qual caso esce dalla funzione senza recuperare oggetti.|  
  
## <a name="background-or-blocking-collections"></a>Raccolte in background o di blocco  
 È possibile chiamare l'overload del metodo <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29?displayProperty=nameWithType> per specificare se una raccolta indotta è di blocco o meno. Il tipo di raccolta eseguita dipende da una combinazione dei parametri `mode` e `blocking` del metodo. `mode` è un membro dell'enumerazione <xref:System.GCCollectionMode> e `blocking` è un valore <xref:System.Boolean>. La tabella seguente riepiloga l'interazione degli argomenti `mode` e `blocking`.  
  
|`mode`|`blocking` = `true`|`blocking` = `false`|  
|------------|--------------------------|---------------------------|  
|<xref:System.GCCollectionMode.Forced> o <xref:System.GCCollectionMode.Default>|Viene eseguita una raccolta di blocco il prima possibile. Se è in corso una raccolta in background e il valore di generation è 0 o 1, il metodo <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> attiva immediatamente una raccolta di blocco e restituisce un risultato al termine della raccolta. Se è in corso una raccolta in background e il parametro `generation` è 2, il metodo attende fino a quando la raccolta in background non viene completata, attiva una raccolta di blocco di generazione 2 e quindi restituisce il risultato.|Viene eseguita una raccolta il prima possibile. Il metodo <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> richiede una raccolta in background, la cui esecuzione non è comunque garantita. A seconda della situazione, può venire comunque eseguita una raccolta di blocco. Se è già in corso una raccolta in background, il metodo viene restituito immediatamente.|  
|<xref:System.GCCollectionMode.Optimized>|Può venire eseguita una raccolta di blocco, a seconda dello stato del Garbage Collector e del parametro `generation`. Il Garbage Collector tenta di garantire prestazioni ottimali.|È possibile eseguire una raccolta, a seconda dello stato del Garbage Collector. Il metodo <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> richiede una raccolta in background, la cui esecuzione non è comunque garantita. A seconda della situazione, può venire comunque eseguita una raccolta di blocco. Il Garbage Collector tenta di garantire prestazioni ottimali. Se è già in corso una raccolta in background, il metodo viene restituito immediatamente.|  
  
## <a name="see-also"></a>Vedere anche

- [Modalità di latenza](../../../docs/standard/garbage-collection/latency.md)
- [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
