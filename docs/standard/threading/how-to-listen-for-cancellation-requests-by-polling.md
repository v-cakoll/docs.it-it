---
title: 'Procedura: mettersi in ascolto di richieste di annullamento tramite polling'
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a>Procedura: mettersi in ascolto di richieste di annullamento tramite polling
Nell'esempio seguente viene illustrato un modo che il codice utente può eseguire il polling di un token di annullamento a intervalli regolari per vedere se è stato richiesto l'annullamento dal thread chiamante. Questo esempio viene utilizzato il <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> tipo, ma lo stesso modello si applica alle operazioni asincrone create direttamente mediante il <xref:System.Threading.ThreadPool?displayProperty=nameWithType> tipo o <xref:System.Threading.Thread?displayProperty=nameWithType> tipo.  
  
## <a name="example"></a>Esempio  
 Polling richiede un tipo di codice di ciclo o ricorsivo in grado di leggere periodicamente il valore della proprietà booleana <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> proprietà. Se si utilizza il <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> tipo ed è in attesa per l'attività da completare sul thread chiamante, è possibile utilizzare il <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> per controllare la proprietà e generare l'eccezione. Tramite questo metodo, assicurarsi che l'eccezione corretta è generata in risposta a una richiesta. Se si utilizza un <xref:System.Threading.Tasks.Task>, quindi chiamare questo metodo è migliore generazione manuale di un <xref:System.OperationCanceledException>. Se non si dispone generare l'eccezione, quindi è solo possibile controllare la proprietà e restituito dal metodo, se la proprietà è `true`.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 La chiamata <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> è estremamente veloce e non comporta un sovraccarico significativo nei cicli.  
  
 Se si chiama <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, è necessario verificare in modo esplicito il <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> proprietà se si dispone di altre attività da eseguire in risposta all'annullamento oltre alla generazione dell'eccezione. In questo esempio, si noterà che il codice effettivamente accede alla proprietà due volte: una volta tramite accesso esplicito e nuovamente il <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> metodo. Tuttavia, poiché l'operazione di lettura di <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> proprietà include solo un'istruzione per l'accesso di lettura volatile, il doppio accesso non è significativo dal punto di vista delle prestazioni. È preferibile chiamare il metodo anziché generare manualmente il <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>Vedere anche  
 [Annullamento in thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md)
