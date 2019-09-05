---
title: Convertire un tipo in un IEnumerable generico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: c92f65c22fe4b4128a171c757bb9e9c0ccbc3fee
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247724"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="5a433-102">Convertire un tipo in un IEnumerable generico</span><span class="sxs-lookup"><span data-stu-id="5a433-102">Convert a Type to a Generic IEnumerable</span></span>
<span data-ttu-id="5a433-103">Usare <xref:System.Linq.Enumerable.AsEnumerable%2A> per restituire l'argomento tipizzato come `IEnumerable` generico.</span><span class="sxs-lookup"><span data-stu-id="5a433-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a433-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a433-104">Example</span></span>  
 <span data-ttu-id="5a433-105">In questo esempio [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tenta di convertire la query in SQL e di eseguirla sul server usando il tipo `Query` generico predefinito.</span><span class="sxs-lookup"><span data-stu-id="5a433-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="5a433-106">La clausola `where`, tuttavia, fa riferimento a un metodo sul lato client definito dall'utente (`isValidProduct`) che non può essere convertito in SQL.</span><span class="sxs-lookup"><span data-stu-id="5a433-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="5a433-107">La soluzione consiste nello specificare l'implementazione di <xref:System.Collections.Generic.IEnumerable%601> del tipo `where` generico sul lato client per sostituire il tipo <xref:System.Linq.IQueryable%601> generico.</span><span class="sxs-lookup"><span data-stu-id="5a433-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="5a433-108">Per eseguire questa operazione, richiamare l'operatore <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a433-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="5a433-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a433-109">See also</span></span>

- [<span data-ttu-id="5a433-110">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="5a433-110">Query Examples</span></span>](query-examples.md)
