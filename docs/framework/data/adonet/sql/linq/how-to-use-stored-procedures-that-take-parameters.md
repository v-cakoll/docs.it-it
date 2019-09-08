---
title: 'Procedura: Usare stored procedure che accettano parametri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: 4f2636d3bb248adbb6b912887012b0b9c246c590
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793066"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="0f8e5-102">Procedura: Usare stored procedure che accettano parametri</span><span class="sxs-lookup"><span data-stu-id="0f8e5-102">How to: Use Stored Procedures that Take Parameters</span></span>
<span data-ttu-id="0f8e5-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping dei parametri di output ai parametri di riferimento, mentre per i tipi di valori il parametro viene dichiarato come nullable.</span><span class="sxs-lookup"><span data-stu-id="0f8e5-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="0f8e5-104">Per un esempio di come usare un parametro di input in una query che restituisce un set di righe [, vedere Procedura: Restituisce set di](how-to-return-rowsets.md)righe.</span><span class="sxs-lookup"><span data-stu-id="0f8e5-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f8e5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f8e5-105">Example</span></span>  
 <span data-ttu-id="0f8e5-106">Nell'esempio seguente viene accettato un solo parametro di input (l'ID del cliente) e viene restituito un parametro out (le vendite totali per quel cliente).</span><span class="sxs-lookup"><span data-stu-id="0f8e5-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="0f8e5-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f8e5-107">Example</span></span>  
 <span data-ttu-id="0f8e5-108">Chiamare questa stored procedure come segue:</span><span class="sxs-lookup"><span data-stu-id="0f8e5-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="0f8e5-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f8e5-109">See also</span></span>

- [<span data-ttu-id="0f8e5-110">stored procedure</span><span class="sxs-lookup"><span data-stu-id="0f8e5-110">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="0f8e5-111">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="0f8e5-111">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="0f8e5-112">Uso dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="0f8e5-112">Using Nullable Types</span></span>](../../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="0f8e5-113">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="0f8e5-113">Nullable Value Types</span></span>](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
