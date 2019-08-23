---
title: 'Procedura: Usare stored procedure che accettano parametri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: 17ae74a430df4d4a4670c2390ce7b2ee25b67c7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938706"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="dfb79-102">Procedura: Usare stored procedure che accettano parametri</span><span class="sxs-lookup"><span data-stu-id="dfb79-102">How to: Use Stored Procedures that Take Parameters</span></span>
<span data-ttu-id="dfb79-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping dei parametri di output ai parametri di riferimento, mentre per i tipi di valori il parametro viene dichiarato come nullable.</span><span class="sxs-lookup"><span data-stu-id="dfb79-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="dfb79-104">Per un esempio di come usare un parametro di input in una query che restituisce un set di righe [, vedere Procedura: Restituisce set di](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)righe.</span><span class="sxs-lookup"><span data-stu-id="dfb79-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfb79-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfb79-105">Example</span></span>  
 <span data-ttu-id="dfb79-106">Nell'esempio seguente viene accettato un solo parametro di input (l'ID del cliente) e viene restituito un parametro out (le vendite totali per quel cliente).</span><span class="sxs-lookup"><span data-stu-id="dfb79-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="dfb79-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfb79-107">Example</span></span>  
 <span data-ttu-id="dfb79-108">Chiamare questa stored procedure come segue:</span><span class="sxs-lookup"><span data-stu-id="dfb79-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="dfb79-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfb79-109">See also</span></span>

- [<span data-ttu-id="dfb79-110">stored procedure</span><span class="sxs-lookup"><span data-stu-id="dfb79-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [<span data-ttu-id="dfb79-111">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="dfb79-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="dfb79-112">Uso dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="dfb79-112">Using Nullable Types</span></span>](../../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="dfb79-113">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="dfb79-113">Nullable Value Types</span></span>](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
