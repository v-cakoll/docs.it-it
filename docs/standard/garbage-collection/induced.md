---
title: Raccolte indotte
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: garbage collection, forced
ms.assetid: 019008fe-4708-4e65-bebf-04fd9941e149
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92918e347b10dfcf3a0d6e2c08cec8c7a6963f5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="induced-collections"></a>Raccolte indotte
Nella maggior parte dei casi, tramite il Garbage Collector è possibile determinare il momento migliore per eseguire una raccolta ed è consigliabile consentire l'esecuzione in modo indipendente. In rari casi una raccolta forzata può migliorare le prestazioni dell'applicazione. In questi casi, si può provocare un'operazione di garbage collection con il <xref:System.GC.Collect%2A?displayProperty=nameWithType> metodo per forzare un'operazione di garbage collection.  
  
 Utilizzare il <xref:System.GC.Collect%2A?displayProperty=nameWithType> metodo quando si verifica una riduzione significativa della quantità di memoria utilizzata in un punto specifico nel codice dell'applicazione. Ad esempio, se l'applicazione utilizza una finestra di dialogo complesso che dispone di diversi controlli, la chiamata <xref:System.GC.Collect%2A> quando viene chiuso la finestra di dialogo potrebbe migliorare le prestazioni recuperando immediatamente la memoria utilizzata dalla finestra di dialogo. Assicurarsi che l'applicazione non induca troppo spesso l'operazione di Garbage Collection, in quanto può causare una riduzione delle prestazioni se il Garbage Collector tenta di recuperare oggetti in momenti non ottimali. È possibile fornire un <xref:System.GCCollectionMode.Optimized?displayProperty=nameWithType> valore di enumerazione per il <xref:System.GC.Collect%2A> metodo per raccogliere solo quando l'insieme sarebbe produttivo, come descritto nella sezione successiva.  
  
## <a name="gc-collection-mode"></a>Modalità di raccolta Garbage Collection  
 È possibile utilizzare uno del <xref:System.GC.Collect%2A?displayProperty=nameWithType> overload del metodo che include un <xref:System.GCCollectionMode> valore per specificare il comportamento per una raccolta forzato come indicato di seguito.  
  
|Valore di `GCCollectionMode`|Descrizione|  
|------------------------------|-----------------|  
|<xref:System.GCCollectionMode.Default>|Utilizza l'impostazione di garbage collection per la versione di .NET in esecuzione.|  
|<xref:System.GCCollectionMode.Forced>|Forza l'esecuzione immediata dell'operazione di Garbage Collection. Questo è equivalente alla chiamata di <xref:System.GC.Collect?displayProperty=nameWithType> rapporto di overload. Restituisce una raccolta di blocco completa di tutte le generazioni.<br /><br /> È anche possibile compattare i heap degli oggetti grandi impostando la <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> proprietà <xref:System.Runtime.GCLargeObjectHeapCompactionMode.CompactOnce?displayProperty=nameWithType> prima di forzare un immediato completa di garbage collection bloccante.|  
|<xref:System.GCCollectionMode.Optimized>|Consente al Garbage Collector di determinare se il momento corrente è ottimale per recuperare oggetti.<br /><br /> Il Garbage Collector può determinare che una raccolta non è sufficientemente produttiva per giustificarne l'esecuzione, nel qual caso esce dalla funzione senza recuperare oggetti.|  
  
## <a name="background-or-blocking-collections"></a>Raccolte in background o di blocco  
 È possibile chiamare il <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29?displayProperty=nameWithType> overload del metodo per specificare se o non sia bloccate da una raccolta indotta. Il tipo della raccolta eseguita dipende da una combinazione del metodo `mode` e `blocking` parametri. `mode`è un membro del <xref:System.GCCollectionMode> , enumerazione e `blocking` è un <xref:System.Boolean> valore. Nella tabella seguente viene riepilogata l'interazione del `mode` e `blocking` argomenti.  
  
|`mode`|`blocking` = `true`|`blocking` = `false`|  
|------------|--------------------------|---------------------------|  
|<xref:System.GCCollectionMode.Forced> o <xref:System.GCCollectionMode.Default>|Viene eseguita una raccolta di blocco il prima possibile. Se una raccolta in background è in corso e la generazione è 0 o 1, il <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> metodo attiva immediatamente una raccolta di blocco e al termine della raccolta. Se una raccolta in background è in corso e `generation` parametro è 2, il metodo attende fino a quando la raccolta in background al termine, attiva una raccolta di generazione 2 blocco e quindi restituisce.|Viene eseguita una raccolta il prima possibile. Il <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> metodo richiede una raccolta in background, ma questo non è garantito, a seconda delle circostanze, può ancora essere eseguita una raccolta di blocco. Se è già in corso una raccolta in background, il metodo viene restituito immediatamente.|  
|<xref:System.GCCollectionMode.Optimized>|Una raccolta di blocco può essere eseguita, a seconda dello stato del garbage collector e `generation` parametro. Il Garbage Collector tenta di garantire prestazioni ottimali.|È possibile eseguire una raccolta, a seconda dello stato del Garbage Collector. Il <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> metodo richiede una raccolta in background, ma questo non è garantito, a seconda delle circostanze, può ancora essere eseguita una raccolta di blocco. Il Garbage Collector tenta di garantire prestazioni ottimali. Se è già in corso una raccolta in background, il metodo viene restituito immediatamente.|  
  
## <a name="see-also"></a>Vedere anche  
 [Modalità di latenza](../../../docs/standard/garbage-collection/latency.md)  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
