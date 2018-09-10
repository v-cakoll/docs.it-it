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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd32deb9c8719a12b76aaea8ec91a17471cf18f9
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259860"
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="bf360-102">Annullamento cooperativo di thread</span><span class="sxs-lookup"><span data-stu-id="bf360-102">Canceling threads cooperatively</span></span>

<span data-ttu-id="bf360-103">Nelle versioni precedenti a .NET Framework 4, .NET Framework non offriva alcun metodo incorporato per annullare un thread in modo cooperativo dopo l'avvio dello stesso.</span><span class="sxs-lookup"><span data-stu-id="bf360-103">Prior to the .NET Framework 4, the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="bf360-104">Tuttavia, a partire dalla versione .NET Framework 4, è possibile usare <xref:System.Threading.CancellationToken?displayProperty=nameWithType> per annullare i thread, nello stesso modo in cui è possibile usarli per annullare oggetti <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="bf360-104">However, starting with the .NET Framework 4, you can use a <xref:System.Threading.CancellationToken?displayProperty=nameWithType> to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="bf360-105">Anche se la classe <xref:System.Threading.Thread?displayProperty=nameWithType> non offre supporto predefinito per i token di annullamento, è possibile passare un token a una routine del thread usando il costruttore <xref:System.Threading.Thread> che accetta un delegato <xref:System.Threading.ParameterizedThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="bf360-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="bf360-106">Nell'esempio riportato di seguito viene illustrato come procedere.</span><span class="sxs-lookup"><span data-stu-id="bf360-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="bf360-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf360-107">See also</span></span>

- [<span data-ttu-id="bf360-108">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="bf360-108">Using Threads and Threading</span></span>](using-threads-and-threading.md)
