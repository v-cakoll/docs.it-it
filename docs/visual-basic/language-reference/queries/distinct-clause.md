---
title: Clausola Distinct
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 5aecffbce036500d294d03a925798d51f1269af6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401394"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="4bbb1-102">Clausola Distinct (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bbb1-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="4bbb1-103">Limita i valori della variabile di intervallo corrente per eliminare i valori duplicati nelle clausole di query successive.</span><span class="sxs-lookup"><span data-stu-id="4bbb1-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bbb1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4bbb1-104">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="4bbb1-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4bbb1-105">Remarks</span></span>  
 <span data-ttu-id="4bbb1-106">È possibile utilizzare la `Distinct` clausola per restituire un elenco di elementi univoci.</span><span class="sxs-lookup"><span data-stu-id="4bbb1-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="4bbb1-107">La `Distinct` clausola fa in modo che la query ignori i risultati di query duplicati.</span><span class="sxs-lookup"><span data-stu-id="4bbb1-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="4bbb1-108">La `Distinct` clausola si applica ai valori duplicati per tutti i campi restituiti specificati dalla `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="4bbb1-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="4bbb1-109">Se non `Select` viene specificata alcuna clausola, la `Distinct` clausola viene applicata alla variabile di intervallo per la query identificata nella `From` clausola.</span><span class="sxs-lookup"><span data-stu-id="4bbb1-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="4bbb1-110">Se la variabile di intervallo non è un tipo non modificabile, la query ignorerà solo il risultato di una query se tutti i membri del tipo corrispondono a un risultato della query esistente.</span><span class="sxs-lookup"><span data-stu-id="4bbb1-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bbb1-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="4bbb1-111">Example</span></span>  
 <span data-ttu-id="4bbb1-112">L'espressione di query seguente unisce un elenco di clienti e un elenco di ordini dei clienti.</span><span class="sxs-lookup"><span data-stu-id="4bbb1-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="4bbb1-113">La `Distinct` clausola viene inclusa per restituire un elenco di nomi di clienti e date degli ordini univoci.</span><span class="sxs-lookup"><span data-stu-id="4bbb1-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="4bbb1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bbb1-114">See also</span></span>

- [<span data-ttu-id="4bbb1-115">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4bbb1-115">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="4bbb1-116">Query</span><span class="sxs-lookup"><span data-stu-id="4bbb1-116">Queries</span></span>](index.md)
- [<span data-ttu-id="4bbb1-117">Clausola from</span><span class="sxs-lookup"><span data-stu-id="4bbb1-117">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="4bbb1-118">Clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="4bbb1-118">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="4bbb1-119">Clausola WHERE</span><span class="sxs-lookup"><span data-stu-id="4bbb1-119">Where Clause</span></span>](where-clause.md)
