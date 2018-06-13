---
title: Operatori di confronto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: 4e37f55b4c873c3dbea22a8edf0e5e2b58824720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604926"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="54b32-102">Operatori di confronto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54b32-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="54b32-103">Di seguito sono indicati gli operatori di confronto definiti in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="54b32-103">The following are the comparison operators defined in Visual Basic.</span></span>  
  
 <span data-ttu-id="54b32-104">`<` (operatore)</span><span class="sxs-lookup"><span data-stu-id="54b32-104">`<` operator</span></span>  
  
 <span data-ttu-id="54b32-105">`<=` (operatore)</span><span class="sxs-lookup"><span data-stu-id="54b32-105">`<=` operator</span></span>  
  
 <span data-ttu-id="54b32-106">`>` (operatore)</span><span class="sxs-lookup"><span data-stu-id="54b32-106">`>` operator</span></span>  
  
 <span data-ttu-id="54b32-107">`>=` (operatore)</span><span class="sxs-lookup"><span data-stu-id="54b32-107">`>=` operator</span></span>  
  
 <span data-ttu-id="54b32-108">`=` (operatore)</span><span class="sxs-lookup"><span data-stu-id="54b32-108">`=` operator</span></span>  
  
 <span data-ttu-id="54b32-109">`<>` (operatore)</span><span class="sxs-lookup"><span data-stu-id="54b32-109">`<>` operator</span></span>  
  
 [<span data-ttu-id="54b32-110">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="54b32-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [<span data-ttu-id="54b32-111">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="54b32-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [<span data-ttu-id="54b32-112">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="54b32-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 <span data-ttu-id="54b32-113">Questi operatori confrontano due espressioni per determinare se sono uguali, e in caso contrario, le differenze.</span><span class="sxs-lookup"><span data-stu-id="54b32-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="54b32-114">`Is`, `IsNot`, e `Like` vengono discussi in dettaglio nelle pagine della Guida separate.</span><span class="sxs-lookup"><span data-stu-id="54b32-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="54b32-115">Gli operatori di confronto relazionali sono descritti in dettaglio in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="54b32-115">The relational comparison operators are discussed in detail on this page.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b32-116">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54b32-116">Syntax</span></span>  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="54b32-117">Parti</span><span class="sxs-lookup"><span data-stu-id="54b32-117">Parts</span></span>  
 `result`  
 <span data-ttu-id="54b32-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="54b32-118">Required.</span></span> <span data-ttu-id="54b32-119">Oggetto `Boolean` valore che rappresenta il risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="54b32-119">A `Boolean` value representing the result of the comparison.</span></span>  
  
 `expression`  
 <span data-ttu-id="54b32-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="54b32-120">Required.</span></span> <span data-ttu-id="54b32-121">Qualsiasi espressione.</span><span class="sxs-lookup"><span data-stu-id="54b32-121">Any expression.</span></span>  
  
 `comparisonoperator`  
 <span data-ttu-id="54b32-122">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="54b32-122">Required.</span></span> <span data-ttu-id="54b32-123">Operatore di confronto relazionale.</span><span class="sxs-lookup"><span data-stu-id="54b32-123">Any relational comparison operator.</span></span>  
  
 <span data-ttu-id="54b32-124">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="54b32-124">`object1`, `object2`</span></span>  
 <span data-ttu-id="54b32-125">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="54b32-125">Required.</span></span> <span data-ttu-id="54b32-126">I nomi di oggetto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="54b32-126">Any reference object names.</span></span>  
  
 `string`  
 <span data-ttu-id="54b32-127">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="54b32-127">Required.</span></span> <span data-ttu-id="54b32-128">Qualsiasi espressione `String`.</span><span class="sxs-lookup"><span data-stu-id="54b32-128">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="54b32-129">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="54b32-129">Required.</span></span> <span data-ttu-id="54b32-130">Qualsiasi `String` intervallo di caratteri o espressione.</span><span class="sxs-lookup"><span data-stu-id="54b32-130">Any `String` expression or range of characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54b32-131">Note</span><span class="sxs-lookup"><span data-stu-id="54b32-131">Remarks</span></span>  
 <span data-ttu-id="54b32-132">Nella tabella seguente contiene un elenco di operatori di confronto relazionali e le condizioni che determinano se `result` è `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="54b32-132">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>  
  
|<span data-ttu-id="54b32-133">Operatore</span><span class="sxs-lookup"><span data-stu-id="54b32-133">Operator</span></span>|<span data-ttu-id="54b32-134">`True` Se</span><span class="sxs-lookup"><span data-stu-id="54b32-134">`True` if</span></span>|<span data-ttu-id="54b32-135">`False` Se</span><span class="sxs-lookup"><span data-stu-id="54b32-135">`False` if</span></span>|  
|--------------|---------------|----------------|  
|<span data-ttu-id="54b32-136">`<` (Minore di)</span><span class="sxs-lookup"><span data-stu-id="54b32-136">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|  
|<span data-ttu-id="54b32-137">`<=` (Minore o uguale a)</span><span class="sxs-lookup"><span data-stu-id="54b32-137">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|  
|<span data-ttu-id="54b32-138">`>` (Maggiore di)</span><span class="sxs-lookup"><span data-stu-id="54b32-138">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|  
|<span data-ttu-id="54b32-139">`>=` (Maggiore o uguale a)</span><span class="sxs-lookup"><span data-stu-id="54b32-139">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|  
|<span data-ttu-id="54b32-140">`=` (È uguale a)</span><span class="sxs-lookup"><span data-stu-id="54b32-140">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|  
|<span data-ttu-id="54b32-141">`<>` (Non uguale a)</span><span class="sxs-lookup"><span data-stu-id="54b32-141">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  <span data-ttu-id="54b32-142">Il [= operatore](../../../visual-basic/language-reference/operators/assignment-operator.md) viene usato anche come un operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="54b32-142">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>  
  
 <span data-ttu-id="54b32-143">Il `Is` (operatore), il `IsNot` (operatore) e `Like` operatore avere le funzionalità di confronto specifiche che si differenziano dagli operatori nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="54b32-143">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>  
  
## <a name="comparing-numbers"></a><span data-ttu-id="54b32-144">Il confronto tra valori</span><span class="sxs-lookup"><span data-stu-id="54b32-144">Comparing Numbers</span></span>  
 <span data-ttu-id="54b32-145">Quando si confronta un'espressione di tipo `Single` a uno di tipo `Double`, `Single` espressione viene convertita in `Double`.</span><span class="sxs-lookup"><span data-stu-id="54b32-145">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="54b32-146">Questo comportamento è opposto a quello trovato in Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="54b32-146">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>  
  
 <span data-ttu-id="54b32-147">Analogamente, quando si confronta un'espressione di tipo `Decimal` a un'espressione di tipo `Single` o `Double`, `Decimal` espressione viene convertita in `Single` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="54b32-147">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="54b32-148">Per `Decimal` espressioni, qualsiasi valore frazionario minore 1E-28 potrebbe andare perse.</span><span class="sxs-lookup"><span data-stu-id="54b32-148">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="54b32-149">Tale perdita valore frazionario potrebbe risultano uguali quando non sono di due valori.</span><span class="sxs-lookup"><span data-stu-id="54b32-149">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="54b32-150">Per questo motivo, è necessario prestare attenzione quando si usa l'uguaglianza (`=`) per confrontare due variabili a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="54b32-150">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="54b32-151">È più sicuro verificare se il valore assoluto della differenza tra due numeri è minore di tolleranza minima accettabile.</span><span class="sxs-lookup"><span data-stu-id="54b32-151">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>  
  
### <a name="floating-point-imprecision"></a><span data-ttu-id="54b32-152">A virgola mobile imprecisione</span><span class="sxs-lookup"><span data-stu-id="54b32-152">Floating-point Imprecision</span></span>  
 <span data-ttu-id="54b32-153">Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre contengono una precisa rappresentazione in memoria.</span><span class="sxs-lookup"><span data-stu-id="54b32-153">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="54b32-154">Ciò potrebbe provocare risultati imprevisti da alcune operazioni, ad esempio il confronto di valori e [operatore Mod](../../../visual-basic/language-reference/operators/mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="54b32-154">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="54b32-155">Per ulteriori informazioni, vedere [risoluzione dei problemi dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="54b32-155">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="comparing-strings"></a><span data-ttu-id="54b32-156">Confronto di stringhe</span><span class="sxs-lookup"><span data-stu-id="54b32-156">Comparing Strings</span></span>  
 <span data-ttu-id="54b32-157">Quando si confrontano stringhe, le espressioni stringa vengono valutate in base all'ordine alfabetico, che dipende il `Option Compare` impostazione.</span><span class="sxs-lookup"><span data-stu-id="54b32-157">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>  
  
 <span data-ttu-id="54b32-158">`Option Compare Binary` Consente i confronti per un tipo di ordinamento derivato dalle rappresentazioni binarie interne dei caratteri di stringhe.</span><span class="sxs-lookup"><span data-stu-id="54b32-158">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="54b32-159">Il tipo di ordinamento è determinato dalla tabella codici.</span><span class="sxs-lookup"><span data-stu-id="54b32-159">The sort order is determined by the code page.</span></span> <span data-ttu-id="54b32-160">Nell'esempio seguente viene illustrato un tipico ordinamento binario.</span><span class="sxs-lookup"><span data-stu-id="54b32-160">The following example shows a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="54b32-161">`Option Compare Text` basi stringa i confronti per un criterio di ordinamento testuale, tra maiuscole e minuscole determinato dalle impostazioni locali dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54b32-161">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="54b32-162">Quando si imposta `Option Compare Text` e ordinare i caratteri nell'esempio precedente, si applica l'ordinamento di testo seguente:</span><span class="sxs-lookup"><span data-stu-id="54b32-162">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a><span data-ttu-id="54b32-163">Dipendono dalle impostazioni locali</span><span class="sxs-lookup"><span data-stu-id="54b32-163">Locale Dependence</span></span>  
 <span data-ttu-id="54b32-164">Quando si imposta `Option Compare Text`, il risultato di un confronto tra stringhe può dipendere dalle impostazioni locali in cui è in esecuzione l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54b32-164">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="54b32-165">Come uguali in una lingua ma non in un'altra potrebbero confrontare i due caratteri.</span><span class="sxs-lookup"><span data-stu-id="54b32-165">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="54b32-166">Se si utilizza un confronto tra stringhe per decisioni importanti, ad esempio, se si desidera accettare un tentativo di accesso, dovrebbe essere tra maiuscole e minuscole delle impostazioni locali dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="54b32-166">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="54b32-167">Prendere in considerazione delle impostazioni `Option Compare Binary` o la chiamata di <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, che tiene conto delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="54b32-167">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="54b32-168">La programmazione con gli operatori di confronto relazionale</span><span class="sxs-lookup"><span data-stu-id="54b32-168">Typeless Programming with Relational Comparison Operators</span></span>  
 <span data-ttu-id="54b32-169">L'utilizzo degli operatori di confronto relazionali con `Object` espressioni non è consentita in `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="54b32-169">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="54b32-170">Quando `Option Strict` è `Off`e `expression1` o `expression2` è un `Object` espressione, i tipi di runtime determinano la modalità di confronto.</span><span class="sxs-lookup"><span data-stu-id="54b32-170">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="54b32-171">Nella tabella seguente viene illustrato come le espressioni vengono confrontate e il risultato del confronto, a seconda del tipo di runtime degli operandi.</span><span class="sxs-lookup"><span data-stu-id="54b32-171">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>  
  
|<span data-ttu-id="54b32-172">Se gli operandi sono</span><span class="sxs-lookup"><span data-stu-id="54b32-172">If operands are</span></span>|<span data-ttu-id="54b32-173">Risultato del confronto è</span><span class="sxs-lookup"><span data-stu-id="54b32-173">Comparison is</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="54b32-174">Entrambi `String`</span><span class="sxs-lookup"><span data-stu-id="54b32-174">Both `String`</span></span>|<span data-ttu-id="54b32-175">Confronto in base alle caratteristiche di ordinamento delle stringhe di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="54b32-175">Sort comparison based on string sorting characteristics.</span></span>|  
|<span data-ttu-id="54b32-176">Entrambi numerici</span><span class="sxs-lookup"><span data-stu-id="54b32-176">Both numeric</span></span>|<span data-ttu-id="54b32-177">Gli oggetti convertiti in `Double`, confronto numerico.</span><span class="sxs-lookup"><span data-stu-id="54b32-177">Objects converted to `Double`, numeric comparison.</span></span>|  
|<span data-ttu-id="54b32-178">Uno numerico e uno `String`</span><span class="sxs-lookup"><span data-stu-id="54b32-178">One numeric and one `String`</span></span>|<span data-ttu-id="54b32-179">Il `String` viene convertito in un `Double` e viene eseguito un confronto numerico.</span><span class="sxs-lookup"><span data-stu-id="54b32-179">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="54b32-180">Se il `String` non può essere convertito in `Double`, un <xref:System.InvalidCastException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="54b32-180">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|  
|<span data-ttu-id="54b32-181">Uno o entrambi sono tipi di riferimento diverso da `String`</span><span class="sxs-lookup"><span data-stu-id="54b32-181">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="54b32-182">Viene generato un tipo <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="54b32-182">An <xref:System.InvalidCastException> is thrown.</span></span>|  
  
 <span data-ttu-id="54b32-183">Considerano i confronti numerici `Nothing` come 0.</span><span class="sxs-lookup"><span data-stu-id="54b32-183">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="54b32-184">Confronti di stringhe considerano `Nothing` come `""` (una stringa vuota).</span><span class="sxs-lookup"><span data-stu-id="54b32-184">String comparisons treat `Nothing` as `""` (an empty string).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="54b32-185">Overload</span><span class="sxs-lookup"><span data-stu-id="54b32-185">Overloading</span></span>  
 <span data-ttu-id="54b32-186">Gli operatori di confronto relazionale (`<`.</span><span class="sxs-lookup"><span data-stu-id="54b32-186">The relational comparison operators (`<`.</span></span> <span data-ttu-id="54b32-187">`<=``>`, `>=`, `=`, `<>`) può essere *overload*, ovvero una classe o struttura possibile ridefinirne il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="54b32-187">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="54b32-188">Se il codice utilizza uno di questi operatori in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="54b32-188">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="54b32-189">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="54b32-189">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
 <span data-ttu-id="54b32-190">Si noti che il [= operatore](../../../visual-basic/language-reference/operators/assignment-operator.md) può essere sottoposto a overload solo come operatore di confronto relazionale, non come un operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="54b32-190">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54b32-191">Esempio</span><span class="sxs-lookup"><span data-stu-id="54b32-191">Example</span></span>  
 <span data-ttu-id="54b32-192">Nell'esempio seguente mostra vari usi di operatori di confronto relazionali che consentono di confrontare le espressioni.</span><span class="sxs-lookup"><span data-stu-id="54b32-192">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="54b32-193">Gli operatori di confronto relazionali restituiscono un `Boolean` risultato che indica se l'espressione specificata è `True`.</span><span class="sxs-lookup"><span data-stu-id="54b32-193">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="54b32-194">Quando si applica il `>` e `<` agli operatori di stringhe, il confronto viene eseguito utilizzando il normale criterio di ordinamento alfabetico delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="54b32-194">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="54b32-195">In questo ordine può essere dipende dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="54b32-195">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="54b32-196">Se l'ordinamento è distinzione maiuscole/minuscole dipende il [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) impostazione.</span><span class="sxs-lookup"><span data-stu-id="54b32-196">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 <span data-ttu-id="54b32-197">Nell'esempio precedente, il primo confronto restituisce `False` e gli altri confronti restituiscono `True`.</span><span class="sxs-lookup"><span data-stu-id="54b32-197">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b32-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54b32-198">See Also</span></span>  
 <xref:System.InvalidCastException>  
 [<span data-ttu-id="54b32-199">Operatore =</span><span class="sxs-lookup"><span data-stu-id="54b32-199">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [<span data-ttu-id="54b32-200">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54b32-200">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="54b32-201">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="54b32-201">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="54b32-202">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="54b32-202">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="54b32-203">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54b32-203">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
