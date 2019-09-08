---
title: Determinare se alcuni o tutti gli elementi di una sequenza soddisfano una condizione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: 7de65579cb41641aded0b9a320fac59804959ff5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782224"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a><span data-ttu-id="060eb-102">Determinare se alcuni o tutti gli elementi di una sequenza soddisfano una condizione</span><span class="sxs-lookup"><span data-stu-id="060eb-102">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>
<span data-ttu-id="060eb-103">L'operatore <xref:System.Linq.Enumerable.All%2A> restituisce `true` se tutti gli elementi in una sequenza soddisfanno una condizione.</span><span class="sxs-lookup"><span data-stu-id="060eb-103">The <xref:System.Linq.Enumerable.All%2A> operator returns `true` if all elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="060eb-104">L'operatore <xref:System.Linq.Queryable.Any%2A> restituisce `true` se un elemento qualsiasi in una sequenza soddisfa una condizione.</span><span class="sxs-lookup"><span data-stu-id="060eb-104">The <xref:System.Linq.Queryable.Any%2A> operator returns `true` if any element in a sequence satisfies a condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="060eb-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="060eb-105">Example</span></span>  
 <span data-ttu-id="060eb-106">Nell'esempio seguente viene restituita una sequenza di clienti con almeno un ordine.</span><span class="sxs-lookup"><span data-stu-id="060eb-106">The following example returns a sequence of customers that have at least one order.</span></span> <span data-ttu-id="060eb-107">La `Where` / clausolarestituisce`true` se l'oggetto specificato`Customer` contiene .`Order` `where`</span><span class="sxs-lookup"><span data-stu-id="060eb-107">The `Where`/`where` clause evaluates to `true` if the given `Customer` has any `Order`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="060eb-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="060eb-108">Example</span></span>  
 <span data-ttu-id="060eb-109">Il codice Visual Basic seguente determina l'elenco di clienti che non hanno effettuato ordini e assicura che per ogni cliente nell'elenco venga fornito un nome di contatto.</span><span class="sxs-lookup"><span data-stu-id="060eb-109">The following Visual Basic code determines the list of customers who have not placed orders, and ensures that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a><span data-ttu-id="060eb-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="060eb-110">Example</span></span>  
 <span data-ttu-id="060eb-111">Nell'esempio C# seguente viene restituita una sequenza di clienti i cui ordini contengono un elemento `ShipCity` che inizia con la lettera specificata.</span><span class="sxs-lookup"><span data-stu-id="060eb-111">The following C# example returns a sequence of customers whose orders have a `ShipCity` beginning with "C".</span></span> <span data-ttu-id="060eb-112">Nei risultati vengono restituiti anche i clienti che non hanno effettuato ordini.</span><span class="sxs-lookup"><span data-stu-id="060eb-112">Also included in the return are customers who have no orders.</span></span> <span data-ttu-id="060eb-113">In base alla progettazione, l'operatore <xref:System.Linq.Queryable.All%2A> restituisce `true` per una sequenza vuota. I clienti senza ordini vengono eliminati nell'output della console usando l'operatore `Count`.</span><span class="sxs-lookup"><span data-stu-id="060eb-113">(By design, the <xref:System.Linq.Queryable.All%2A> operator returns `true` for an empty sequence.) Customers with no orders are eliminated in the console output by using the `Count` operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="060eb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="060eb-114">See also</span></span>

- [<span data-ttu-id="060eb-115">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="060eb-115">Query Examples</span></span>](query-examples.md)
