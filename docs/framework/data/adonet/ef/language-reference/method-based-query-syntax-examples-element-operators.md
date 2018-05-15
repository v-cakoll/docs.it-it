---
title: 'Esempi di sintassi di query basate sul metodo: operatori di elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 0933b1852d87f4f00a77aacfd9ea2cf19a3e9a1f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="ca69d-102">Esempi di sintassi di query basate sul metodo: operatori di elemento</span><span class="sxs-lookup"><span data-stu-id="ca69d-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="ca69d-103">Negli esempi in questo argomento viene illustrato come utilizzare il <xref:System.Linq.Enumerable.First%2A> metodo per eseguire query di [modello Sales di AdventureWorks](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) utilizzando la sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="ca69d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="ca69d-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ca69d-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ca69d-105">Nell'esempio di questo argomento utilizza il seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="ca69d-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="ca69d-106">First</span><span class="sxs-lookup"><span data-stu-id="ca69d-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="ca69d-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca69d-107">Example</span></span>  
 <span data-ttu-id="ca69d-108">L'esempio seguente usa il <xref:System.Linq.Enumerable.First%2A> metodo per trovare il primo indirizzo di posta elettronica che inizia con la parola "caroline".</span><span class="sxs-lookup"><span data-stu-id="ca69d-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="ca69d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca69d-109">See Also</span></span>  
 [<span data-ttu-id="ca69d-110">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ca69d-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
