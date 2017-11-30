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
helpviewer_keywords: tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 374068694a3aa9724905964717dc5e77c09fc0ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-task-and-its-children"></a>Procedura: Annullare un'attività e i relativi figli
Questi esempi illustrano come eseguire le attività seguenti:  
  
1.  Creare e avviare un'attività annullabile.  
  
2.  Passare un token di annullamento al delegato dell'utente e, facoltativamente, per l'istanza dell'attività.  
  
3.  Rilevare e rispondere alla richiesta di annullamento nel delegato dell'utente.  
  
4.  Facoltativamente, si noti sul thread chiamante che l'attività è stata annullata.  
  
 Il thread chiamante non termina forzatamente dell'attività. indica solo che la richiesta di annullamento. Se l'attività è già in esecuzione, è responsabilità del delegato dell'utente si noti che la richiesta e rispondere in modo appropriato. Se la richiesta di annullamento prima dell'esecuzione di attività, il delegato dell'utente non viene mai eseguito e l'oggetto attività passa allo stato Canceled.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come terminare una <xref:System.Threading.Tasks.Task> e relativi elementi figlio in risposta a una richiesta di annullamento. Viene inoltre mostrato che quando un delegato dell'utente viene terminato generando un oggetto <xref:System.Threading.Tasks.TaskCanceledException>, tramite il thread chiamante è possibile utilizzare facoltativamente il metodo <xref:System.Threading.Tasks.Task.Wait%2A> o il metodo <xref:System.Threading.Tasks.Task.WaitAll%2A> per attendere il completamento delle attività. In questo caso, è necessario utilizzare un blocco `try/catch` per gestire le eccezioni nel thread chiamante.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 Il <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classe è completamente integrata con il modello di annullamento che si basa sul <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> e <xref:System.Threading.CancellationToken?displayProperty=nameWithType> tipi. Per ulteriori informazioni, vedere [annullamento in thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md) e [annullamento delle attività](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>  
 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>  
 [Programmazione asincrona basata su attività](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
 [Attività figlio connesse e disconnesse](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)  
 [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
