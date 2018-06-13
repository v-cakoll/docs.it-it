---
title: Thread.Suspend, operazioni di Garbage Collection e punti sicuri
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ded5c057b1c257e8bcf3c8427f5810720eaf0947
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582161"
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend, operazioni di Garbage Collection e punti sicuri
Quando si chiama <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> su un thread, nel sistema viene rilevato che è stata richiesta una sospensione di thread, di cui viene consentita l'esecuzione fino al raggiungimento di un punto sicuro, prima di sospendere effettivamente il thread. Per un thread, un punto sicuro è un punto nell'esecuzione in corrispondenza del quale è possibile eseguire operazioni di Garbage Collection.  
  
 Dopo aver raggiunto un punto sicuro, il runtime garantisce che il thread sospeso non effettuerà ulteriori avanzamenti nel codice gestito. Un thread in esecuzione all'esterno del codice gestito è sempre sicuro per le operazioni di Garbage Collection e l'esecuzione continua finché non tenta di riprendere l'esecuzione del codice gestito.  
  
> [!NOTE]
>  Per eseguire un'operazione di Garbage Collection, è necessario che vengano sospesi tutti i thread ad eccezione di quello che esegue la raccolta. Ogni thread deve essere portato a un punto sicuro prima di poter essere sospeso.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Gestione automatica della memoria](../../../docs/standard/automatic-memory-management.md)
