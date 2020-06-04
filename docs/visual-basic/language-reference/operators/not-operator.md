---
title: Operatore Not
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
ms.openlocfilehash: 56cdeb80a217dbce15921eddd6a43d8d1b049376
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401459"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="0ecdb-102">Operatore Not (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ecdb-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="0ecdb-103">Esegue una negazione logica su un' `Boolean` espressione o una negazione bit per bit su un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ecdb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ecdb-104">Syntax</span></span>  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="0ecdb-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0ecdb-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="0ecdb-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-106">Required.</span></span> <span data-ttu-id="0ecdb-107">Qualsiasi espressione `Boolean` o numerica.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="0ecdb-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-108">Required.</span></span> <span data-ttu-id="0ecdb-109">Qualsiasi espressione `Boolean` o numerica.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ecdb-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="0ecdb-110">Remarks</span></span>  
 <span data-ttu-id="0ecdb-111">Per `Boolean` le espressioni, nella tabella seguente viene illustrato il modo in cui `result` viene determinato.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="0ecdb-112">Se `expression` è </span><span class="sxs-lookup"><span data-stu-id="0ecdb-112">If `expression` is</span></span>|<span data-ttu-id="0ecdb-113">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="0ecdb-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="0ecdb-114">Per le espressioni numeriche, l' `Not` operatore inverte i valori di bit di qualsiasi espressione numerica e imposta il bit corrispondente in in `result` base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="0ecdb-115">Se il bit in `expression` è</span><span class="sxs-lookup"><span data-stu-id="0ecdb-115">If bit in `expression` is</span></span>|<span data-ttu-id="0ecdb-116">Il bit in `result` è</span><span class="sxs-lookup"><span data-stu-id="0ecdb-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="0ecdb-117">1</span><span class="sxs-lookup"><span data-stu-id="0ecdb-117">1</span></span>|<span data-ttu-id="0ecdb-118">0</span><span class="sxs-lookup"><span data-stu-id="0ecdb-118">0</span></span>|  
|<span data-ttu-id="0ecdb-119">0</span><span class="sxs-lookup"><span data-stu-id="0ecdb-119">0</span></span>|<span data-ttu-id="0ecdb-120">1</span><span class="sxs-lookup"><span data-stu-id="0ecdb-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="0ecdb-121">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire un'esecuzione accurata.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="0ecdb-122">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0ecdb-122">Data Types</span></span>  
 <span data-ttu-id="0ecdb-123">Per una negazione booleana, il tipo di dati del risultato è `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="0ecdb-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="0ecdb-124">Per una negazione bit per bit, il tipo di dati del risultato è identico a quello di `expression` .</span><span class="sxs-lookup"><span data-stu-id="0ecdb-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="0ecdb-125">Tuttavia, se Expression è `Decimal` , il risultato è `Long` .</span><span class="sxs-lookup"><span data-stu-id="0ecdb-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="0ecdb-126">Overload</span><span class="sxs-lookup"><span data-stu-id="0ecdb-126">Overloading</span></span>  
 <span data-ttu-id="0ecdb-127">L' `Not` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="0ecdb-128">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0ecdb-129">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0ecdb-129">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ecdb-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ecdb-130">Example</span></span>  
 <span data-ttu-id="0ecdb-131">Nell'esempio seguente viene usato l' `Not` operatore per eseguire la negazione logica su un' `Boolean` espressione.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="0ecdb-132">Il risultato è un `Boolean` valore che rappresenta l'inverso del valore dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="0ecdb-133">Nell'esempio precedente vengono restituiti i risultati di `False` e `True` , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ecdb-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ecdb-134">Example</span></span>  
 <span data-ttu-id="0ecdb-135">Nell'esempio seguente viene usato l' `Not` operatore per eseguire la negazione logica dei singoli bit di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="0ecdb-136">Il bit nel modello di risultato viene impostato sul contrario del bit corrispondente nel modello di operando, incluso il bit di segno.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="0ecdb-137">Nell'esempio precedente vengono restituiti rispettivamente i risultati di – 11, – 9 e-7.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ecdb-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ecdb-138">See also</span></span>

- [<span data-ttu-id="0ecdb-139">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ecdb-139">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="0ecdb-140">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ecdb-140">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="0ecdb-141">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="0ecdb-141">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="0ecdb-142">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ecdb-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
