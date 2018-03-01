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
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 334cbcf8b4a888dbac5962c0fd668673e15e0e29
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="canceling-threads-cooperatively"></a>Annullamento cooperativo di thread
Nelle versioni precedenti a [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework non forniva alcun metodo incorporato per annullare un thread in modo cooperativo dopo l'avvio dello stesso. In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] è tuttavia possibile usare i token di annullamento per annullare i thread, nello stesso modo in cui è possibile usarli per annullare oggetti <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o query PLINQ. Anche se la classe <xref:System.Threading.Thread?displayProperty=nameWithType> non offre supporto predefinito per i token di annullamento, è possibile passare un token a una routine del thread usando il costruttore <xref:System.Threading.Thread> che accetta un delegato <xref:System.Threading.ParameterizedThreadStart>. Nell'esempio riportato di seguito viene illustrato come procedere.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo di thread e threading](../../../docs/standard/threading/using-threads-and-threading.md)
