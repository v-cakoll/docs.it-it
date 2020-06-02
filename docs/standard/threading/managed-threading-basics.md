---
title: Nozioni di base sul threading gestito
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: 4d2a96619fd1c48c79b5590efdb52c307d29710c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291006"
---
# <a name="managed-threading-basics"></a>Nozioni di base sul threading gestito

I primi cinque argomenti di questa sezione contengono informazioni utili per determinare quando usare il threading gestito e descrivono alcune funzionalità di base. Per informazioni sulle classi che forniscono funzionalità aggiuntive, vedere [Oggetti e funzionalità del threading](threading-objects-and-features.md) e [Cenni preliminari sulle primitive di sincronizzazione](overview-of-synchronization-primitives.md).  
  
 Gli altri argomenti di questa sezione illustrano funzionalità avanzate, tra cui l'interazione del threading gestito con il sistema operativo Windows.  
  
> [!NOTE]
> In .NET Framework 4, Task Parallel Library e PLINQ forniscono le API per il parallelismo di attività e dati nei programmi multithread. Per ulteriori informazioni, vedere [programmazione parallela](../parallel-programming/index.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione

 [Thread e Threading](threads-and-threading.md)  
 Illustra i vantaggi e gli svantaggi di più thread e descrive gli scenari in cui è possibile creare thread o usare thread di pool di thread.  
  
 [Eccezioni in thread gestiti](exceptions-in-managed-threads.md)  
 Illustra il comportamento delle eccezioni non gestite nei thread per versioni diverse di .NET Framework, in particolare le situazioni in cui causano la terminazione dell'applicazione.  
  
 [Sincronizzazione dei dati per il multithreading](synchronizing-data-for-multithreading.md)  
 Illustra le strategie per la sincronizzazione dei dati nelle classi, che verranno usati con più thread.  
  
 [Thread in primo piano e in background](foreground-and-background-threads.md)  
 Illustra le differenze tra i thread in primo piano e in background.  
  
 [Threading gestito e non gestito in Windows](managed-and-unmanaged-threading-in-windows.md)  
 Illustra la relazione tra il threading gestito e non gestito, elenca gli equivalenti gestiti delle API di threading Windows e illustra l'interazione degli apartment COM e dei thread gestiti.  
  
 [Archiviazione locale del thread: slot di dati e campi statici relativi ai thread](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Illustra i meccanismi di archiviazione relativi ai thread.  
  
## <a name="reference"></a>Informazioni di riferimento

 <xref:System.Threading.Thread>  
 Rende disponibile la documentazione di riferimento per la classe **Thread**, che rappresenta un thread gestito, indipendentemente dal fatto che derivi da codice non gestito o sia stato creato in un'applicazione gestita.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Consente di implementare in modo sicuro il multithreading insieme agli oggetti dell'interfaccia utente.  
  
## <a name="related-sections"></a>Sezioni correlate

 [Panoramica delle primitive di sincronizzazione](overview-of-synchronization-primitives.md)  
 Illustra le classi gestite usate per sincronizzare le attività di più thread.  
  
 [Procedure consigliate per il threading gestito](managed-threading-best-practices.md)  
 Illustra i problemi comuni del multithreading e le strategie per evitarli.  
  
 [Programmazione parallela](../parallel-programming/index.md)  
 Illustra Task Parallel Library e PLINQ, che semplificano notevolmente la creazione di applicazioni .NET Framework asincrone e multithread.
