---
title: "Procedura: Usare funzioni definite dall'utente con valori scalari"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: ffb24468c81cb4ec9f41645f8888c2c4ba021609
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127173"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a><span data-ttu-id="79ee4-102">Procedura: Usare funzioni definite dall'utente con valori scalari</span><span class="sxs-lookup"><span data-stu-id="79ee4-102">How to: Use Scalar-Valued User-Defined Functions</span></span>
<span data-ttu-id="79ee4-103">È possibile eseguire il mapping di un metodo client definito in una classe a una funzione definita dall'utente usando l'attributo <xref:System.Data.Linq.Mapping.FunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="79ee4-103">You can map a client method defined on a class to a user-defined function by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute.</span></span> <span data-ttu-id="79ee4-104">Notare che nel corpo del metodo viene costruita un'espressione che acquisisce lo scopo della chiamata al metodo e passa quell'espressione a <xref:System.Data.Linq.DataContext> per la conversione e l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="79ee4-104">Note that the body of the method constructs an expression that captures the intent of the method call, and passes that expression to the <xref:System.Data.Linq.DataContext> for translation and execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79ee4-105">Si verifica l'esecuzione diretta solo se la funzione viene chiamata all'esterno di una query.</span><span class="sxs-lookup"><span data-stu-id="79ee4-105">Direct execution occurs only if the function is called outside a query.</span></span> <span data-ttu-id="79ee4-106">Per altre informazioni, vedere [Procedura: Chiamare funzioni definite dall'utente Inline](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).</span><span class="sxs-lookup"><span data-stu-id="79ee4-106">For more information, see [How to: Call User-Defined Functions Inline](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79ee4-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="79ee4-107">Example</span></span>  
 <span data-ttu-id="79ee4-108">Nel codice SQL seguente viene presentata una funzione con valori scalari definita dall'utente `ReverseCustName()`.</span><span class="sxs-lookup"><span data-stu-id="79ee4-108">The following SQL code presents a scalar-valued user-defined function `ReverseCustName()`.</span></span>  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 <span data-ttu-id="79ee4-109">Per questo codice si eseguirà il mapping di un metodo client come il seguente:</span><span class="sxs-lookup"><span data-stu-id="79ee4-109">You would map a client method such as the following for this code:</span></span>  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="79ee4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79ee4-110">See also</span></span>

- [<span data-ttu-id="79ee4-111">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="79ee4-111">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
