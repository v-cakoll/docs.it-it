---
title: Operatore Xor
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: 999050314d674fa98833083d84796e471c22971d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406340"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="dd78e-102">Operatore Xor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd78e-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="dd78e-103">Esegue un'esclusione logica di due `Boolean` espressioni oppure un'esclusione bit per bit su due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="dd78e-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd78e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd78e-104">Syntax</span></span>  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="dd78e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="dd78e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="dd78e-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd78e-106">Required.</span></span> <span data-ttu-id="dd78e-107">Qualsiasi `Boolean` variabile o variabile numerica.</span><span class="sxs-lookup"><span data-stu-id="dd78e-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="dd78e-108">Per il confronto booleano, `result` è l'esclusione logica (disgiunzione logica esclusiva) di due `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="dd78e-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="dd78e-109">Per le operazioni bit per bit, `result` è un valore numerico che rappresenta l'esclusione bit per bit (disgiunzione bit per bit esclusiva) di due modelli di bit numerici.</span><span class="sxs-lookup"><span data-stu-id="dd78e-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="dd78e-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd78e-110">Required.</span></span> <span data-ttu-id="dd78e-111">Qualsiasi espressione `Boolean` o numerica.</span><span class="sxs-lookup"><span data-stu-id="dd78e-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="dd78e-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd78e-112">Required.</span></span> <span data-ttu-id="dd78e-113">Qualsiasi espressione `Boolean` o numerica.</span><span class="sxs-lookup"><span data-stu-id="dd78e-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd78e-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="dd78e-114">Remarks</span></span>  
 <span data-ttu-id="dd78e-115">Per il confronto booleano, `result` è `True` se e solo se esattamente uno di `expression1` e `expression2` restituisce `True` .</span><span class="sxs-lookup"><span data-stu-id="dd78e-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="dd78e-116">Ovvero, se e solo se `expression1` e `expression2` restituiscono valori opposti `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="dd78e-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="dd78e-117">Nella tabella seguente viene illustrato come `result` determinare.</span><span class="sxs-lookup"><span data-stu-id="dd78e-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="dd78e-118">Se `expression1` è </span><span class="sxs-lookup"><span data-stu-id="dd78e-118">If `expression1` is</span></span>|<span data-ttu-id="dd78e-119">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="dd78e-119">And `expression2` is</span></span>|<span data-ttu-id="dd78e-120">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="dd78e-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="dd78e-121">In un confronto booleano, l' `Xor` operatore valuta sempre entrambe le espressioni, che possono includere l'esecuzione di chiamate di routine.</span><span class="sxs-lookup"><span data-stu-id="dd78e-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="dd78e-122">Non esiste alcuna controparte di corto circuito di `Xor` , perché il risultato dipende sempre da entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="dd78e-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="dd78e-123">Per gli operatori logici di *corto circuito* , vedere [operatore AndAlso](andalso-operator.md) e [operatore OrElse](orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="dd78e-123">For *short-circuiting* logical operators, see [AndAlso Operator](andalso-operator.md) and [OrElse Operator](orelse-operator.md).</span></span>  
  
 <span data-ttu-id="dd78e-124">Per le operazioni bit per bit, l' `Xor` operatore esegue un confronto bit per bit dei bit posizionati in modo identico in due espressioni numeriche e imposta il bit corrispondente in in `result` base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="dd78e-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="dd78e-125">Se il bit in `expression1` è</span><span class="sxs-lookup"><span data-stu-id="dd78e-125">If bit in `expression1` is</span></span>|<span data-ttu-id="dd78e-126">E bit in `expression2` è</span><span class="sxs-lookup"><span data-stu-id="dd78e-126">And bit in `expression2` is</span></span>|<span data-ttu-id="dd78e-127">Il bit in `result` è</span><span class="sxs-lookup"><span data-stu-id="dd78e-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="dd78e-128">1</span><span class="sxs-lookup"><span data-stu-id="dd78e-128">1</span></span>|<span data-ttu-id="dd78e-129">1</span><span class="sxs-lookup"><span data-stu-id="dd78e-129">1</span></span>|<span data-ttu-id="dd78e-130">0</span><span class="sxs-lookup"><span data-stu-id="dd78e-130">0</span></span>|  
|<span data-ttu-id="dd78e-131">1</span><span class="sxs-lookup"><span data-stu-id="dd78e-131">1</span></span>|<span data-ttu-id="dd78e-132">0</span><span class="sxs-lookup"><span data-stu-id="dd78e-132">0</span></span>|<span data-ttu-id="dd78e-133">1</span><span class="sxs-lookup"><span data-stu-id="dd78e-133">1</span></span>|  
|<span data-ttu-id="dd78e-134">0</span><span class="sxs-lookup"><span data-stu-id="dd78e-134">0</span></span>|<span data-ttu-id="dd78e-135">1</span><span class="sxs-lookup"><span data-stu-id="dd78e-135">1</span></span>|<span data-ttu-id="dd78e-136">1</span><span class="sxs-lookup"><span data-stu-id="dd78e-136">1</span></span>|  
|<span data-ttu-id="dd78e-137">0</span><span class="sxs-lookup"><span data-stu-id="dd78e-137">0</span></span>|<span data-ttu-id="dd78e-138">0</span><span class="sxs-lookup"><span data-stu-id="dd78e-138">0</span></span>|<span data-ttu-id="dd78e-139">0</span><span class="sxs-lookup"><span data-stu-id="dd78e-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="dd78e-140">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire un'esecuzione accurata.</span><span class="sxs-lookup"><span data-stu-id="dd78e-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="dd78e-141">Ad esempio, 5 `Xor` 3 è 6.</span><span class="sxs-lookup"><span data-stu-id="dd78e-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="dd78e-142">Per verificarne il motivo, convertire 5 e 3 nelle rispettive rappresentazioni binarie, 101 e 011.</span><span class="sxs-lookup"><span data-stu-id="dd78e-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="dd78e-143">Usare quindi la tabella precedente per determinare che 101 Xor 011 è 110, ovvero la rappresentazione binaria del numero decimale 6.</span><span class="sxs-lookup"><span data-stu-id="dd78e-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="dd78e-144">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="dd78e-144">Data Types</span></span>  
 <span data-ttu-id="dd78e-145">Se gli operandi sono costituiti da un'espressione e da un' `Boolean` espressione numerica, Visual Basic converte l' `Boolean` espressione in un valore numerico (-1 per `True` e 0 per `False` ) ed esegue un'operazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="dd78e-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="dd78e-146">Per un `Boolean` confronto, il tipo di dati del risultato è `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="dd78e-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="dd78e-147">Per un confronto bit per bit, il tipo di dati result è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2` .</span><span class="sxs-lookup"><span data-stu-id="dd78e-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="dd78e-148">Vedere la tabella "confronto relazionale e bit per bit" in [tipi di dati dei risultati dell'operatore](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="dd78e-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="dd78e-149">Overload</span><span class="sxs-lookup"><span data-stu-id="dd78e-149">Overloading</span></span>  
 <span data-ttu-id="dd78e-150">L' `Xor` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="dd78e-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="dd78e-151">Se il codice usa questo operatore su una classe o una struttura di questo tipo, verificare di aver compreso il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="dd78e-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="dd78e-152">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="dd78e-152">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd78e-153">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd78e-153">Example</span></span>  
 <span data-ttu-id="dd78e-154">Nell'esempio seguente viene usato l' `Xor` operatore per eseguire l'esclusione logica (disgiunzione logica esclusiva) su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="dd78e-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="dd78e-155">Il risultato è un `Boolean` valore che indica se una delle espressioni è esattamente `True` .</span><span class="sxs-lookup"><span data-stu-id="dd78e-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="dd78e-156">Nell'esempio precedente vengono prodotti rispettivamente i risultati di `False` , `True` e `False` .</span><span class="sxs-lookup"><span data-stu-id="dd78e-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd78e-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd78e-157">Example</span></span>  
 <span data-ttu-id="dd78e-158">Nell'esempio seguente viene usato l' `Xor` operatore per eseguire l'esclusione logica (disgiunzione logica esclusiva) sui singoli bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="dd78e-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="dd78e-159">Il bit nel modello di risultato viene impostato se esattamente uno dei bit corrispondenti negli operandi è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="dd78e-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="dd78e-160">Nell'esempio precedente vengono prodotti rispettivamente i risultati 2, 12 e 14.</span><span class="sxs-lookup"><span data-stu-id="dd78e-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd78e-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd78e-161">See also</span></span>

- [<span data-ttu-id="dd78e-162">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd78e-162">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="dd78e-163">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd78e-163">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="dd78e-164">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="dd78e-164">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="dd78e-165">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd78e-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
