---
title: 'Procedura: disattivare il caricamento posticipato'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b0db2b178ba3c043ddadaeb650701ba144ed8e6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="b863e-102">Procedura: disattivare il caricamento posticipato</span><span class="sxs-lookup"><span data-stu-id="b863e-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="b863e-103">È possibile disattivare il caricamento posticipato impostando <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="b863e-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="b863e-104">Per ulteriori informazioni, vedere [posticipata e il caricamento immediato](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="b863e-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b863e-105">Il caricamento posticipato viene disattivato implicitamente quando è disattivato il rilevamento degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="b863e-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="b863e-106">Per ulteriori informazioni, vedere [procedura: recuperare informazioni di sola lettura](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="b863e-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b863e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b863e-107">Example</span></span>  
 <span data-ttu-id="b863e-108">Nell'esempio seguente viene descritto come disattivare il caricamento posticipato impostando <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="b863e-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="b863e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b863e-109">See Also</span></span>  
 [<span data-ttu-id="b863e-110">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="b863e-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="b863e-111">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="b863e-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
