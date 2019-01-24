---
title: Operatore Is (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: a78189a6b82100665ac07b9d7c89590613ec1e1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745623"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="5df58-102">Operatore Is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5df58-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="5df58-103">Confronta due variabili di riferimento di oggetto.</span><span class="sxs-lookup"><span data-stu-id="5df58-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5df58-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5df58-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="5df58-105">Parti</span><span class="sxs-lookup"><span data-stu-id="5df58-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="5df58-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5df58-106">Required.</span></span> <span data-ttu-id="5df58-107">Qualsiasi `Boolean` valore.</span><span class="sxs-lookup"><span data-stu-id="5df58-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="5df58-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5df58-108">Required.</span></span> <span data-ttu-id="5df58-109">Qualsiasi `Object` nome.</span><span class="sxs-lookup"><span data-stu-id="5df58-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="5df58-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5df58-110">Required.</span></span> <span data-ttu-id="5df58-111">Qualsiasi `Object` nome.</span><span class="sxs-lookup"><span data-stu-id="5df58-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5df58-112">Note</span><span class="sxs-lookup"><span data-stu-id="5df58-112">Remarks</span></span>  
 <span data-ttu-id="5df58-113">Il `Is` operatore determina se due riferimenti a oggetti si riferiscono allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="5df58-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="5df58-114">Tuttavia, non esegue confronti di valore.</span><span class="sxs-lookup"><span data-stu-id="5df58-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="5df58-115">Se `object1` e `object2` entrambi la stessa istanza di oggetto, si intende `result` viene `True`; in caso contrario, `result` è `False`.</span><span class="sxs-lookup"><span data-stu-id="5df58-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="5df58-116">`Is` è anche utilizzabile con il `TypeOf` parola chiave per rendere un `TypeOf`... `Is` espressione, che verifica se una variabile oggetto è compatibile con un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="5df58-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5df58-117">Il `Is` parola chiave viene usata anche nel [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5df58-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5df58-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="5df58-118">Example</span></span>  
 <span data-ttu-id="5df58-119">L'esempio seguente usa il `Is` operatore per confrontare coppie di riferimenti a oggetti.</span><span class="sxs-lookup"><span data-stu-id="5df58-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="5df58-120">I risultati vengono assegnati a un `Boolean` valore che indica se i due oggetti sono identici.</span><span class="sxs-lookup"><span data-stu-id="5df58-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 <span data-ttu-id="5df58-121">Come illustrato nell'esempio precedente, è possibile usare il `Is` operatore per eseguire il test sia ad associazione anticipata e gli oggetti ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="5df58-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df58-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5df58-122">See also</span></span>
- [<span data-ttu-id="5df58-123">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="5df58-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="5df58-124">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="5df58-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="5df58-125">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5df58-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="5df58-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5df58-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="5df58-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="5df58-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="5df58-128">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="5df58-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
