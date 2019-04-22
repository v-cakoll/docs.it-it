---
title: Operatore IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: e07a775eec003a3e488f6909181aed3f742b4b91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833516"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="a22e1-102">Operatore IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a22e1-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="a22e1-103">Confronta due variabili di riferimento di oggetto.</span><span class="sxs-lookup"><span data-stu-id="a22e1-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a22e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a22e1-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="a22e1-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a22e1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a22e1-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a22e1-106">Required.</span></span> <span data-ttu-id="a22e1-107">Valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a22e1-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="a22e1-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a22e1-108">Required.</span></span> <span data-ttu-id="a22e1-109">Qualsiasi `Object` variabile o espressione.</span><span class="sxs-lookup"><span data-stu-id="a22e1-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="a22e1-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a22e1-110">Required.</span></span> <span data-ttu-id="a22e1-111">Qualsiasi `Object` variabile o espressione.</span><span class="sxs-lookup"><span data-stu-id="a22e1-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a22e1-112">Note</span><span class="sxs-lookup"><span data-stu-id="a22e1-112">Remarks</span></span>  
 <span data-ttu-id="a22e1-113">Il `IsNot` operatore determina se due riferimenti a oggetti si riferiscono a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="a22e1-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="a22e1-114">Tuttavia, non esegue confronti di valore.</span><span class="sxs-lookup"><span data-stu-id="a22e1-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="a22e1-115">Se `object1` e `object2` entrambi la stessa istanza di oggetto, si intende `result` viene `False`; in caso contrario, `result` è `True`.</span><span class="sxs-lookup"><span data-stu-id="a22e1-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="a22e1-116">`IsNot` è l'opposto del `Is` operatore.</span><span class="sxs-lookup"><span data-stu-id="a22e1-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="a22e1-117">Il vantaggio `IsNot` è che è possibile evitare sintassi difficile `Not` e `Is`, che può essere difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="a22e1-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="a22e1-118">È possibile usare la `Is` e `IsNot` operatori per testare gli oggetti ad associazione anticipata e tardiva.</span><span class="sxs-lookup"><span data-stu-id="a22e1-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a22e1-119">Il `IsNot` operatore non può essere utilizzato per confrontare espressioni restituite dal `TypeOf` operatore.</span><span class="sxs-lookup"><span data-stu-id="a22e1-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="a22e1-120">In alternativa, è necessario usare il `Not` e `Is` operatori.</span><span class="sxs-lookup"><span data-stu-id="a22e1-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a22e1-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="a22e1-121">Example</span></span>  
 <span data-ttu-id="a22e1-122">Esempio di codice seguente usa sia la `Is` operatore e `IsNot` operatore per eseguire lo stesso confronto.</span><span class="sxs-lookup"><span data-stu-id="a22e1-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="a22e1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a22e1-123">See also</span></span>

- [<span data-ttu-id="a22e1-124">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="a22e1-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="a22e1-125">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="a22e1-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="a22e1-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a22e1-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a22e1-127">Procedura: Verificare se due oggetti sono uguali.</span><span class="sxs-lookup"><span data-stu-id="a22e1-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
