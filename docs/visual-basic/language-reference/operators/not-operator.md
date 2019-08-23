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
ms.openlocfilehash: 29e2b159e4c6261a62e788b537102b9b457fe0c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955828"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="8d2df-102">Operatore Not (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d2df-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="8d2df-103">Esegue una negazione logica su `Boolean` un'espressione o una negazione bit per bit su un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="8d2df-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d2df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d2df-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="8d2df-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8d2df-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="8d2df-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="8d2df-106">Required.</span></span> <span data-ttu-id="8d2df-107">Espressione `Boolean` qualsiasi o numerica.</span><span class="sxs-lookup"><span data-stu-id="8d2df-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="8d2df-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="8d2df-108">Required.</span></span> <span data-ttu-id="8d2df-109">Espressione `Boolean` qualsiasi o numerica.</span><span class="sxs-lookup"><span data-stu-id="8d2df-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d2df-110">Note</span><span class="sxs-lookup"><span data-stu-id="8d2df-110">Remarks</span></span>  
 <span data-ttu-id="8d2df-111">Per `Boolean` le espressioni, nella tabella seguente viene illustrato `result` il modo in cui viene determinato.</span><span class="sxs-lookup"><span data-stu-id="8d2df-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="8d2df-112">Se `expression` è</span><span class="sxs-lookup"><span data-stu-id="8d2df-112">If `expression` is</span></span>|<span data-ttu-id="8d2df-113">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="8d2df-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="8d2df-114">Per le espressioni numeriche `Not` , l'operatore inverte i valori di bit di qualsiasi espressione numerica e imposta il `result` bit corrispondente in in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8d2df-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="8d2df-115">Se il bit `expression` in è</span><span class="sxs-lookup"><span data-stu-id="8d2df-115">If bit in `expression` is</span></span>|<span data-ttu-id="8d2df-116">Il bit in `result` è</span><span class="sxs-lookup"><span data-stu-id="8d2df-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="8d2df-117">1</span><span class="sxs-lookup"><span data-stu-id="8d2df-117">1</span></span>|<span data-ttu-id="8d2df-118">0</span><span class="sxs-lookup"><span data-stu-id="8d2df-118">0</span></span>|  
|<span data-ttu-id="8d2df-119">0</span><span class="sxs-lookup"><span data-stu-id="8d2df-119">0</span></span>|<span data-ttu-id="8d2df-120">1</span><span class="sxs-lookup"><span data-stu-id="8d2df-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="8d2df-121">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire un'esecuzione accurata.</span><span class="sxs-lookup"><span data-stu-id="8d2df-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="8d2df-122">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="8d2df-122">Data Types</span></span>  
 <span data-ttu-id="8d2df-123">Per una negazione booleana, il tipo di dati del risultato `Boolean`è.</span><span class="sxs-lookup"><span data-stu-id="8d2df-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="8d2df-124">Per una negazione bit per bit, il tipo di dati del risultato è identico a quello di `expression`.</span><span class="sxs-lookup"><span data-stu-id="8d2df-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="8d2df-125">Tuttavia, se Expression è `Decimal`, il risultato è `Long`.</span><span class="sxs-lookup"><span data-stu-id="8d2df-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8d2df-126">Overload</span><span class="sxs-lookup"><span data-stu-id="8d2df-126">Overloading</span></span>  
 <span data-ttu-id="8d2df-127">L' `Not` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="8d2df-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="8d2df-128">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="8d2df-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8d2df-129">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8d2df-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d2df-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d2df-130">Example</span></span>  
 <span data-ttu-id="8d2df-131">Nell'esempio seguente viene usato `Not` l'operatore per eseguire la negazione logica `Boolean` su un'espressione.</span><span class="sxs-lookup"><span data-stu-id="8d2df-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="8d2df-132">Il risultato è un `Boolean` valore che rappresenta l'inverso del valore dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="8d2df-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="8d2df-133">Nell'esempio precedente vengono restituiti i `False` risultati `True`di e, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="8d2df-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d2df-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d2df-134">Example</span></span>  
 <span data-ttu-id="8d2df-135">Nell'esempio seguente viene usato `Not` l'operatore per eseguire la negazione logica dei singoli bit di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="8d2df-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="8d2df-136">Il bit nel modello di risultato viene impostato sul contrario del bit corrispondente nel modello di operando, incluso il bit di segno.</span><span class="sxs-lookup"><span data-stu-id="8d2df-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="8d2df-137">Nell'esempio precedente vengono restituiti rispettivamente i risultati di – 11, – 9 e-7.</span><span class="sxs-lookup"><span data-stu-id="8d2df-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d2df-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d2df-138">See also</span></span>

- [<span data-ttu-id="8d2df-139">Operatori logici/bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d2df-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="8d2df-140">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8d2df-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8d2df-141">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="8d2df-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8d2df-142">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8d2df-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
