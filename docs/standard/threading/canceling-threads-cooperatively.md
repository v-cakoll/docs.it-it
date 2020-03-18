---
title: Annullamento cooperativo di thread
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
ms.openlocfilehash: 1d1433ecf39974bf9e68fe07b9d0818ac16fb544
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138132"
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="1230e-102">Annullamento cooperativo di thread</span><span class="sxs-lookup"><span data-stu-id="1230e-102">Canceling threads cooperatively</span></span>

<span data-ttu-id="1230e-103">Nelle versioni precedenti a .NET Framework 4, .NET Framework non offriva alcun metodo incorporato per annullare un thread in modo cooperativo dopo l'avvio dello stesso.</span><span class="sxs-lookup"><span data-stu-id="1230e-103">Prior to the .NET Framework 4, the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="1230e-104">Tuttavia, a partire dalla versione .NET Framework 4, è possibile usare <xref:System.Threading.CancellationToken?displayProperty=nameWithType> per annullare i thread, nello stesso modo in cui è possibile usarli per annullare oggetti <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="1230e-104">However, starting with the .NET Framework 4, you can use a <xref:System.Threading.CancellationToken?displayProperty=nameWithType> to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="1230e-105">Anche se la classe <xref:System.Threading.Thread?displayProperty=nameWithType> non offre supporto predefinito per i token di annullamento, è possibile passare un token a una routine del thread usando il costruttore <xref:System.Threading.Thread> che accetta un delegato <xref:System.Threading.ParameterizedThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="1230e-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="1230e-106">Nell'esempio riportato di seguito viene illustrato come procedere.</span><span class="sxs-lookup"><span data-stu-id="1230e-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="1230e-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1230e-107">See also</span></span>

- [<span data-ttu-id="1230e-108">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="1230e-108">Using Threads and Threading</span></span>](using-threads-and-threading.md)
