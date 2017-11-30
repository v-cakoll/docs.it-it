---
title: "Procedura: eseguire il wrapping di modelli EAP in un'attività"
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
helpviewer_keywords: tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ae9d90c9bb3d0e8d315cbef510cdfe1b54e66da4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="bc4d0-102">Procedura: eseguire il wrapping di modelli EAP in un'attività</span><span class="sxs-lookup"><span data-stu-id="bc4d0-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="bc4d0-103">Nell'esempio seguente viene illustrato come esporre una sequenza arbitraria di operazioni del modello asincrono basato su eventi (EAP) come un'unica attività tramite un oggetto <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span><span class="sxs-lookup"><span data-stu-id="bc4d0-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="bc4d0-104">Nell'esempio viene inoltre illustrato come utilizzare un <xref:System.Threading.CancellationToken> per richiamare i metodi di annullamento incorporate sul <xref:System.Net.WebClient> oggetti.</span><span class="sxs-lookup"><span data-stu-id="bc4d0-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc4d0-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc4d0-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="bc4d0-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc4d0-106">See Also</span></span>  
 [<span data-ttu-id="bc4d0-107">Task Parallel Library e programmazione asincrona .NET Framework tradizionale</span><span class="sxs-lookup"><span data-stu-id="bc4d0-107">TPL and Traditional .NET Framework Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
