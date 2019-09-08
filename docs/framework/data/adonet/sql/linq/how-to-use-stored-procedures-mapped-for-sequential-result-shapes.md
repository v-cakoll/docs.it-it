---
title: 'Procedura: Usare stored procedure mappate per forme di risultati sequenziali'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: bae10e823a274304f21292cf55947a4d4eaccc10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781465"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="c1dbe-102">Procedura: Usare stored procedure mappate per forme di risultati sequenziali</span><span class="sxs-lookup"><span data-stu-id="c1dbe-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>
<span data-ttu-id="c1dbe-103">Questo tipo di stored procedure può generare più di una forma di risultati, tuttavia si conosce l'ordine in cui tali risultati vengono restituiti.</span><span class="sxs-lookup"><span data-stu-id="c1dbe-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="c1dbe-104">Si consideri questo scenario rispetto allo scenario in cui non si conosca la sequenza dei risultati restituiti.</span><span class="sxs-lookup"><span data-stu-id="c1dbe-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="c1dbe-105">Per altre informazioni, vedere [Procedura: Utilizzare stored procedure mappate per più forme](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)di risultato.</span><span class="sxs-lookup"><span data-stu-id="c1dbe-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1dbe-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1dbe-106">Example</span></span>  
 <span data-ttu-id="c1dbe-107">Di seguito è riportato il codice T-SQL di un stored procedure che restituisce più forme di risultati in sequenza:</span><span class="sxs-lookup"><span data-stu-id="c1dbe-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="c1dbe-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1dbe-108">Example</span></span>  
 <span data-ttu-id="c1dbe-109">Per eseguire questa stored procedure si utilizzerà codice simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="c1dbe-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="c1dbe-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1dbe-110">See also</span></span>

- [<span data-ttu-id="c1dbe-111">stored procedure</span><span class="sxs-lookup"><span data-stu-id="c1dbe-111">Stored Procedures</span></span>](stored-procedures.md)
