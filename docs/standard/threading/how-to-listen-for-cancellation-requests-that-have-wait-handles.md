---
title: 'Procedura: mettersi in ascolto di richieste di annullamento con handle di attesa'
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
helpviewer_keywords: cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1eaa84d924fde63e94c36fab50a809c7c03f075
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a>Procedura: mettersi in ascolto di richieste di annullamento con handle di attesa
Se un metodo è bloccato mentre è in attesa di un evento venga segnalato, non è possibile controllare il valore del token di annullamento e rispondere in modo tempestivo. Nel primo esempio viene illustrato come risolvere questo problema quando si lavora con gli eventi, ad esempio <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> che non supportano in modo nativo il framework di annullamento unificato. Nel secondo esempio viene illustrato un approccio più semplice che utilizza <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, che supporta l'annullamento unificato.  
  
> [!NOTE]
>  Quando "Just My Code" è abilitato, Visual Studio in alcuni casi si interromperà in corrispondenza della riga che genera l'eccezione e visualizzerà un messaggio di errore simile a "Eccezione non gestita dal codice utente". Questo errore non è grave. È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti. Per impedire l'interruzione per il primo errore di Visual Studio, deselezionare semplicemente la casella di controllo "Just My Code" **strumenti, opzioni, debug, generale**.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un <xref:System.Threading.ManualResetEvent> per illustrare come sbloccare gli handle di attesa che non supportano l'annullamento unificato.  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un <xref:System.Threading.ManualResetEventSlim> per illustrare come sbloccare coordination primitive che supportano l'annullamento unificato. Lo stesso approccio è utilizzabile con altri primitive di coordinamento leggere, ad esempio <xref:System.Threading.Semaphore> `Slim` e <xref:System.Threading.CountdownEvent>.  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a>Vedere anche  
 [Annullamento in thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md)
