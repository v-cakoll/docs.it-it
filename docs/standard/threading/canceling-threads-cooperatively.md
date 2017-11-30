---
title: Annullamento cooperativo di thread
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
helpviewer_keywords: threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 482f48b347af1a4f76231abcb15abc2f4dba168b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="canceling-threads-cooperatively"></a>Annullamento cooperativo di thread
Nelle versioni precedenti a [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework non forniva alcun metodo incorporato per annullare un thread in modo cooperativo dopo l'avvio dello stesso. Tuttavia, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile utilizzare i token di annullamento per annullare i thread, così come è possibile usarli per annullare <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> oggetti o query PLINQ. Sebbene il <xref:System.Threading.Thread?displayProperty=nameWithType> classe offre supporto incorporato per i token di annullamento, è possibile passare un token per una procedura thread usando il <xref:System.Threading.Thread> costruttore che accetta un <xref:System.Threading.ParameterizedThreadStart> delegato. Nell'esempio riportato di seguito viene illustrato come procedere.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo di thread e threading](../../../docs/standard/threading/using-threads-and-threading.md)
