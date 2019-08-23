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
ms.openlocfilehash: a5481a9bce01e84ce4f078335c8cd15a747a3c51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917210"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="fef4d-102">Operatore Is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fef4d-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="fef4d-103">Confronta due variabili di riferimento a oggetti.</span><span class="sxs-lookup"><span data-stu-id="fef4d-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fef4d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fef4d-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="fef4d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="fef4d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="fef4d-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="fef4d-106">Required.</span></span> <span data-ttu-id="fef4d-107">Qualsiasi `Boolean` valore.</span><span class="sxs-lookup"><span data-stu-id="fef4d-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="fef4d-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="fef4d-108">Required.</span></span> <span data-ttu-id="fef4d-109">Qualsiasi `Object` nome.</span><span class="sxs-lookup"><span data-stu-id="fef4d-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="fef4d-110">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="fef4d-110">Required.</span></span> <span data-ttu-id="fef4d-111">Qualsiasi `Object` nome.</span><span class="sxs-lookup"><span data-stu-id="fef4d-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fef4d-112">Note</span><span class="sxs-lookup"><span data-stu-id="fef4d-112">Remarks</span></span>  
 <span data-ttu-id="fef4d-113">L' `Is` operatore determina se due riferimenti a oggetti si riferiscono allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="fef4d-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="fef4d-114">Tuttavia, non esegue confronti di valori.</span><span class="sxs-lookup"><span data-stu-id="fef4d-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="fef4d-115">Se `object1` ed `True` `result` `result` `False`entrambi fanno riferimento alla stessa istanza dell'oggetto, è; in caso contrario, è. `object2`</span><span class="sxs-lookup"><span data-stu-id="fef4d-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="fef4d-116">`Is`può essere usato anche con la `TypeOf` parola chiave per creare `TypeOf`un... `Is` espressione, che verifica se una variabile oggetto è compatibile con un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="fef4d-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fef4d-117">La `Is` parola chiave viene inoltre utilizzata nell'oggetto [Select... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fef4d-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fef4d-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="fef4d-118">Example</span></span>  
 <span data-ttu-id="fef4d-119">Nell'esempio seguente viene usato `Is` l'operatore per confrontare coppie di riferimenti a oggetti.</span><span class="sxs-lookup"><span data-stu-id="fef4d-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="fef4d-120">I risultati vengono assegnati a un `Boolean` valore che indica se i due oggetti sono identici.</span><span class="sxs-lookup"><span data-stu-id="fef4d-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="fef4d-121">Come illustrato nell'esempio precedente, è possibile usare l' `Is` operatore per testare gli oggetti ad associazione anticipata e ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="fef4d-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef4d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fef4d-122">See also</span></span>

- [<span data-ttu-id="fef4d-123">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="fef4d-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="fef4d-124">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="fef4d-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="fef4d-125">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fef4d-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="fef4d-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fef4d-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fef4d-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="fef4d-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fef4d-128">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="fef4d-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
