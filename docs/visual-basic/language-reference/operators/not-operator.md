---
title: Operatore Not (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Not
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac160aef7b7dc8acb8bf0211b403599692f2373c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="b5655-102">Operatore Not (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5655-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="b5655-103">Esegue una negazione logica su un `Boolean` espressione oppure una negazione bit per bit su un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="b5655-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5655-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5655-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b5655-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b5655-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b5655-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b5655-106">Required.</span></span> <span data-ttu-id="b5655-107">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="b5655-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="b5655-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b5655-108">Required.</span></span> <span data-ttu-id="b5655-109">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="b5655-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5655-110">Note</span><span class="sxs-lookup"><span data-stu-id="b5655-110">Remarks</span></span>  
 <span data-ttu-id="b5655-111">Per `Boolean` espressioni, la tabella seguente illustra come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="b5655-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="b5655-112">Se `expression` è</span><span class="sxs-lookup"><span data-stu-id="b5655-112">If `expression` is</span></span>|<span data-ttu-id="b5655-113">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="b5655-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="b5655-114">Le espressioni numeriche, di `Not` operatore inverte i valori di bit di qualsiasi espressione numerica e imposta il bit nel corrispondente `result` in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b5655-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="b5655-115">Se in bit in `expression` è</span><span class="sxs-lookup"><span data-stu-id="b5655-115">If bit in `expression` is</span></span>|<span data-ttu-id="b5655-116">Il bit `result` è</span><span class="sxs-lookup"><span data-stu-id="b5655-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="b5655-117">1</span><span class="sxs-lookup"><span data-stu-id="b5655-117">1</span></span>|<span data-ttu-id="b5655-118">0</span><span class="sxs-lookup"><span data-stu-id="b5655-118">0</span></span>|  
|<span data-ttu-id="b5655-119">0</span><span class="sxs-lookup"><span data-stu-id="b5655-119">0</span></span>|<span data-ttu-id="b5655-120">1</span><span class="sxs-lookup"><span data-stu-id="b5655-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b5655-121">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiuse tra parentesi per garantire un'esecuzione accurata.</span><span class="sxs-lookup"><span data-stu-id="b5655-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="b5655-122">Riepilogo dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="b5655-122">Data Types</span></span>  
 <span data-ttu-id="b5655-123">Per una negazione booleana, il tipo di dati del risultato è `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b5655-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="b5655-124">Per una negazione bit per bit, il tipo di dati del risultato è uguale a quello di `expression`.</span><span class="sxs-lookup"><span data-stu-id="b5655-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="b5655-125">Tuttavia, se l'espressione è `Decimal`, il risultato è `Long`.</span><span class="sxs-lookup"><span data-stu-id="b5655-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b5655-126">Overload</span><span class="sxs-lookup"><span data-stu-id="b5655-126">Overloading</span></span>  
 <span data-ttu-id="b5655-127">Il `Not` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando l'operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b5655-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="b5655-128">Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="b5655-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b5655-129">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b5655-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5655-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5655-130">Example</span></span>  
 <span data-ttu-id="b5655-131">L'esempio seguente usa il `Not` operatore per eseguire la negazione logica su un `Boolean` espressione.</span><span class="sxs-lookup"><span data-stu-id="b5655-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="b5655-132">Il risultato è un `Boolean` valore che rappresenta l'opposto del valore dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="b5655-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 <span data-ttu-id="b5655-133">Nell'esempio precedente produce i risultati di `False` e `True`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="b5655-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5655-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5655-134">Example</span></span>  
 <span data-ttu-id="b5655-135">L'esempio seguente usa il `Not` operatore per eseguire la negazione logica dei singoli bit di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="b5655-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="b5655-136">Il bit nel risultato viene impostato per l'operazione inversa del bit corrispondente nel modello dell'operando, compreso il bit di segno.</span><span class="sxs-lookup"><span data-stu-id="b5655-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 <span data-ttu-id="b5655-137">Nell'esempio precedente produce risultati di – 11 – 9 e –7, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="b5655-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5655-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5655-138">See Also</span></span>  
 [<span data-ttu-id="b5655-139">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5655-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="b5655-140">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5655-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="b5655-141">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="b5655-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="b5655-142">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5655-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
