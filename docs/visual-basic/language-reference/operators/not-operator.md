---
title: Operatore Not (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: cd93316ada1fcf0997922f71a8efc5a3cf411d09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614579"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="ffed1-102">Operatore Not (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffed1-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="ffed1-103">Esegue una negazione logica su un `Boolean` espressione oppure una negazione bit per bit di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="ffed1-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffed1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ffed1-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ffed1-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ffed1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="ffed1-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ffed1-106">Required.</span></span> <span data-ttu-id="ffed1-107">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="ffed1-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="ffed1-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ffed1-108">Required.</span></span> <span data-ttu-id="ffed1-109">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="ffed1-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffed1-110">Note</span><span class="sxs-lookup"><span data-stu-id="ffed1-110">Remarks</span></span>  
 <span data-ttu-id="ffed1-111">Per la `Boolean` espressioni, la tabella seguente illustra come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="ffed1-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="ffed1-112">Se `expression` è</span><span class="sxs-lookup"><span data-stu-id="ffed1-112">If `expression` is</span></span>|<span data-ttu-id="ffed1-113">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="ffed1-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="ffed1-114">Per le espressioni numeriche, il `Not` operatore inverte i valori di bit di qualsiasi espressione numerica e imposta il bit nel corrispondente `result` in base alla tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="ffed1-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="ffed1-115">Se in bit in `expression` è</span><span class="sxs-lookup"><span data-stu-id="ffed1-115">If bit in `expression` is</span></span>|<span data-ttu-id="ffed1-116">Il bit nel `result` è</span><span class="sxs-lookup"><span data-stu-id="ffed1-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="ffed1-117">1</span><span class="sxs-lookup"><span data-stu-id="ffed1-117">1</span></span>|<span data-ttu-id="ffed1-118">0</span><span class="sxs-lookup"><span data-stu-id="ffed1-118">0</span></span>|  
|<span data-ttu-id="ffed1-119">0</span><span class="sxs-lookup"><span data-stu-id="ffed1-119">0</span></span>|<span data-ttu-id="ffed1-120">1</span><span class="sxs-lookup"><span data-stu-id="ffed1-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ffed1-121">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiusi tra parentesi per garantire un'esecuzione accurata.</span><span class="sxs-lookup"><span data-stu-id="ffed1-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="ffed1-122">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="ffed1-122">Data Types</span></span>  
 <span data-ttu-id="ffed1-123">Per una negazione booleana, il tipo di dati del risultato è `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="ffed1-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="ffed1-124">Per una negazione bit per bit, il tipo di dati del risultato è uguale a quello di `expression`.</span><span class="sxs-lookup"><span data-stu-id="ffed1-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="ffed1-125">Tuttavia, se espressione è `Decimal`, il risultato è `Long`.</span><span class="sxs-lookup"><span data-stu-id="ffed1-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ffed1-126">Overload</span><span class="sxs-lookup"><span data-stu-id="ffed1-126">Overloading</span></span>  
 <span data-ttu-id="ffed1-127">Il `Not` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando l'operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="ffed1-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="ffed1-128">Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="ffed1-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ffed1-129">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ffed1-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffed1-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="ffed1-130">Example</span></span>  
 <span data-ttu-id="ffed1-131">L'esempio seguente usa il `Not` operatore per eseguire la negazione logica su un `Boolean` espressione.</span><span class="sxs-lookup"><span data-stu-id="ffed1-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="ffed1-132">Il risultato è un `Boolean` valore che rappresenta l'opposto del valore dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="ffed1-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 <span data-ttu-id="ffed1-133">Nell'esempio precedente produce i risultati dei `False` e `True`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="ffed1-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffed1-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="ffed1-134">Example</span></span>  
 <span data-ttu-id="ffed1-135">L'esempio seguente usa il `Not` operatore per eseguire la negazione logica dei singoli bit di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="ffed1-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="ffed1-136">Il bit nel risultato viene impostato per l'operazione inversa del bit corrispondente nel modello dell'operando, tra cui il bit di segno.</span><span class="sxs-lookup"><span data-stu-id="ffed1-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 <span data-ttu-id="ffed1-137">Nell'esempio precedente produce i risultati di – 11, –9 e –7, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="ffed1-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffed1-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffed1-138">See also</span></span>
- [<span data-ttu-id="ffed1-139">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffed1-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="ffed1-140">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ffed1-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ffed1-141">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="ffed1-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ffed1-142">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ffed1-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
