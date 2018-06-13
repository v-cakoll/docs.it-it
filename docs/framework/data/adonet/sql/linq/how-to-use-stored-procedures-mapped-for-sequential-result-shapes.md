---
title: 'Procedura: utilizzare stored procedure mappate per forme di risultati sequenziali'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: ade123f10e1c9ffd6d042b45599cc6e352614e5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351940"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="12497-102">Procedura: utilizzare stored procedure mappate per forme di risultati sequenziali</span><span class="sxs-lookup"><span data-stu-id="12497-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>
<span data-ttu-id="12497-103">Questo tipo di stored procedure può generare più di una forma di risultati, tuttavia si conosce l'ordine in cui tali risultati vengono restituiti.</span><span class="sxs-lookup"><span data-stu-id="12497-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="12497-104">Si consideri questo scenario rispetto allo scenario in cui non si conosca la sequenza dei risultati restituiti.</span><span class="sxs-lookup"><span data-stu-id="12497-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="12497-105">Per ulteriori informazioni, vedere [procedura: utilizzare Stored procedure mappate per più forme di risultati](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="12497-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="12497-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="12497-106">Example</span></span>  
 <span data-ttu-id="12497-107">Di seguito è riportato il codice T-SQL di un stored procedure che restituisce più forme di risultati in sequenza:</span><span class="sxs-lookup"><span data-stu-id="12497-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="12497-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="12497-108">Example</span></span>  
 <span data-ttu-id="12497-109">Per eseguire questa stored procedure si utilizzerà codice simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="12497-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="12497-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12497-110">See Also</span></span>  
 [<span data-ttu-id="12497-111">stored procedure</span><span class="sxs-lookup"><span data-stu-id="12497-111">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
