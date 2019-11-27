---
title: Operatore Is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 52fbb39ab0a36c8b947b78f464fad26be05ce204
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349539"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="d337b-102">Operatore Is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d337b-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="d337b-103">Confronta due variabili di riferimento a oggetti.</span><span class="sxs-lookup"><span data-stu-id="d337b-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d337b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d337b-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="d337b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d337b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="d337b-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="d337b-106">Required.</span></span> <span data-ttu-id="d337b-107">Qualsiasi valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="d337b-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="d337b-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="d337b-108">Required.</span></span> <span data-ttu-id="d337b-109">Qualsiasi nome del `Object`.</span><span class="sxs-lookup"><span data-stu-id="d337b-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="d337b-110">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="d337b-110">Required.</span></span> <span data-ttu-id="d337b-111">Qualsiasi nome del `Object`.</span><span class="sxs-lookup"><span data-stu-id="d337b-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d337b-112">Note</span><span class="sxs-lookup"><span data-stu-id="d337b-112">Remarks</span></span>  
 <span data-ttu-id="d337b-113">L'operatore `Is` determina se due riferimenti a oggetti si riferiscono allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="d337b-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="d337b-114">Tuttavia, non esegue confronti di valori.</span><span class="sxs-lookup"><span data-stu-id="d337b-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="d337b-115">Se `object1` e `object2` entrambi fanno riferimento alla stessa istanza dell'oggetto, `result` è `True`; in caso contrario, `result` viene `False`.</span><span class="sxs-lookup"><span data-stu-id="d337b-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="d337b-116">`Is` possibile utilizzare anche con la parola chiave `TypeOf` per creare un'espressione `TypeOf`...`Is`, che verifica se una variabile oggetto è compatibile con un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d337b-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d337b-117">La parola chiave `Is` viene inoltre utilizzata nell'oggetto [Select... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d337b-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d337b-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="d337b-118">Example</span></span>  
 <span data-ttu-id="d337b-119">Nell'esempio seguente viene usato l'operatore `Is` per confrontare coppie di riferimenti a oggetti.</span><span class="sxs-lookup"><span data-stu-id="d337b-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="d337b-120">I risultati vengono assegnati a un valore `Boolean` che indica se i due oggetti sono identici.</span><span class="sxs-lookup"><span data-stu-id="d337b-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="d337b-121">Come illustrato nell'esempio precedente, è possibile usare l'operatore `Is` per testare gli oggetti ad associazione anticipata e ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="d337b-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d337b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d337b-122">See also</span></span>

- [<span data-ttu-id="d337b-123">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="d337b-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="d337b-124">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="d337b-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="d337b-125">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d337b-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="d337b-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d337b-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d337b-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="d337b-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d337b-128">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="d337b-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
