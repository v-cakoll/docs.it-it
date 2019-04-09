---
title: 'Procedura: Usare stored procedure mappate per forme di risultati sequenziali'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: e51ebacb3f6be849f7b871f2d12db3ea7476b117
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134511"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="c85fb-102">Procedura: Usare stored procedure mappate per forme di risultati sequenziali</span><span class="sxs-lookup"><span data-stu-id="c85fb-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>
<span data-ttu-id="c85fb-103">Questo tipo di stored procedure può generare più di una forma di risultati, tuttavia si conosce l'ordine in cui tali risultati vengono restituiti.</span><span class="sxs-lookup"><span data-stu-id="c85fb-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="c85fb-104">Si consideri questo scenario rispetto allo scenario in cui non si conosca la sequenza dei risultati restituiti.</span><span class="sxs-lookup"><span data-stu-id="c85fb-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="c85fb-105">Per altre informazioni, vedere [Procedura: Utilizzare le Stored procedure mappate per più forme di risultati](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="c85fb-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c85fb-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c85fb-106">Example</span></span>  
 <span data-ttu-id="c85fb-107">Di seguito è riportato il codice T-SQL di un stored procedure che restituisce più forme di risultati in sequenza:</span><span class="sxs-lookup"><span data-stu-id="c85fb-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="c85fb-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="c85fb-108">Example</span></span>  
 <span data-ttu-id="c85fb-109">Per eseguire questa stored procedure si utilizzerà codice simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="c85fb-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="c85fb-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c85fb-110">See also</span></span>

- [<span data-ttu-id="c85fb-111">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="c85fb-111">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
