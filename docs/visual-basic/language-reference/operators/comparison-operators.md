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
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: 9014cac5e2f3933b27411dfe5681fc16f4cdde30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821036"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="d987e-102">Operatori di confronto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d987e-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="d987e-103">Di seguito è elencati gli operatori di confronto definiti in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d987e-103">The following are the comparison operators defined in Visual Basic.</span></span>  
  
 <span data-ttu-id="d987e-104">`<` Operatore</span><span class="sxs-lookup"><span data-stu-id="d987e-104">`<` operator</span></span>  
  
 <span data-ttu-id="d987e-105">`<=` Operatore</span><span class="sxs-lookup"><span data-stu-id="d987e-105">`<=` operator</span></span>  
  
 <span data-ttu-id="d987e-106">`>` Operatore</span><span class="sxs-lookup"><span data-stu-id="d987e-106">`>` operator</span></span>  
  
 <span data-ttu-id="d987e-107">`>=` Operatore</span><span class="sxs-lookup"><span data-stu-id="d987e-107">`>=` operator</span></span>  
  
 <span data-ttu-id="d987e-108">`=` Operatore</span><span class="sxs-lookup"><span data-stu-id="d987e-108">`=` operator</span></span>  
  
 <span data-ttu-id="d987e-109">`<>` Operatore</span><span class="sxs-lookup"><span data-stu-id="d987e-109">`<>` operator</span></span>  
  
 [<span data-ttu-id="d987e-110">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="d987e-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [<span data-ttu-id="d987e-111">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="d987e-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [<span data-ttu-id="d987e-112">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="d987e-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 <span data-ttu-id="d987e-113">Questi operatori confrontano due espressioni per determinare se sono uguali, e in caso contrario, le differenze.</span><span class="sxs-lookup"><span data-stu-id="d987e-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="d987e-114">`Is`, `IsNot`, e `Like` vengono descritti in dettaglio nelle pagine della Guida separate.</span><span class="sxs-lookup"><span data-stu-id="d987e-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="d987e-115">Gli operatori di confronto relazionale vengono descritti in dettaglio in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="d987e-115">The relational comparison operators are discussed in detail on this page.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d987e-116">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d987e-116">Syntax</span></span>  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="d987e-117">Parti</span><span class="sxs-lookup"><span data-stu-id="d987e-117">Parts</span></span>  
 `result`  
 <span data-ttu-id="d987e-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d987e-118">Required.</span></span> <span data-ttu-id="d987e-119">Oggetto `Boolean` valore che rappresenta il risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="d987e-119">A `Boolean` value representing the result of the comparison.</span></span>  
  
 `expression`  
 <span data-ttu-id="d987e-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d987e-120">Required.</span></span> <span data-ttu-id="d987e-121">Qualsiasi espressione.</span><span class="sxs-lookup"><span data-stu-id="d987e-121">Any expression.</span></span>  
  
 `comparisonoperator`  
 <span data-ttu-id="d987e-122">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d987e-122">Required.</span></span> <span data-ttu-id="d987e-123">Qualsiasi operatore di confronto relazionale.</span><span class="sxs-lookup"><span data-stu-id="d987e-123">Any relational comparison operator.</span></span>  
  
 <span data-ttu-id="d987e-124">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="d987e-124">`object1`, `object2`</span></span>  
 <span data-ttu-id="d987e-125">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d987e-125">Required.</span></span> <span data-ttu-id="d987e-126">Tutti i nomi degli oggetti di riferimento.</span><span class="sxs-lookup"><span data-stu-id="d987e-126">Any reference object names.</span></span>  
  
 `string`  
 <span data-ttu-id="d987e-127">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d987e-127">Required.</span></span> <span data-ttu-id="d987e-128">Qualsiasi espressione `String` .</span><span class="sxs-lookup"><span data-stu-id="d987e-128">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="d987e-129">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d987e-129">Required.</span></span> <span data-ttu-id="d987e-130">Qualsiasi `String` espressione o un intervallo di caratteri.</span><span class="sxs-lookup"><span data-stu-id="d987e-130">Any `String` expression or range of characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d987e-131">Note</span><span class="sxs-lookup"><span data-stu-id="d987e-131">Remarks</span></span>  
 <span data-ttu-id="d987e-132">Nella tabella seguente contiene un elenco di operatori di confronto relazionale e le condizioni che determinano se `result` viene `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="d987e-132">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>  
  
|<span data-ttu-id="d987e-133">Operatore</span><span class="sxs-lookup"><span data-stu-id="d987e-133">Operator</span></span>|<span data-ttu-id="d987e-134">`True` se</span><span class="sxs-lookup"><span data-stu-id="d987e-134">`True` if</span></span>|<span data-ttu-id="d987e-135">`False` se</span><span class="sxs-lookup"><span data-stu-id="d987e-135">`False` if</span></span>|  
|--------------|---------------|----------------|  
|<span data-ttu-id="d987e-136">`<` (Minore di)</span><span class="sxs-lookup"><span data-stu-id="d987e-136">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|  
|<span data-ttu-id="d987e-137">`<=` (Minore o uguale a)</span><span class="sxs-lookup"><span data-stu-id="d987e-137">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|  
|<span data-ttu-id="d987e-138">`>` (Maggiore di)</span><span class="sxs-lookup"><span data-stu-id="d987e-138">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|  
|<span data-ttu-id="d987e-139">`>=` (Maggiore o uguale a)</span><span class="sxs-lookup"><span data-stu-id="d987e-139">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|  
|<span data-ttu-id="d987e-140">`=` (Uguale a)</span><span class="sxs-lookup"><span data-stu-id="d987e-140">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|  
|<span data-ttu-id="d987e-141">`<>` (Non uguale a)</span><span class="sxs-lookup"><span data-stu-id="d987e-141">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  <span data-ttu-id="d987e-142">Il [= (operatore)](../../../visual-basic/language-reference/operators/assignment-operator.md) viene usato anche come operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d987e-142">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>  
  
 <span data-ttu-id="d987e-143">Il `Is` operatore, la `IsNot` operatore e il `Like` operatore hanno le funzionalità di confronto specifiche che si differenziano dagli operatori nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="d987e-143">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>  
  
## <a name="comparing-numbers"></a><span data-ttu-id="d987e-144">Confronto tra valori</span><span class="sxs-lookup"><span data-stu-id="d987e-144">Comparing Numbers</span></span>  
 <span data-ttu-id="d987e-145">Quando si confronta un'espressione di tipo `Single` a uno di tipo `Double`, il `Single` espressione viene convertita in `Double`.</span><span class="sxs-lookup"><span data-stu-id="d987e-145">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="d987e-146">Questo comportamento è opposto a quello trovato in Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="d987e-146">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>  
  
 <span data-ttu-id="d987e-147">Analogamente, quando si confronta un'espressione di tipo `Decimal` a un'espressione di tipo `Single` oppure `Double`, il `Decimal` espressione viene convertita in `Single` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="d987e-147">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="d987e-148">Per `Decimal` espressioni, qualsiasi valore minore di 1E-28 frazionari potrebbe andare perse.</span><span class="sxs-lookup"><span data-stu-id="d987e-148">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="d987e-149">Potrebbero essere due valori vengono considerati uguali quando non sono di perdere i dati valore frazionario.</span><span class="sxs-lookup"><span data-stu-id="d987e-149">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="d987e-150">Per questo motivo, è necessario prestare attenzione quando si usa l'uguaglianza (`=`) per confrontare due variabili a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="d987e-150">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="d987e-151">È più sicuro verificare se il valore assoluto della differenza tra due numeri è minore di tolleranza minima accettabile.</span><span class="sxs-lookup"><span data-stu-id="d987e-151">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>  
  
### <a name="floating-point-imprecision"></a><span data-ttu-id="d987e-152">A virgola mobile dell'imprecisione</span><span class="sxs-lookup"><span data-stu-id="d987e-152">Floating-point Imprecision</span></span>  
 <span data-ttu-id="d987e-153">Quando si lavora con numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione esatta in memoria.</span><span class="sxs-lookup"><span data-stu-id="d987e-153">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="d987e-154">Ciò potrebbe provocare risultati imprevisti da determinate operazioni, ad esempio il confronto dei valori e le [operatore Mod](../../../visual-basic/language-reference/operators/mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="d987e-154">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="d987e-155">Per altre informazioni, vedere [tipi di dati di risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="d987e-155">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="comparing-strings"></a><span data-ttu-id="d987e-156">Confronto di stringhe</span><span class="sxs-lookup"><span data-stu-id="d987e-156">Comparing Strings</span></span>  
 <span data-ttu-id="d987e-157">Quando si confrontano stringhe, le espressioni stringa vengono valutate in base all'ordine alfabetico, che dipende la `Option Compare` impostazione.</span><span class="sxs-lookup"><span data-stu-id="d987e-157">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>  
  
 <span data-ttu-id="d987e-158">`Option Compare Binary` Consente i confronti in un tipo di ordinamento derivato dalle rappresentazioni binarie interne dei caratteri di stringhe.</span><span class="sxs-lookup"><span data-stu-id="d987e-158">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="d987e-159">L'ordinamento è determinato dalla tabella codici.</span><span class="sxs-lookup"><span data-stu-id="d987e-159">The sort order is determined by the code page.</span></span> <span data-ttu-id="d987e-160">L'esempio seguente illustra un tipico ordinamento binario.</span><span class="sxs-lookup"><span data-stu-id="d987e-160">The following example shows a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="d987e-161">`Option Compare Text` Consente di eseguire stringhe confronti su un criterio di ordinamento testuale, tra maiuscole e minuscole determinato dalle impostazioni locali dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d987e-161">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="d987e-162">Quando si imposta `Option Compare Text` e ordinano i caratteri nell'esempio precedente, si applica l'ordinamento di testo seguente:</span><span class="sxs-lookup"><span data-stu-id="d987e-162">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a><span data-ttu-id="d987e-163">Dipendono dalle impostazioni locali</span><span class="sxs-lookup"><span data-stu-id="d987e-163">Locale Dependence</span></span>  
 <span data-ttu-id="d987e-164">Quando si imposta `Option Compare Text`, il risultato di un confronto tra stringhe può dipendere dalle impostazioni locali in cui viene eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d987e-164">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="d987e-165">Due caratteri potrebbe essere considerati uguali nelle impostazioni locali, ma non in un altro.</span><span class="sxs-lookup"><span data-stu-id="d987e-165">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="d987e-166">Se si usa un confronto tra stringhe per prendere decisioni importanti, ad esempio se si desidera accettare un tentativo di accesso, dovrebbe essere tra maiuscole e minuscole delle impostazioni locali dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="d987e-166">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="d987e-167">Prendere in considerazione delle impostazioni `Option Compare Binary` o la chiamata di <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, che tiene conto delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="d987e-167">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="d987e-168">La programmazione con gli operatori di confronto relazionale</span><span class="sxs-lookup"><span data-stu-id="d987e-168">Typeless Programming with Relational Comparison Operators</span></span>  
 <span data-ttu-id="d987e-169">L'utilizzo degli operatori di confronto relazionale con `Object` espressioni non è consentita negli `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="d987e-169">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="d987e-170">Quando `Option Strict` viene `Off`e il valore `expression1` oppure `expression2` è un `Object` espressione, i tipi in fase di esecuzione determinano la modalità di confronto.</span><span class="sxs-lookup"><span data-stu-id="d987e-170">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="d987e-171">Nella tabella seguente viene illustrato come vengono confrontate le espressioni e il risultato del confronto, a seconda del tipo di runtime degli operandi.</span><span class="sxs-lookup"><span data-stu-id="d987e-171">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>  
  
|<span data-ttu-id="d987e-172">Se gli operandi sono</span><span class="sxs-lookup"><span data-stu-id="d987e-172">If operands are</span></span>|<span data-ttu-id="d987e-173">Risultato del confronto è</span><span class="sxs-lookup"><span data-stu-id="d987e-173">Comparison is</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="d987e-174">Entrambi `String`</span><span class="sxs-lookup"><span data-stu-id="d987e-174">Both `String`</span></span>|<span data-ttu-id="d987e-175">Confronto in base alle caratteristiche di ordinamento delle stringhe di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="d987e-175">Sort comparison based on string sorting characteristics.</span></span>|  
|<span data-ttu-id="d987e-176">Entrambe numeriche</span><span class="sxs-lookup"><span data-stu-id="d987e-176">Both numeric</span></span>|<span data-ttu-id="d987e-177">Gli oggetti convertiti in `Double`, confronto numerico.</span><span class="sxs-lookup"><span data-stu-id="d987e-177">Objects converted to `Double`, numeric comparison.</span></span>|  
|<span data-ttu-id="d987e-178">Uno numerico e uno `String`</span><span class="sxs-lookup"><span data-stu-id="d987e-178">One numeric and one `String`</span></span>|<span data-ttu-id="d987e-179">Il `String` viene convertito in un `Double` e viene eseguito un confronto numerico.</span><span class="sxs-lookup"><span data-stu-id="d987e-179">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="d987e-180">Se il `String` non può essere convertito `Double`, un <xref:System.InvalidCastException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d987e-180">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|  
|<span data-ttu-id="d987e-181">Uno o entrambi sono tipi riferimento diverso da `String`</span><span class="sxs-lookup"><span data-stu-id="d987e-181">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="d987e-182">Viene generato un tipo <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="d987e-182">An <xref:System.InvalidCastException> is thrown.</span></span>|  
  
 <span data-ttu-id="d987e-183">Considerano i confronti numerici `Nothing` come 0.</span><span class="sxs-lookup"><span data-stu-id="d987e-183">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="d987e-184">Confronti di stringhe considerano `Nothing` come `""` (una stringa vuota).</span><span class="sxs-lookup"><span data-stu-id="d987e-184">String comparisons treat `Nothing` as `""` (an empty string).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d987e-185">Overload</span><span class="sxs-lookup"><span data-stu-id="d987e-185">Overloading</span></span>  
 <span data-ttu-id="d987e-186">Gli operatori di confronto relazionale (`<`.</span><span class="sxs-lookup"><span data-stu-id="d987e-186">The relational comparison operators (`<`.</span></span> <span data-ttu-id="d987e-187">`<=``>`, `>=`, `=`, `<>`) può essere *sottoposti a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="d987e-187">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d987e-188">Se il codice usa uno di questi operatori in una classe o una struttura, assicurarsi di che comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="d987e-188">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="d987e-189">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d987e-189">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
 <span data-ttu-id="d987e-190">Si noti che il [= (operatore)](../../../visual-basic/language-reference/operators/assignment-operator.md) può essere sottoposto a overload solo come un operatore di confronto relazionale e non come un operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d987e-190">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d987e-191">Esempio</span><span class="sxs-lookup"><span data-stu-id="d987e-191">Example</span></span>  
 <span data-ttu-id="d987e-192">L'esempio seguente illustra vari usi di operatori di confronto relazionale, che consente di confrontare espressioni.</span><span class="sxs-lookup"><span data-stu-id="d987e-192">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="d987e-193">Gli operatori di confronto relazionale restituiscono un `Boolean` risultato che indica se l'espressione specificata è `True`.</span><span class="sxs-lookup"><span data-stu-id="d987e-193">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="d987e-194">Quando si applica il `>` e `<` agli operatori di stringhe, il confronto viene eseguito utilizzando il normale di ordinamento alfabetico delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="d987e-194">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="d987e-195">Quest'ordine può dipendere dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="d987e-195">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="d987e-196">Se l'ordinamento è distinzione maiuscole/minuscole o meno dipende il [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) impostazione.</span><span class="sxs-lookup"><span data-stu-id="d987e-196">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>  
  
 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]  
  
 <span data-ttu-id="d987e-197">Nell'esempio precedente, restituisce il primo confronto `False` e gli altri confronti restituiscono `True`.</span><span class="sxs-lookup"><span data-stu-id="d987e-197">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d987e-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d987e-198">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="d987e-199">Operatore =</span><span class="sxs-lookup"><span data-stu-id="d987e-199">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="d987e-200">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d987e-200">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d987e-201">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="d987e-201">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d987e-202">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="d987e-202">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="d987e-203">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d987e-203">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
