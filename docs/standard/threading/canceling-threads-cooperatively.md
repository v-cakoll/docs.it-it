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
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="fb98d-102">Annullamento cooperativo di thread</span><span class="sxs-lookup"><span data-stu-id="fb98d-102">Canceling Threads Cooperatively</span></span>
<span data-ttu-id="fb98d-103">Nelle versioni precedenti a [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework non forniva alcun metodo incorporato per annullare un thread in modo cooperativo dopo l'avvio dello stesso.</span><span class="sxs-lookup"><span data-stu-id="fb98d-103">Prior to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="fb98d-104">Tuttavia, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile utilizzare i token di annullamento per annullare i thread, così come è possibile usarli per annullare <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> oggetti o query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="fb98d-104">However, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use cancellation tokens to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="fb98d-105">Sebbene il <xref:System.Threading.Thread?displayProperty=nameWithType> classe offre supporto incorporato per i token di annullamento, è possibile passare un token per una procedura thread usando il <xref:System.Threading.Thread> costruttore che accetta un <xref:System.Threading.ParameterizedThreadStart> delegato.</span><span class="sxs-lookup"><span data-stu-id="fb98d-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="fb98d-106">Nell'esempio riportato di seguito viene illustrato come procedere.</span><span class="sxs-lookup"><span data-stu-id="fb98d-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="fb98d-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb98d-107">See Also</span></span>  
 [<span data-ttu-id="fb98d-108">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="fb98d-108">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
