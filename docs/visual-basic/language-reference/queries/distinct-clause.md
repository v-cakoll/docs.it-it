---
title: Clausola Distinct (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 00a2e52bd6669869bb2e25bc2857f1598da5763f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971247"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="99e53-102">Clausola Distinct (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99e53-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="99e53-103">Limita i valori della variabile di intervallo corrente per eliminare i valori duplicati nelle clausole di query successiva.</span><span class="sxs-lookup"><span data-stu-id="99e53-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e53-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99e53-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="99e53-105">Note</span><span class="sxs-lookup"><span data-stu-id="99e53-105">Remarks</span></span>  
 <span data-ttu-id="99e53-106">È possibile usare il `Distinct` clausola per restituire un elenco di elementi univoci.</span><span class="sxs-lookup"><span data-stu-id="99e53-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="99e53-107">Il `Distinct` clausola fa sì che la query ignorare i risultati della query duplicate.</span><span class="sxs-lookup"><span data-stu-id="99e53-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="99e53-108">Il `Distinct` clausola viene applicata ai valori duplicati per tutti i campi specificati dalla restituiti il `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="99e53-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="99e53-109">Se nessun `Select` clausola viene specificata, il `Distinct` clausola viene applicata alla variabile di intervallo per la query identificata nel `From` clausola.</span><span class="sxs-lookup"><span data-stu-id="99e53-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="99e53-110">Se la variabile di intervallo non è un tipo non modificabile, la query ignorerà un risultato della query solo se tutti i membri del tipo corrisponde a un risultato di query esistente.</span><span class="sxs-lookup"><span data-stu-id="99e53-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99e53-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="99e53-111">Example</span></span>  
 <span data-ttu-id="99e53-112">L'espressione di query seguente viene aggiunto un elenco di clienti e un elenco di ordini dei clienti.</span><span class="sxs-lookup"><span data-stu-id="99e53-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="99e53-113">Il `Distinct` clausola è inclusa per restituire un elenco di nomi di clienti univoci e ordinare le date.</span><span class="sxs-lookup"><span data-stu-id="99e53-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="99e53-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99e53-114">See also</span></span>
- [<span data-ttu-id="99e53-115">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="99e53-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="99e53-116">Query</span><span class="sxs-lookup"><span data-stu-id="99e53-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="99e53-117">Clausola From</span><span class="sxs-lookup"><span data-stu-id="99e53-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="99e53-118">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="99e53-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="99e53-119">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="99e53-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
