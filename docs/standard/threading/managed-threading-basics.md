---
title: Nozioni di base sul threading gestito
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62c207f6074e33813887c6903f5285ee72d14e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading-basics"></a>Nozioni di base sul threading gestito
I primi cinque argomenti di questa sezione sono progettati per determinare quando usare threading gestito e vengono descritte alcune funzionalità di base. Per informazioni sulle classi che forniscono funzionalità aggiuntive, vedere [Threading oggetti e funzionalità](../../../docs/standard/threading/threading-objects-and-features.md) e [panoramica delle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Il resto degli argomenti in questa sezione illustrano avanzata, tra cui l'interazione del threading gestito con il sistema operativo Windows.  
  
> [!NOTE]
>  Nel [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la libreria Task Parallel Library e PLINQ forniscono le API per parallelismo delle attività e i dati nei programmi multithread. Per altre informazioni, vedere [Programmazione parallela](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Thread e Threading](../../../docs/standard/threading/threads-and-threading.md)  
 Illustra i vantaggi e svantaggi di più thread e vengono descritti gli scenari in cui è possibile creare thread o usano i pool thread.  
  
 [Eccezioni in thread gestiti](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 Viene descritto il comportamento di eccezioni non gestite nei thread per versioni diverse di .NET Framework, in particolare nelle situazioni in cui risultano chiusura dell'applicazione.  
  
 [Sincronizzazione dei dati per il multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 Descrive le strategie per la sincronizzazione dei dati nelle classi che verranno utilizzate con più thread.  
  
 [Stati dei thread gestiti](../../../docs/standard/threading/managed-thread-states.md)  
 Vengono descritti gli stati di base di thread e viene illustrato come rilevare se un thread è in esecuzione.  
  
 [Thread in primo piano e in background](../../../docs/standard/threading/foreground-and-background-threads.md)  
 Vengono illustrate le differenze tra i thread in primo piano e sfondo.  
  
 [Threading gestito e non gestito in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 Viene illustrata la relazione tra threading gestito e non gestito, elenca equivalenti gestiti threading API di Windows e viene descritta l'interazione di thread gestiti e apartment COM.  
  
 [Thread.Suspend, operazioni di Garbage Collection e punti sicuri](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 Descrive i thread sospensione e garbage collection.  
  
 [Archiviazione locale del thread: slot di dati e campi statici relativi ai thread](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Vengono descritti i meccanismi di archiviazione relativi ai thread.  
  
 [Annullamento in thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 Descrive le operazioni sincrone asincrone o con esecuzione prolungata può essere annullata utilizzando un token di annullamento.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Threading.Thread>  
 Rende disponibile la documentazione di riferimento per la classe **Thread**, che rappresenta un thread gestito, indipendentemente dal fatto che derivi da codice non gestito o sia stato creato in un'applicazione gestita.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Fornisce un metodo sicuro per implementare il multithreading insieme a oggetti dell'interfaccia utente.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Cenni preliminari sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Descrive le classi gestite utilizzate per sincronizzare le attività di più thread.  
  
 [Suggerimenti per l'utilizzo del threading gestito](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Vengono descritti problemi comuni con multithreading e le strategie per evitarli.  
  
 [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)  
 Descrive la Task Parallel Library e PLINQ, che semplificano notevolmente la creazione di applicazioni .NET Framework asincrone e multithreading.
