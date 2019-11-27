---
title: Clausola Let
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 63eaf97016db259870eb77199651ecbdc5f809c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350440"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="c2845-102">Clausola Let (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2845-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="c2845-103">Calcola un valore e lo assegna a una nuova variabile all'interno della query.</span><span class="sxs-lookup"><span data-stu-id="c2845-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2845-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2845-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="c2845-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c2845-105">Parts</span></span>  
  
|<span data-ttu-id="c2845-106">Termine</span><span class="sxs-lookup"><span data-stu-id="c2845-106">Term</span></span>|<span data-ttu-id="c2845-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="c2845-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="c2845-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="c2845-108">Required.</span></span> <span data-ttu-id="c2845-109">Alias che può essere utilizzato per fare riferimento ai risultati dell'espressione fornita.</span><span class="sxs-lookup"><span data-stu-id="c2845-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="c2845-110">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="c2845-110">Required.</span></span> <span data-ttu-id="c2845-111">Espressione che verrà valutata e assegnata alla variabile specificata.</span><span class="sxs-lookup"><span data-stu-id="c2845-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2845-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c2845-112">Remarks</span></span>  
 <span data-ttu-id="c2845-113">La clausola `Let` consente di calcolare i valori per ogni risultato della query e di farvi riferimento tramite un alias.</span><span class="sxs-lookup"><span data-stu-id="c2845-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="c2845-114">L'alias può essere utilizzato in altre clausole, ad esempio la clausola `Where`.</span><span class="sxs-lookup"><span data-stu-id="c2845-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="c2845-115">La clausola `Let` consente di creare un'istruzione di query più semplice da leggere, in quanto è possibile specificare un alias per una clausola Expression inclusa nella query e sostituire l'alias ogni volta che viene utilizzata la clausola Expression.</span><span class="sxs-lookup"><span data-stu-id="c2845-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="c2845-116">Nella clausola `Let` è possibile includere un numero qualsiasi di assegnazioni di `variable` e di `expression`.</span><span class="sxs-lookup"><span data-stu-id="c2845-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="c2845-117">Separare ogni assegnazione con una virgola (,).</span><span class="sxs-lookup"><span data-stu-id="c2845-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2845-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="c2845-118">Example</span></span>  
 <span data-ttu-id="c2845-119">Nell'esempio di codice seguente viene usata la clausola `Let` per calcolare uno sconto del 10% sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="c2845-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="c2845-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2845-120">See also</span></span>

- [<span data-ttu-id="c2845-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c2845-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="c2845-122">Query</span><span class="sxs-lookup"><span data-stu-id="c2845-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="c2845-123">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="c2845-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="c2845-124">Clausola From</span><span class="sxs-lookup"><span data-stu-id="c2845-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="c2845-125">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="c2845-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
