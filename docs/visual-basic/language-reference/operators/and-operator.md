---
title: Operatore And
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: c2b135d27e14816c011a4f70793543aa835d960a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371947"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="fc31c-102">Operatore And (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc31c-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="fc31c-103">Esegue una congiunzione logica di due `Boolean` espressioni o una congiunzione bit per bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="fc31c-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc31c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc31c-104">Syntax</span></span>  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="fc31c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="fc31c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="fc31c-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fc31c-106">Required.</span></span> <span data-ttu-id="fc31c-107">Qualsiasi espressione `Boolean` o numerica.</span><span class="sxs-lookup"><span data-stu-id="fc31c-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="fc31c-108">Per il confronto booleano, `result` è la congiunzione logica di due `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="fc31c-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="fc31c-109">Per le operazioni bit per bit, `result` è un valore numerico che rappresenta la combinazione bit per bit di due schemi di bit numerici.</span><span class="sxs-lookup"><span data-stu-id="fc31c-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="fc31c-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fc31c-110">Required.</span></span> <span data-ttu-id="fc31c-111">Qualsiasi espressione `Boolean` o numerica.</span><span class="sxs-lookup"><span data-stu-id="fc31c-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="fc31c-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fc31c-112">Required.</span></span> <span data-ttu-id="fc31c-113">Qualsiasi espressione `Boolean` o numerica.</span><span class="sxs-lookup"><span data-stu-id="fc31c-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc31c-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="fc31c-114">Remarks</span></span>  
 <span data-ttu-id="fc31c-115">Per il confronto booleano, `result` è `True` se e solo se `expression1` e `expression2` restituiscono `True` .</span><span class="sxs-lookup"><span data-stu-id="fc31c-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="fc31c-116">Nella tabella seguente viene illustrato come `result` determinare.</span><span class="sxs-lookup"><span data-stu-id="fc31c-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="fc31c-117">Se `expression1` è </span><span class="sxs-lookup"><span data-stu-id="fc31c-117">If `expression1` is</span></span>|<span data-ttu-id="fc31c-118">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="fc31c-118">And `expression2` is</span></span>|<span data-ttu-id="fc31c-119">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="fc31c-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="fc31c-120">In un confronto booleano, l' `And` operatore valuta sempre entrambe le espressioni, che possono includere l'esecuzione di chiamate di routine.</span><span class="sxs-lookup"><span data-stu-id="fc31c-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="fc31c-121">L' [operatore AndAlso](andalso-operator.md) esegue un *corto circuito*, il che significa che se `expression1` è `False` , `expression2` non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="fc31c-121">The [AndAlso Operator](andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="fc31c-122">Quando viene applicato a valori numerici, l' `And` operatore esegue un confronto bit per bit dei bit posizionati in modo identico in due espressioni numeriche e imposta il bit corrispondente in in `result` base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="fc31c-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="fc31c-123">Se il bit in `expression1` è</span><span class="sxs-lookup"><span data-stu-id="fc31c-123">If bit in `expression1` is</span></span>|<span data-ttu-id="fc31c-124">E bit in `expression2` è</span><span class="sxs-lookup"><span data-stu-id="fc31c-124">And bit in `expression2` is</span></span>|<span data-ttu-id="fc31c-125">Il bit in `result` è</span><span class="sxs-lookup"><span data-stu-id="fc31c-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="fc31c-126">1</span><span class="sxs-lookup"><span data-stu-id="fc31c-126">1</span></span>|<span data-ttu-id="fc31c-127">1</span><span class="sxs-lookup"><span data-stu-id="fc31c-127">1</span></span>|<span data-ttu-id="fc31c-128">1</span><span class="sxs-lookup"><span data-stu-id="fc31c-128">1</span></span>|  
|<span data-ttu-id="fc31c-129">1</span><span class="sxs-lookup"><span data-stu-id="fc31c-129">1</span></span>|<span data-ttu-id="fc31c-130">0</span><span class="sxs-lookup"><span data-stu-id="fc31c-130">0</span></span>|<span data-ttu-id="fc31c-131">0</span><span class="sxs-lookup"><span data-stu-id="fc31c-131">0</span></span>|  
|<span data-ttu-id="fc31c-132">0</span><span class="sxs-lookup"><span data-stu-id="fc31c-132">0</span></span>|<span data-ttu-id="fc31c-133">1</span><span class="sxs-lookup"><span data-stu-id="fc31c-133">1</span></span>|<span data-ttu-id="fc31c-134">0</span><span class="sxs-lookup"><span data-stu-id="fc31c-134">0</span></span>|  
|<span data-ttu-id="fc31c-135">0</span><span class="sxs-lookup"><span data-stu-id="fc31c-135">0</span></span>|<span data-ttu-id="fc31c-136">0</span><span class="sxs-lookup"><span data-stu-id="fc31c-136">0</span></span>|<span data-ttu-id="fc31c-137">0</span><span class="sxs-lookup"><span data-stu-id="fc31c-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="fc31c-138">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire risultati accurati.</span><span class="sxs-lookup"><span data-stu-id="fc31c-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="fc31c-139">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="fc31c-139">Data Types</span></span>  
 <span data-ttu-id="fc31c-140">Se gli operandi sono costituiti da un'espressione e da un' `Boolean` espressione numerica, Visual Basic converte l' `Boolean` espressione in un valore numerico (-1 per `True` e 0 per `False` ) ed esegue un'operazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="fc31c-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="fc31c-141">Per un confronto booleano, il tipo di dati del risultato è `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="fc31c-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="fc31c-142">Per un confronto bit per bit, il tipo di dati result è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2` .</span><span class="sxs-lookup"><span data-stu-id="fc31c-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="fc31c-143">Vedere la tabella "confronto relazionale e bit per bit" in [tipi di dati dei risultati dell'operatore](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="fc31c-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc31c-144">L' `And` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="fc31c-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fc31c-145">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="fc31c-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fc31c-146">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fc31c-146">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc31c-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc31c-147">Example</span></span>  
 <span data-ttu-id="fc31c-148">Nell'esempio seguente viene utilizzato l' `And` operatore per eseguire una congiunzione logica di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="fc31c-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="fc31c-149">Il risultato è un `Boolean` valore che indica se entrambe le espressioni sono `True` .</span><span class="sxs-lookup"><span data-stu-id="fc31c-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="fc31c-150">Nell'esempio precedente vengono restituiti i risultati di `True` e `False` , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="fc31c-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc31c-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc31c-151">Example</span></span>  
 <span data-ttu-id="fc31c-152">Nell'esempio seguente viene usato l' `And` operatore per eseguire congiunzioni logiche sui singoli bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="fc31c-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="fc31c-153">Il bit nel modello di risultato viene impostato se i bit corrispondenti negli operandi sono entrambi impostati su 1.</span><span class="sxs-lookup"><span data-stu-id="fc31c-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="fc31c-154">Nell'esempio precedente vengono prodotti rispettivamente i risultati 8, 2 e 0.</span><span class="sxs-lookup"><span data-stu-id="fc31c-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc31c-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc31c-155">See also</span></span>

- [<span data-ttu-id="fc31c-156">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc31c-156">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="fc31c-157">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc31c-157">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="fc31c-158">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="fc31c-158">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="fc31c-159">Operatore AndAlso</span><span class="sxs-lookup"><span data-stu-id="fc31c-159">AndAlso Operator</span></span>](andalso-operator.md)
- [<span data-ttu-id="fc31c-160">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc31c-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
