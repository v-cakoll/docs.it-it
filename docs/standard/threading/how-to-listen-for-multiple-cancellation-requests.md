---
title: "Procedura: Ascolto di più richieste di annullamento"
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
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36cf338a15ad3f7d234f902c50a2dbb1b2e95847
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a>Procedura: Ascolto di più richieste di annullamento
In questo esempio viene illustrato come contemporaneamente in attesa di due token di annullamento in modo che se uno dei token lo richiede, è possibile annullare un'operazione.  
  
> [!NOTE]
>  Quando "Just My Code" è abilitato, Visual Studio in alcuni casi si interromperà in corrispondenza della riga che genera l'eccezione e visualizzerà un messaggio di errore simile a "Eccezione non gestita dal codice utente". Questo errore non è grave. È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti. Per impedire l'interruzione per il primo errore di Visual Studio, deselezionare semplicemente la casella di controllo "Just My Code" **strumenti, opzioni, debug, generale**.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> metodo viene utilizzato per unire due token in un token. In questo modo il token deve essere passato ai metodi che accettano l'annullamento di un solo token come argomento. Nell'esempio viene illustrato uno scenario comune in cui un metodo è necessario osservare sia un token passato dall'esterno della classe e un token generato all'interno della classe.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 Quando il token collegato genera un <xref:System.OperationCanceledException>, il token passato all'eccezione è il token collegato, non uno dei token del predecessore. Per determinare quale dei token è stata annullata, controllare lo stato dei token del predecessore direttamente.  
  
 In questo esempio, <xref:System.AggregateException> non deve essere mai generata, ma venga intercettato qui perché in scenari reali eccezione <xref:System.OperationCanceledException> generati da un delegato di attività viene eseguito il wrapping un <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>Vedere anche  
 [Annullamento in thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md)
