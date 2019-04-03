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
ms.openlocfilehash: fbca9fa8aa227d8d5b6488bef179f4bda08bb38c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830058"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="d961d-102">Clausola Distinct (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d961d-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="d961d-103">Limita i valori della variabile di intervallo corrente per eliminare i valori duplicati nelle clausole di query successiva.</span><span class="sxs-lookup"><span data-stu-id="d961d-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d961d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d961d-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="d961d-105">Note</span><span class="sxs-lookup"><span data-stu-id="d961d-105">Remarks</span></span>  
 <span data-ttu-id="d961d-106">È possibile usare il `Distinct` clausola per restituire un elenco di elementi univoci.</span><span class="sxs-lookup"><span data-stu-id="d961d-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="d961d-107">Il `Distinct` clausola fa sì che la query ignorare i risultati della query duplicate.</span><span class="sxs-lookup"><span data-stu-id="d961d-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="d961d-108">Il `Distinct` clausola viene applicata ai valori duplicati per tutti i campi specificati dalla restituiti il `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="d961d-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="d961d-109">Se nessun `Select` clausola viene specificata, il `Distinct` clausola viene applicata alla variabile di intervallo per la query identificata nel `From` clausola.</span><span class="sxs-lookup"><span data-stu-id="d961d-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="d961d-110">Se la variabile di intervallo non è un tipo non modificabile, la query ignorerà un risultato della query solo se tutti i membri del tipo corrisponde a un risultato di query esistente.</span><span class="sxs-lookup"><span data-stu-id="d961d-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d961d-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d961d-111">Example</span></span>  
 <span data-ttu-id="d961d-112">L'espressione di query seguente viene aggiunto un elenco di clienti e un elenco di ordini dei clienti.</span><span class="sxs-lookup"><span data-stu-id="d961d-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="d961d-113">Il `Distinct` clausola è inclusa per restituire un elenco di nomi di clienti univoci e ordinare le date.</span><span class="sxs-lookup"><span data-stu-id="d961d-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="d961d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d961d-114">See also</span></span>

- [<span data-ttu-id="d961d-115">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d961d-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="d961d-116">Query</span><span class="sxs-lookup"><span data-stu-id="d961d-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="d961d-117">Clausola From</span><span class="sxs-lookup"><span data-stu-id="d961d-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="d961d-118">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="d961d-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="d961d-119">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="d961d-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
