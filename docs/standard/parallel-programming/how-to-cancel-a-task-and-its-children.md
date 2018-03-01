---
title: "Procedura: Annullare un'attività e i relativi figli"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ecccd5ddd3ff662b03ae7078aabaf58e397f7003
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-cancel-a-task-and-its-children"></a>Procedura: Annullare un'attività e i relativi figli
Questi esempi mostrano come eseguire le attività seguenti:  
  
1.  Creare e avviare un'attività annullabile.  
  
2.  Passare un token di annullamento al delegato dell'utente e, facoltativamente, all'istanza dell'attività.  
  
3.  Rilevare e rispondere alla richiesta di annullamento nel delegato dell'utente.  
  
4.  Facoltativamente, indicare nel thread chiamante che l'attività è stata annullata.  
  
 Il thread chiamante non forza la fine dell'attività, ma segnala solo che è richiesto l'annullamento. Se l'attività è già in esecuzione, è responsabilità del delegato dell'utente rilevare la richiesta e rispondervi nel modo appropriato. Se l'annullamento viene richiesto prima dell'esecuzione dell'attività, il delegato dell'utente non viene mai eseguito e l'oggetto attività passa allo stato annullato.  
  
## <a name="example"></a>Esempio  
 Questo esempio mostra come terminare un'attività <xref:System.Threading.Tasks.Task> e i relativi elementi figlio in risposta a una richiesta di annullamento. Viene inoltre mostrato che quando un delegato dell'utente viene terminato generando un oggetto <xref:System.Threading.Tasks.TaskCanceledException>, tramite il thread chiamante è possibile utilizzare facoltativamente il metodo <xref:System.Threading.Tasks.Task.Wait%2A> o il metodo <xref:System.Threading.Tasks.Task.WaitAll%2A> per attendere il completamento delle attività. In questo caso, è necessario utilizzare un blocco `try/catch` per gestire le eccezioni nel thread chiamante.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 La classe <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> è completamente integrata con il modello di annullamento basato sui tipi <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> e <xref:System.Threading.CancellationToken?displayProperty=nameWithType>. Per altre informazioni, vedere [Annullamento in thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md) e [Annullamento delle attività](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>  
 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>  
 [Programmazione asincrona basata su attività](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
 [Attività figlio connesse e disconnesse](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)  
 [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
