---
title: 'Procedura: Disattivare il caricamento posticipato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: f68db5a5a0092fc4cf37746f2a4dc81e40ee4a9d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938681"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="983ce-102">Procedura: Disattivare il caricamento posticipato</span><span class="sxs-lookup"><span data-stu-id="983ce-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="983ce-103">È possibile disattivare il caricamento posticipato impostando <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="983ce-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="983ce-104">Per ulteriori informazioni, vedere il [caricamento posticipato rispetto al caricamento immediato](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="983ce-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="983ce-105">Il caricamento posticipato viene disattivato implicitamente quando è disattivato il rilevamento degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="983ce-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="983ce-106">Per altre informazioni, vedere [Procedura: Recuperare informazioni in sola lettura](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="983ce-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="983ce-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="983ce-107">Example</span></span>  
 <span data-ttu-id="983ce-108">Nell'esempio seguente viene descritto come disattivare il caricamento posticipato impostando <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="983ce-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="983ce-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="983ce-109">See also</span></span>

- [<span data-ttu-id="983ce-110">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="983ce-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="983ce-111">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="983ce-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
