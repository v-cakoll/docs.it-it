---
title: Operatore IsNot (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 969fdebdf15a1f779075c58616ccd16c64976a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="a917e-102">Operatore IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a917e-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="a917e-103">Confronta due variabili di riferimento di oggetto.</span><span class="sxs-lookup"><span data-stu-id="a917e-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a917e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a917e-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="a917e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a917e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a917e-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a917e-106">Required.</span></span> <span data-ttu-id="a917e-107">Valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a917e-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="a917e-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a917e-108">Required.</span></span> <span data-ttu-id="a917e-109">Qualsiasi `Object` variabile o espressione.</span><span class="sxs-lookup"><span data-stu-id="a917e-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="a917e-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a917e-110">Required.</span></span> <span data-ttu-id="a917e-111">Qualsiasi `Object` variabile o espressione.</span><span class="sxs-lookup"><span data-stu-id="a917e-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a917e-112">Note</span><span class="sxs-lookup"><span data-stu-id="a917e-112">Remarks</span></span>  
 <span data-ttu-id="a917e-113">Il `IsNot` operatore determina se due riferimenti a oggetti fanno riferimento a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="a917e-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="a917e-114">Tuttavia, non esegue i confronti di valore.</span><span class="sxs-lookup"><span data-stu-id="a917e-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="a917e-115">Se `object1` e `object2` si riferiscono entrambi alla stessa istanza di oggetto, `result` è `False`; in caso contrario, `result` è `True`.</span><span class="sxs-lookup"><span data-stu-id="a917e-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="a917e-116">`IsNot`è l'opposto del `Is` operatore.</span><span class="sxs-lookup"><span data-stu-id="a917e-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="a917e-117">Il vantaggio di `IsNot` è che è possibile evitare la sintassi difficile con `Not` e `Is`, che può essere difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="a917e-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="a917e-118">È possibile utilizzare il `Is` e `IsNot` operatori per testare gli oggetti sia con associazione anticipata e tardiva.</span><span class="sxs-lookup"><span data-stu-id="a917e-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a917e-119">Il `IsNot` operatore non può essere utilizzato per confrontare espressioni restituite dal `TypeOf` operatore.</span><span class="sxs-lookup"><span data-stu-id="a917e-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="a917e-120">In alternativa, è necessario utilizzare il `Not` e `Is` operatori.</span><span class="sxs-lookup"><span data-stu-id="a917e-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a917e-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="a917e-121">Example</span></span>  
 <span data-ttu-id="a917e-122">Esempio di codice seguente utilizza sia il `Is` operatore e `IsNot` operatore per eseguire lo stesso confronto.</span><span class="sxs-lookup"><span data-stu-id="a917e-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a917e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a917e-123">See Also</span></span>  
 [<span data-ttu-id="a917e-124">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="a917e-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="a917e-125">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="a917e-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="a917e-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a917e-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a917e-127">Procedura: Determinare se due oggetti sono uguali</span><span class="sxs-lookup"><span data-stu-id="a917e-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
