---
title: 'Procedura: utilizzare stored procedure che accettano parametri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: 05ecc467f75fbeda785b4bac1c3b8b1ceeb173b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174329"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="b2620-102">Procedura: utilizzare stored procedure che accettano parametri</span><span class="sxs-lookup"><span data-stu-id="b2620-102">How to: Use Stored Procedures that Take Parameters</span></span>
<span data-ttu-id="b2620-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping dei parametri di output ai parametri di riferimento, mentre per i tipi di valori il parametro viene dichiarato come nullable.</span><span class="sxs-lookup"><span data-stu-id="b2620-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="b2620-104">Per un esempio di come utilizzare un parametro di input in una query che restituisce un set di righe, vedere [Procedura: restituire set di righe](how-to-return-rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="b2620-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2620-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2620-105">Example</span></span>  
 <span data-ttu-id="b2620-106">Nell'esempio seguente viene accettato un solo parametro di input (l'ID del cliente) e viene restituito un parametro out (le vendite totali per quel cliente).</span><span class="sxs-lookup"><span data-stu-id="b2620-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
```sql
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
  
## <a name="example"></a><span data-ttu-id="b2620-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2620-107">Example</span></span>  
 <span data-ttu-id="b2620-108">Chiamare questa stored procedure come segue:</span><span class="sxs-lookup"><span data-stu-id="b2620-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="b2620-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2620-109">See also</span></span>

- [<span data-ttu-id="b2620-110">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="b2620-110">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="b2620-111">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="b2620-111">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="b2620-112">Tipi di valore nullable (c ')</span><span class="sxs-lookup"><span data-stu-id="b2620-112">Nullable Value Types (C#)</span></span>](../../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
- [<span data-ttu-id="b2620-113">Tipi di valori nullable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2620-113">Nullable Value Types (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
