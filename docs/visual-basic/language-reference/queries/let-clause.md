---
title: Clausola Let (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70e47517a62f58dcababd31c26277417b62eab66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="53c5b-102">Clausola Let (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53c5b-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="53c5b-103">Calcola un valore e lo assegna a una nuova variabile all'interno della query.</span><span class="sxs-lookup"><span data-stu-id="53c5b-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53c5b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53c5b-104">Syntax</span></span>  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="53c5b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="53c5b-105">Parts</span></span>  
  
|<span data-ttu-id="53c5b-106">Termine</span><span class="sxs-lookup"><span data-stu-id="53c5b-106">Term</span></span>|<span data-ttu-id="53c5b-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="53c5b-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="53c5b-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="53c5b-108">Required.</span></span> <span data-ttu-id="53c5b-109">Un alias che può essere usato per fare riferimento ai risultati dell'espressione fornita.</span><span class="sxs-lookup"><span data-stu-id="53c5b-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="53c5b-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="53c5b-110">Required.</span></span> <span data-ttu-id="53c5b-111">Un'espressione che verrà valutata e assegnata alla variabile specificata.</span><span class="sxs-lookup"><span data-stu-id="53c5b-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53c5b-112">Note</span><span class="sxs-lookup"><span data-stu-id="53c5b-112">Remarks</span></span>  
 <span data-ttu-id="53c5b-113">Il `Let` clausola consente di calcolare valori per ogni risultato della query e farvi riferimento utilizzando un alias.</span><span class="sxs-lookup"><span data-stu-id="53c5b-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="53c5b-114">L'alias può essere utilizzato in altre clausole, ad esempio il `Where` clausola.</span><span class="sxs-lookup"><span data-stu-id="53c5b-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="53c5b-115">Il `Let` clausola consente di creare un'istruzione di query che è facile leggere perché è possibile specificare un alias per una clausola dell'espressione inclusa nella query e sostituire l'alias ogni volta che viene utilizzata la clausola dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="53c5b-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="53c5b-116">È possibile includere un numero qualsiasi di `variable` e `expression` le assegnazioni di `Let` clausola.</span><span class="sxs-lookup"><span data-stu-id="53c5b-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="53c5b-117">Separare ogni assegnazione con una virgola (,).</span><span class="sxs-lookup"><span data-stu-id="53c5b-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53c5b-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="53c5b-118">Example</span></span>  
 <span data-ttu-id="53c5b-119">Nell'esempio di codice viene illustrato come utilizzare il `Let` clausola per calcolare uno sconto del 10% per i prodotti.</span><span class="sxs-lookup"><span data-stu-id="53c5b-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="53c5b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53c5b-120">See Also</span></span>  
 [<span data-ttu-id="53c5b-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53c5b-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="53c5b-122">Query</span><span class="sxs-lookup"><span data-stu-id="53c5b-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="53c5b-123">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="53c5b-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="53c5b-124">Clausola From</span><span class="sxs-lookup"><span data-stu-id="53c5b-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="53c5b-125">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="53c5b-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
