---
title: 'Procedura: Recuperare informazioni in sola lettura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 131562e9ee0fbfde8c94f580bcb6d452918f42ee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148980"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="3274c-102">Procedura: Recuperare informazioni in sola lettura</span><span class="sxs-lookup"><span data-stu-id="3274c-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="3274c-103">Quando non si prevede di modificare i dati, è possibile migliorare le prestazione delle query effettuando la ricerca di risultati di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="3274c-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="3274c-104">Per implementare l'elaborazione di sola lettura, impostare <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="3274c-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3274c-105">Quando <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> è impostato su `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> viene impostato in modo implicito su `false`.</span><span class="sxs-lookup"><span data-stu-id="3274c-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3274c-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="3274c-106">Example</span></span>  
 <span data-ttu-id="3274c-107">Nel codice seguente viene recuperato una raccolta di date di assunzione dei dipendenti di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="3274c-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3274c-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3274c-108">See also</span></span>

- [<span data-ttu-id="3274c-109">Concetti relatici alle query</span><span class="sxs-lookup"><span data-stu-id="3274c-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="3274c-110">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="3274c-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
- [<span data-ttu-id="3274c-111">Caricamento posticipato e immediato</span><span class="sxs-lookup"><span data-stu-id="3274c-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
