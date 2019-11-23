---
title: "Procedura: utilizzare funzioni definite dall'utente con valori scalari"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: dfe82fd50eb3eedeaff9082a4288901f72197795
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003231"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a><span data-ttu-id="8903b-102">Procedura: utilizzare funzioni definite dall'utente con valori scalari</span><span class="sxs-lookup"><span data-stu-id="8903b-102">How to: Use Scalar-Valued User-Defined Functions</span></span>
<span data-ttu-id="8903b-103">È possibile eseguire il mapping di un metodo client definito in una classe a una funzione definita dall'utente usando l'attributo <xref:System.Data.Linq.Mapping.FunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8903b-103">You can map a client method defined on a class to a user-defined function by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute.</span></span> <span data-ttu-id="8903b-104">Notare che nel corpo del metodo viene costruita un'espressione che acquisisce lo scopo della chiamata al metodo e passa quell'espressione a <xref:System.Data.Linq.DataContext> per la conversione e l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8903b-104">Note that the body of the method constructs an expression that captures the intent of the method call, and passes that expression to the <xref:System.Data.Linq.DataContext> for translation and execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8903b-105">Si verifica l'esecuzione diretta solo se la funzione viene chiamata all'esterno di una query.</span><span class="sxs-lookup"><span data-stu-id="8903b-105">Direct execution occurs only if the function is called outside a query.</span></span> <span data-ttu-id="8903b-106">Per altre informazioni, vedere [procedura: chiamare funzioni definite dall'utente inline](how-to-call-user-defined-functions-inline.md).</span><span class="sxs-lookup"><span data-stu-id="8903b-106">For more information, see [How to: Call User-Defined Functions Inline](how-to-call-user-defined-functions-inline.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8903b-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="8903b-107">Example</span></span>  
 <span data-ttu-id="8903b-108">Nel codice SQL seguente viene presentata una funzione con valori scalari definita dall'utente `ReverseCustName()`.</span><span class="sxs-lookup"><span data-stu-id="8903b-108">The following SQL code presents a scalar-valued user-defined function `ReverseCustName()`.</span></span>  
  
```sql  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 <span data-ttu-id="8903b-109">Per questo codice si eseguirà il mapping di un metodo client come il seguente:</span><span class="sxs-lookup"><span data-stu-id="8903b-109">You would map a client method such as the following for this code:</span></span>  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8903b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8903b-110">See also</span></span>

- [<span data-ttu-id="8903b-111">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="8903b-111">User-Defined Functions</span></span>](user-defined-functions.md)
