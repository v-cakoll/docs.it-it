---
title: Thread.Suspend, operazioni di Garbage Collection e punti sicuri
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e47674ef8d1b1a7487e42765bcbce4b33cf98769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend, operazioni di Garbage Collection e punti sicuri
Quando si chiama <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> su un thread, il sistema rileva che una sospensione di thread è stato richiesto e consente l'esecuzione fino a quando non è stato raggiunto un punto sicuro prima di sospendere effettivamente il thread del thread. Un punto sicuro per un thread è un punto nell'esecuzione delle Garbage collection può essere eseguita.  
  
 Quando viene raggiunto un punto sicuro, il runtime garantisce che il thread sospeso non effettuerà ulteriori progressi nel codice gestito. Un thread in esecuzione all'esterno di codice gestito è sempre sicuro per l'operazione di garbage collection e l'esecuzione continua fino a quando non tenta di riprendere l'esecuzione del codice gestito.  
  
> [!NOTE]
>  Per eseguire un'operazione di garbage collection, il runtime deve sospendere tutti i thread eccetto quello che esegue la raccolta. Ogni thread deve essere portato a un punto sicuro prima di poter essere sospeso.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Gestione automatica della memoria](../../../docs/standard/automatic-memory-management.md)
