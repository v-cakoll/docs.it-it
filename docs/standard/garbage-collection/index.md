---
title: Garbage Collection di .NET
ms.date: 04/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: c087deb033a373dd8b3980feb7ec6901c7909569
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102242"
---
# <a name="garbage-collection"></a>Garbage Collection

Il Garbage Collector di .NET gestisce l'allocazione e il rilascio di memoria per l'applicazione. Ogni volta che si crea un nuovo oggetto, Common Language Runtime alloca memoria per l'oggetto dall'heap gestito. Lo spazio per i nuovi oggetti verrà allocato in questo modo dal runtime fino all'esaurimento dello spazio degli indirizzi nell'heap gestito. La memoria, tuttavia, non è infinita. Alla fine il Garbage Collector deve eseguire una raccolta per liberare memoria. Il modulo di ottimizzazione del Garbage Collector consente di determinare il momento migliore per l'esecuzione di una raccolta sulla base delle allocazioni in corso. Durante l'esecuzione di una raccolta, il Garbage Collector verifica la presenza di oggetti non più usati dall'applicazione nell'heap gestito ed esegue le operazioni necessarie per reclamare la relativa memoria.  
  
## <a name="in-this-section"></a>Contenuto della sezione
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Nozioni fondamentali sull'operazione di Garbage Collection](../../../docs/standard/garbage-collection/fundamentals.md)|Descrive il funzionamento di Garbage Collection, la modalità di allocazione degli oggetti nell'heap gestito e altri concetti di base.|  
|[Operazione di Garbage Collection per workstation e server](workstation-server-gc.md)|Vengono descritte le differenze tra la procedura di Garbage Collection per le workstation per le app client e la Garbage Collection del server per le app server.|
|[Garbage Collection in background](background-gc.md)|Descrive la garbage collection in background, ovvero la raccolta di oggetti di generazione 0 e 1 mentre è in corso la raccolta di generazione 2.Describes background garbage collection, which is the collection of generation 0 and 1 objects while generation 2 collection is in progress.|
|[L'heap oggetti grandi](large-object-heap.md)|Descrive l'heap oggetti grandi (LOH) e il modo in cui gli oggetti di grandi dimensioni vengono sottoposti a garbage collection.|
|[Garbage Collection e prestazioni](../../../docs/standard/garbage-collection/performance.md)|Descrive i controlli delle prestazioni è possibile usare per diagnosticare i problemi di Garbage Collection e di prestazioni.|  
|[Raccolte indotte](../../../docs/standard/garbage-collection/induced.md)|Descrive come eseguire un'operazione di Garbage Collection.|  
|[Modalità di latenza](../../../docs/standard/garbage-collection/latency.md)|Descrive i modi per determinare l'ingerenza di Garbage Collection.|  
|[Ottimizzazione per l'hosting Web condiviso](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|Descrive come ottimizzare l'operazione di Garbage Collection nei server condivisi da più siti Web di piccole dimensioni.|  
|[Notifiche di Garbage Collection](../../../docs/standard/garbage-collection/notifications.md)|Descrive come determinare quando è imminente una Garbage Collection completa e quando è stata completata.|  
|[Monitoraggio delle risorse del dominio applicazione](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|Descrive come monitorare l'utilizzo della CPU e della memoria da un dominio dell'applicazione.|  
|[Riferimenti deboli](../../../docs/standard/garbage-collection/weak-references.md)|Descrive i riferimenti che consentono al Garbage Collector di raccogliere un oggetto, pur senza impedire all'applicazione di accedervi.|  
  
## <a name="reference"></a>Informazioni di riferimento

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a>Vedere anche

- [Pulizia delle risorse non gestite](../../../docs/standard/garbage-collection/unmanaged.md)
