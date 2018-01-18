---
title: Restituire l'unione di set di due sequenze
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
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 24a3c7e7ee33d616afdbc9651850c10716a0547c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="08cd4-102">Restituire l'unione di set di due sequenze</span><span class="sxs-lookup"><span data-stu-id="08cd4-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="08cd4-103">Per restituire l'unione di set di due sequenze, usare l'operatore <xref:System.Linq.Queryable.Union%2A>.</span><span class="sxs-lookup"><span data-stu-id="08cd4-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08cd4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="08cd4-104">Example</span></span>  
 <span data-ttu-id="08cd4-105">In questo esempio viene usato <xref:System.Linq.Queryable.Union%2A> per restituire una sequenza di tutti i paesi in cui sono presenti `Customers` o `Employees`.</span><span class="sxs-lookup"><span data-stu-id="08cd4-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="08cd4-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> è definito per i tipi multiset come concatenazione non ordinata di multiset, che corrisponde (in modo efficace il risultato del `UNION ALL` clausola in SQL).</span><span class="sxs-lookup"><span data-stu-id="08cd4-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the `UNION ALL` clause in SQL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08cd4-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08cd4-107">See Also</span></span>  
 [<span data-ttu-id="08cd4-108">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="08cd4-108">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="08cd4-109">Conversione dell'operatore query standard</span><span class="sxs-lookup"><span data-stu-id="08cd4-109">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
