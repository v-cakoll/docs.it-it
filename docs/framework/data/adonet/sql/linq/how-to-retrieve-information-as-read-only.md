---
title: 'Procedura: Recuperare informazioni in sola lettura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 399bf44ef5536a9adebf1cad590439741df998f0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793311"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="35df2-102">Procedura: Recuperare informazioni in sola lettura</span><span class="sxs-lookup"><span data-stu-id="35df2-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="35df2-103">Quando non si prevede di modificare i dati, è possibile migliorare le prestazione delle query effettuando la ricerca di risultati di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="35df2-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="35df2-104">Per implementare l'elaborazione di sola lettura, impostare <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="35df2-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35df2-105">Quando <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> è impostato su `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> viene impostato in modo implicito su `false`.</span><span class="sxs-lookup"><span data-stu-id="35df2-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35df2-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="35df2-106">Example</span></span>  
 <span data-ttu-id="35df2-107">Nel codice seguente viene recuperato una raccolta di date di assunzione dei dipendenti di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="35df2-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="35df2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35df2-108">See also</span></span>

- [<span data-ttu-id="35df2-109">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="35df2-109">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="35df2-110">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="35df2-110">Querying the Database</span></span>](querying-the-database.md)
- [<span data-ttu-id="35df2-111">Caricamento posticipato e immediato</span><span class="sxs-lookup"><span data-stu-id="35df2-111">Deferred versus Immediate Loading</span></span>](deferred-versus-immediate-loading.md)
