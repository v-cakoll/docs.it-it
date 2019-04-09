---
title: Concatenare due sequenze
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
ms.openlocfilehash: a2f2510cb334f4e22a7b0c6015a0a93b4dc11579
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142779"
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="aa526-102">Concatenare due sequenze</span><span class="sxs-lookup"><span data-stu-id="aa526-102">Concatenate Two Sequences</span></span>
<span data-ttu-id="aa526-103">Usare l'operatore <xref:System.Linq.Queryable.Concat%2A> per concatenare due sequenze.</span><span class="sxs-lookup"><span data-stu-id="aa526-103">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="aa526-104">L'operatore <xref:System.Linq.Queryable.Concat%2A> viene definito per multiset ordinati in cui gli ordini del ricevente e dell'argomento sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="aa526-104">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="aa526-105">L'ordinamento in SQL è il passaggio finale prima della generazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="aa526-105">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="aa526-106">Per questo motivo l'operatore <xref:System.Linq.Queryable.Concat%2A> viene implementato usando `UNION ALL` e non mantiene l'ordine dei relativi argomenti.</span><span class="sxs-lookup"><span data-stu-id="aa526-106">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="aa526-107">Per essere certi che l'ordine nei risultati sia corretto, ordinarli in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="aa526-107">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa526-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa526-108">Example</span></span>  
 <span data-ttu-id="aa526-109">In questo esempio viene usato <xref:System.Linq.Queryable.Concat%2A> per restituire una sequenza di tutti i numeri di telefono e di fax relativi a `Customer` e `Employee`.</span><span class="sxs-lookup"><span data-stu-id="aa526-109">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="aa526-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa526-110">Example</span></span>  
 <span data-ttu-id="aa526-111">In questo esempio viene usato <xref:System.Linq.Queryable.Concat%2A> per restituire una sequenza di tutti i mapping di nomi e numeri di telefono relativi a `Customer` e `Employee`.</span><span class="sxs-lookup"><span data-stu-id="aa526-111">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="aa526-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa526-112">See also</span></span>

- [<span data-ttu-id="aa526-113">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="aa526-113">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="aa526-114">Conversione dell'operatore query standard</span><span class="sxs-lookup"><span data-stu-id="aa526-114">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
