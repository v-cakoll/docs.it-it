---
title: 'Procedura: Recuperare le informazioni in sola lettura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 8b83a77adb02cc2bcc01b274867143887114bb1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669549"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="fb7f4-102">Procedura: Recuperare le informazioni in sola lettura</span><span class="sxs-lookup"><span data-stu-id="fb7f4-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="fb7f4-103">Quando non si prevede di modificare i dati, è possibile migliorare le prestazione delle query effettuando la ricerca di risultati di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="fb7f4-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="fb7f4-104">Per implementare l'elaborazione di sola lettura, impostare <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="fb7f4-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb7f4-105">Quando <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> è impostato su `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> viene impostato in modo implicito su `false`.</span><span class="sxs-lookup"><span data-stu-id="fb7f4-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb7f4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb7f4-106">Example</span></span>  
 <span data-ttu-id="fb7f4-107">Nel codice seguente viene recuperato una raccolta di date di assunzione dei dipendenti di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="fb7f4-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="fb7f4-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb7f4-108">See also</span></span>
- [<span data-ttu-id="fb7f4-109">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="fb7f4-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="fb7f4-110">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="fb7f4-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
- [<span data-ttu-id="fb7f4-111">Caricamento posticipato e immediato</span><span class="sxs-lookup"><span data-stu-id="fb7f4-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
