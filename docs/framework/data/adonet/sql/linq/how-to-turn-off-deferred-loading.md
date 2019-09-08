---
title: 'Procedura: Disattivare il caricamento posticipato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 6559392527bb02afe9cea61e704f1f371c6d5470
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781649"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="36eac-102">Procedura: Disattivare il caricamento posticipato</span><span class="sxs-lookup"><span data-stu-id="36eac-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="36eac-103">È possibile disattivare il caricamento posticipato impostando <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="36eac-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="36eac-104">Per ulteriori informazioni, vedere il [caricamento posticipato rispetto al caricamento immediato](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="36eac-104">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36eac-105">Il caricamento posticipato viene disattivato implicitamente quando è disattivato il rilevamento degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="36eac-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="36eac-106">Per altre informazioni, vedere [Procedura: Recuperare informazioni in sola lettura](how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="36eac-106">For more information, see [How to: Retrieve Information As Read-Only](how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="36eac-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="36eac-107">Example</span></span>  
 <span data-ttu-id="36eac-108">Nell'esempio seguente viene descritto come disattivare il caricamento posticipato impostando <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="36eac-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="36eac-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36eac-109">See also</span></span>

- [<span data-ttu-id="36eac-110">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="36eac-110">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="36eac-111">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="36eac-111">Querying the Database</span></span>](querying-the-database.md)
