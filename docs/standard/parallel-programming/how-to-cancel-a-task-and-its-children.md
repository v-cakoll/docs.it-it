---
title: "Procedura: Annullare un'attività e i relativi figli"
description: Vedere esempi di come annullare un'attività e i relativi elementi figlio in .NET. Gli esempi illustrano i passaggi della creazione di un'attività annullabile, fino alla nota che l'attività è stata annullata.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: 66daf00680b65aace1ce6367761e3ed81596d33b
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662680"
---
# <a name="how-to-cancel-a-task-and-its-children"></a>Procedura: Annullare un'attività e i relativi figli
Questi esempi mostrano come eseguire le attività seguenti:  
  
1. Creare e avviare un'attività annullabile.  
  
2. Passare un token di annullamento al delegato dell'utente e, facoltativamente, all'istanza dell'attività.  
  
3. Rilevare e rispondere alla richiesta di annullamento nel delegato dell'utente.  
  
4. Facoltativamente, indicare nel thread chiamante che l'attività è stata annullata.  
  
 Il thread chiamante non forza la fine dell'attività, ma segnala solo che è richiesto l'annullamento. Se l'attività è già in esecuzione, è responsabilità del delegato dell'utente rilevare la richiesta e rispondervi nel modo appropriato. Se l'annullamento viene richiesto prima dell'esecuzione dell'attività, il delegato dell'utente non viene mai eseguito e l'oggetto attività passa allo stato annullato.  
  
## <a name="example"></a>Esempio  
 Questo esempio mostra come terminare un'attività <xref:System.Threading.Tasks.Task> e i relativi elementi figlio in risposta a una richiesta di annullamento. Viene inoltre mostrato che quando un delegato dell'utente viene terminato generando un oggetto <xref:System.Threading.Tasks.TaskCanceledException>, tramite il thread chiamante è possibile utilizzare facoltativamente il metodo <xref:System.Threading.Tasks.Task.Wait%2A> o il metodo <xref:System.Threading.Tasks.Task.WaitAll%2A> per attendere il completamento delle attività. In questo caso, è necessario utilizzare un blocco `try/catch` per gestire le eccezioni nel thread chiamante.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 La classe <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> è completamente integrata con il modello di annullamento basato sui tipi <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> e <xref:System.Threading.CancellationToken?displayProperty=nameWithType>. Per altre informazioni, vedere [Annullamento in thread gestiti](../threading/cancellation-in-managed-threads.md) e [Annullamento delle attività](task-cancellation.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [Programmazione asincrona basata su attività](task-based-asynchronous-programming.md)
- [Attività figlio connesse e disconnesse](attached-and-detached-child-tasks.md)
- [Espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md)
