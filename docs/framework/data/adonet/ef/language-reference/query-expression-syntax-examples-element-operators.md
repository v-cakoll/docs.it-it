---
title: 'Esempi di sintassi di espressione di query: operatori di elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 846344bf5e8005473fe7db8217228cd33179a206
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="34630-102">Esempi di sintassi di espressione di query: operatori di elemento</span><span class="sxs-lookup"><span data-stu-id="34630-102">Query Expression Syntax Examples: Element Operators</span></span>
<span data-ttu-id="34630-103">Negli esempi in questo argomento viene illustrato come utilizzare il <xref:System.Linq.Enumerable.First%2A> metodo per eseguire query di [modello Sales di AdventureWorks](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) utilizzando la sintassi di espressione di query.</span><span class="sxs-lookup"><span data-stu-id="34630-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using the query expression syntax.</span></span> <span data-ttu-id="34630-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="34630-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="34630-105">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="34630-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="34630-106">First</span><span class="sxs-lookup"><span data-stu-id="34630-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="34630-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="34630-107">Example</span></span>  
 <span data-ttu-id="34630-108">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.First%2A> per restituire il primo contatto il cui nome è "Brooke".</span><span class="sxs-lookup"><span data-stu-id="34630-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="34630-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34630-109">See Also</span></span>  
 [<span data-ttu-id="34630-110">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="34630-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
