---
title: 'Procedura: Utilizzare le Stored procedure che accettano parametri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: b81cb3b7428ba2ed4e958e18e9368f6f774e8ee3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604237"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="3dad7-102">Procedura: Utilizzare le Stored procedure che accettano parametri</span><span class="sxs-lookup"><span data-stu-id="3dad7-102">How to: Use Stored Procedures that Take Parameters</span></span>
<span data-ttu-id="3dad7-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping dei parametri di output ai parametri di riferimento, mentre per i tipi di valori il parametro viene dichiarato come nullable.</span><span class="sxs-lookup"><span data-stu-id="3dad7-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="3dad7-104">Per un esempio di come usare un parametro di input in una query che restituisce un set di righe, vedere [come: Restituire rowset](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="3dad7-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dad7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="3dad7-105">Example</span></span>  
 <span data-ttu-id="3dad7-106">Nell'esempio seguente viene accettato un solo parametro di input (l'ID del cliente) e viene restituito un parametro out (le vendite totali per quel cliente).</span><span class="sxs-lookup"><span data-stu-id="3dad7-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
```  
CREATE PROCEDURE [dbo].[CustOrderTotal]   
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="3dad7-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="3dad7-107">Example</span></span>  
 <span data-ttu-id="3dad7-108">Chiamare questa stored procedure come segue:</span><span class="sxs-lookup"><span data-stu-id="3dad7-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3dad7-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dad7-109">See also</span></span>
- [<span data-ttu-id="3dad7-110">stored procedure</span><span class="sxs-lookup"><span data-stu-id="3dad7-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [<span data-ttu-id="3dad7-111">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="3dad7-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="3dad7-112">Uso dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="3dad7-112">Using Nullable Types</span></span>](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="3dad7-113">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="3dad7-113">Nullable Value Types</span></span>](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
