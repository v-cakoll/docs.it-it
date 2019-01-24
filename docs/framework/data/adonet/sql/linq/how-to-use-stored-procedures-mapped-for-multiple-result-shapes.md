---
title: 'Procedura: Utilizzare le Stored procedure mappate per più forme di risultati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
ms.openlocfilehash: 6ea318e89cf91dcbf16747117b8000dfa3f9571d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573669"
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a><span data-ttu-id="2e109-102">Procedura: Utilizzare le Stored procedure mappate per più forme di risultati</span><span class="sxs-lookup"><span data-stu-id="2e109-102">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>
<span data-ttu-id="2e109-103">Quando una stored procedure consente di restituire più forme di risultati, il tipo restituito non può essere fortemente tipizzato a una singola forma di proiezione.</span><span class="sxs-lookup"><span data-stu-id="2e109-103">When a stored procedure can return multiple result shapes, the return type cannot be strongly typed to a single projection shape.</span></span> <span data-ttu-id="2e109-104">Sebbene [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] può generare tutti i tipi di proiezione possibili, non è possibile conoscere l'ordine in cui saranno restituiti.</span><span class="sxs-lookup"><span data-stu-id="2e109-104">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can generate all possible projection types, it cannot know the order in which they will be returned.</span></span>  
  
 <span data-ttu-id="2e109-105">Si consideri questo scenario rispetto a stored procedure che producono più forme di risultati in sequenza.</span><span class="sxs-lookup"><span data-stu-id="2e109-105">Contrast this scenario with stored procedures that produce multiple result shapes sequentially.</span></span> <span data-ttu-id="2e109-106">Per altre informazioni, vedere [Procedura: Utilizzare le Stored procedure mappate per forme di risultati sequenziali](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="2e109-106">For more information, see [How to: Use Stored Procedures Mapped for Sequential Result Shapes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).</span></span>  
  
 <span data-ttu-id="2e109-107">L'attributo <xref:System.Data.Linq.Mapping.ResultTypeAttribute> viene applicato a stored procedure che restituiscono più tipi di risultati per specificare il set di tipi che la stored procedure può restituire.</span><span class="sxs-lookup"><span data-stu-id="2e109-107">The <xref:System.Data.Linq.Mapping.ResultTypeAttribute> attribute is applied to stored procedures that return multiple result types to specify the set of types the procedure can return.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e109-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e109-108">Example</span></span>  
 <span data-ttu-id="2e109-109">Nell'esempio di codice SQL riportato di seguito la forma dei risultati dipende dall'input (`shape =1` o `shape = 2`).</span><span class="sxs-lookup"><span data-stu-id="2e109-109">In the following SQL code example, the result shape depends on the input (`shape =1` or `shape = 2`).</span></span> <span data-ttu-id="2e109-110">Non si conosce la proiezione che verrà restituita per prima.</span><span class="sxs-lookup"><span data-stu-id="2e109-110">You do not know which projection will be returned first.</span></span>  
  
```  
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="2e109-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e109-111">Example</span></span>  
 <span data-ttu-id="2e109-112">Per eseguire questa stored procedure si utilizzerà codice simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="2e109-112">You would use code similar to the following to execute this stored procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e109-113">È necessario usare il modello <xref:System.Data.Linq.IMultipleResults.GetResult%2A> per ottenere un enumeratore di tipo corretto, in base alla propria conoscenza della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="2e109-113">You must use the <xref:System.Data.Linq.IMultipleResults.GetResult%2A> pattern to obtain an enumerator of the correct type, based on your knowledge of the stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="2e109-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e109-114">See also</span></span>
- [<span data-ttu-id="2e109-115">stored procedure</span><span class="sxs-lookup"><span data-stu-id="2e109-115">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
