---
title: "Procedura: eseguire il wrapping di modelli EAP in un'attività"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
ms.openlocfilehash: ac7436892c644340286bb4670bf75c9cd63a8ce5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106826"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="dd4ea-102">Procedura: eseguire il wrapping di modelli EAP in un'attività</span><span class="sxs-lookup"><span data-stu-id="dd4ea-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="dd4ea-103">Nell'esempio seguente viene illustrato come esporre una sequenza arbitraria di operazioni del modello asincrono basato su eventi (EAP) come un'unica attività tramite un oggetto <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span><span class="sxs-lookup"><span data-stu-id="dd4ea-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="dd4ea-104">L'esempio mostra anche come usare un oggetto <xref:System.Threading.CancellationToken> per richiamare i metodi di annullamento predefiniti sugli oggetti <xref:System.Net.WebClient>.</span><span class="sxs-lookup"><span data-stu-id="dd4ea-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd4ea-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd4ea-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="dd4ea-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd4ea-106">See also</span></span>

- [<span data-ttu-id="dd4ea-107">Task Parallel Library e programmazione asincrona .NET Framework tradizionale</span><span class="sxs-lookup"><span data-stu-id="dd4ea-107">TPL and Traditional .NET Framework Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
