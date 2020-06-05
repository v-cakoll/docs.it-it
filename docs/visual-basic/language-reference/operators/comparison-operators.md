---
title: Operatori di confronto
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
ms.openlocfilehash: bcd51d70c5c7bd08991c7433e244316a82daa9da
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371791"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="85911-102">Operatori di confronto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85911-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="85911-103">Di seguito sono riportati gli operatori di confronto definiti in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="85911-103">The following are the comparison operators defined in Visual Basic.</span></span>

 <span data-ttu-id="85911-104">`<`operatore</span><span class="sxs-lookup"><span data-stu-id="85911-104">`<` operator</span></span>

 <span data-ttu-id="85911-105">`<=`operatore</span><span class="sxs-lookup"><span data-stu-id="85911-105">`<=` operator</span></span>

 <span data-ttu-id="85911-106">`>`operatore</span><span class="sxs-lookup"><span data-stu-id="85911-106">`>` operator</span></span>

 <span data-ttu-id="85911-107">`>=`operatore</span><span class="sxs-lookup"><span data-stu-id="85911-107">`>=` operator</span></span>

 <span data-ttu-id="85911-108">`=`operatore</span><span class="sxs-lookup"><span data-stu-id="85911-108">`=` operator</span></span>

 <span data-ttu-id="85911-109">`<>`operatore</span><span class="sxs-lookup"><span data-stu-id="85911-109">`<>` operator</span></span>

 [<span data-ttu-id="85911-110">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="85911-110">Is Operator</span></span>](is-operator.md)

 [<span data-ttu-id="85911-111">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="85911-111">IsNot Operator</span></span>](isnot-operator.md)

 [<span data-ttu-id="85911-112">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="85911-112">Like Operator</span></span>](like-operator.md)

 <span data-ttu-id="85911-113">Questi operatori confrontano due espressioni per determinare se sono uguali e, in caso contrario, come si differenziano.</span><span class="sxs-lookup"><span data-stu-id="85911-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="85911-114">`Is`, `IsNot` e `Like` vengono descritti in dettaglio nelle pagine della guida separate.</span><span class="sxs-lookup"><span data-stu-id="85911-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="85911-115">Gli operatori di confronto relazionali vengono descritti in dettaglio in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="85911-115">The relational comparison operators are discussed in detail on this page.</span></span>

## <a name="syntax"></a><span data-ttu-id="85911-116">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85911-116">Syntax</span></span>
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="85911-117">Parti</span><span class="sxs-lookup"><span data-stu-id="85911-117">Parts</span></span>
 `result`  
 <span data-ttu-id="85911-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="85911-118">Required.</span></span> <span data-ttu-id="85911-119">`Boolean`Valore che rappresenta il risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="85911-119">A `Boolean` value representing the result of the comparison.</span></span>

 <span data-ttu-id="85911-120">`expression1`, `expression2`</span><span class="sxs-lookup"><span data-stu-id="85911-120">`expression1`, `expression2`</span></span>  
 <span data-ttu-id="85911-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="85911-121">Required.</span></span> <span data-ttu-id="85911-122">Qualsiasi espressione.</span><span class="sxs-lookup"><span data-stu-id="85911-122">Any expression.</span></span>

 `comparisonoperator`  
 <span data-ttu-id="85911-123">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="85911-123">Required.</span></span> <span data-ttu-id="85911-124">Qualsiasi operatore di confronto relazionale.</span><span class="sxs-lookup"><span data-stu-id="85911-124">Any relational comparison operator.</span></span>

 <span data-ttu-id="85911-125">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="85911-125">`object1`, `object2`</span></span>  
 <span data-ttu-id="85911-126">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="85911-126">Required.</span></span> <span data-ttu-id="85911-127">Qualsiasi nome di oggetto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="85911-127">Any reference object names.</span></span>

 `string`  
 <span data-ttu-id="85911-128">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="85911-128">Required.</span></span> <span data-ttu-id="85911-129">Qualsiasi espressione `String` .</span><span class="sxs-lookup"><span data-stu-id="85911-129">Any `String` expression.</span></span>

 `pattern`  
 <span data-ttu-id="85911-130">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="85911-130">Required.</span></span> <span data-ttu-id="85911-131">Qualsiasi `String` espressione o intervallo di caratteri.</span><span class="sxs-lookup"><span data-stu-id="85911-131">Any `String` expression or range of characters.</span></span>

## <a name="remarks"></a><span data-ttu-id="85911-132">Commenti</span><span class="sxs-lookup"><span data-stu-id="85911-132">Remarks</span></span>
 <span data-ttu-id="85911-133">La tabella seguente contiene un elenco degli operatori di confronto relazionale e le condizioni che determinano se `result` è `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="85911-133">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>

|<span data-ttu-id="85911-134">Operatore</span><span class="sxs-lookup"><span data-stu-id="85911-134">Operator</span></span>|<span data-ttu-id="85911-135">`True` se</span><span class="sxs-lookup"><span data-stu-id="85911-135">`True` if</span></span>|<span data-ttu-id="85911-136">`False` se</span><span class="sxs-lookup"><span data-stu-id="85911-136">`False` if</span></span>|
|--------------|---------------|----------------|
|<span data-ttu-id="85911-137">`<`(Minore di)</span><span class="sxs-lookup"><span data-stu-id="85911-137">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|
|<span data-ttu-id="85911-138">`<=`(Minore o uguale a)</span><span class="sxs-lookup"><span data-stu-id="85911-138">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|
|<span data-ttu-id="85911-139">`>`(Maggiore di)</span><span class="sxs-lookup"><span data-stu-id="85911-139">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|
|<span data-ttu-id="85911-140">`>=`(Maggiore o uguale a)</span><span class="sxs-lookup"><span data-stu-id="85911-140">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|
|<span data-ttu-id="85911-141">`=`(Uguale a)</span><span class="sxs-lookup"><span data-stu-id="85911-141">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|
|<span data-ttu-id="85911-142">`<>`(Diverso da)</span><span class="sxs-lookup"><span data-stu-id="85911-142">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> <span data-ttu-id="85911-143">L' [operatore =](assignment-operator.md) viene utilizzato anche come operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="85911-143">The [= Operator](assignment-operator.md) is also used as an assignment operator.</span></span>

 <span data-ttu-id="85911-144">L'operatore `Is` , l'operatore `IsNot` e l' `Like` operatore hanno funzionalità di confronto specifiche che differiscono dagli operatori della tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="85911-144">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>

## <a name="comparing-numbers"></a><span data-ttu-id="85911-145">Confronto di numeri</span><span class="sxs-lookup"><span data-stu-id="85911-145">Comparing Numbers</span></span>
 <span data-ttu-id="85911-146">Quando si confronta un'espressione di tipo `Single` con una di tipo `Double` , l' `Single` espressione viene convertita in `Double` .</span><span class="sxs-lookup"><span data-stu-id="85911-146">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="85911-147">Questo comportamento è opposto al comportamento trovato nella Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="85911-147">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>

 <span data-ttu-id="85911-148">Analogamente, quando si confronta un'espressione di tipo `Decimal` con un'espressione di tipo `Single` o `Double` , l' `Decimal` espressione viene convertita in `Single` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="85911-148">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="85911-149">Per `Decimal` le espressioni, qualsiasi valore frazionario minore di 1E-28 potrebbe andare perduto.</span><span class="sxs-lookup"><span data-stu-id="85911-149">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="85911-150">Tale perdita di valori frazionari può causare il confronto di due valori come uguali quando non lo sono.</span><span class="sxs-lookup"><span data-stu-id="85911-150">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="85911-151">Per questo motivo, è necessario prestare attenzione quando si usa l'uguaglianza ( `=` ) per confrontare due variabili a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="85911-151">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="85911-152">È più sicuro verificare se il valore assoluto della differenza tra i due numeri è inferiore a una piccola tolleranza accettabile.</span><span class="sxs-lookup"><span data-stu-id="85911-152">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>

### <a name="floating-point-imprecision"></a><span data-ttu-id="85911-153">Imprecisione a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="85911-153">Floating-point Imprecision</span></span>
 <span data-ttu-id="85911-154">Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione precisa in memoria.</span><span class="sxs-lookup"><span data-stu-id="85911-154">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="85911-155">Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l' [operatore mod](mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="85911-155">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](mod-operator.md).</span></span> <span data-ttu-id="85911-156">Per ulteriori informazioni, vedere [risoluzione dei problemi](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="85911-156">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="comparing-strings"></a><span data-ttu-id="85911-157">Confronto di stringhe</span><span class="sxs-lookup"><span data-stu-id="85911-157">Comparing Strings</span></span>
 <span data-ttu-id="85911-158">Quando si confrontano le stringhe, le espressioni stringa vengono valutate in base al relativo ordinamento alfabetico, che dipende dall' `Option Compare` impostazione.</span><span class="sxs-lookup"><span data-stu-id="85911-158">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>

 <span data-ttu-id="85911-159">`Option Compare Binary`basa i confronti tra stringhe in base a un ordinamento derivato dalle rappresentazioni binarie interne dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="85911-159">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="85911-160">Il tipo di ordinamento è determinato dalla tabella codici.</span><span class="sxs-lookup"><span data-stu-id="85911-160">The sort order is determined by the code page.</span></span> <span data-ttu-id="85911-161">Nell'esempio seguente viene illustrato un tipico ordinamento binario.</span><span class="sxs-lookup"><span data-stu-id="85911-161">The following example shows a typical binary sort order.</span></span>

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 <span data-ttu-id="85911-162">`Option Compare Text`basa i confronti tra stringhe in base a un ordinamento testuale senza distinzione tra maiuscole e minuscole determinato dalle impostazioni locali dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="85911-162">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="85911-163">Quando si impostano `Option Compare Text` e ordinano i caratteri nell'esempio precedente, viene applicato l'ordinamento del testo seguente:</span><span class="sxs-lookup"><span data-stu-id="85911-163">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a><span data-ttu-id="85911-164">Dipendenza dalle impostazioni locali</span><span class="sxs-lookup"><span data-stu-id="85911-164">Locale Dependence</span></span>
 <span data-ttu-id="85911-165">Quando si imposta `Option Compare Text` , il risultato di un confronto tra stringhe può dipendere dalle impostazioni locali in cui l'applicazione è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="85911-165">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="85911-166">Due caratteri possono essere paragonati come uguali in un'unica impostazione locale ma non in un'altra.</span><span class="sxs-lookup"><span data-stu-id="85911-166">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="85911-167">Se si utilizza un confronto tra stringhe per prendere decisioni importanti, ad esempio se si desidera accettare un tentativo di accesso, è necessario ricevere un avviso per la riservatezza delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="85911-167">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="85911-168">Prendere in considerazione `Option Compare Binary` l'impostazione o la chiamata di <xref:Microsoft.VisualBasic.Strings.StrComp%2A> , che prende in considerazione le impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="85911-168">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>

## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="85911-169">Programmazione senza tipo con operatori di confronto relazionali</span><span class="sxs-lookup"><span data-stu-id="85911-169">Typeless Programming with Relational Comparison Operators</span></span>
 <span data-ttu-id="85911-170">L'utilizzo di operatori di confronto relazionali con `Object` espressioni non è consentito in `Option Strict On` .</span><span class="sxs-lookup"><span data-stu-id="85911-170">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="85911-171">Quando `Option Strict` è `Off` e `expression1` o `expression2` è un' `Object` espressione, i tipi in fase di esecuzione determinano il modo in cui vengono confrontati.</span><span class="sxs-lookup"><span data-stu-id="85911-171">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="85911-172">Nella tabella seguente viene illustrata la modalità di confronto delle espressioni e il risultato del confronto, a seconda del tipo di runtime degli operandi.</span><span class="sxs-lookup"><span data-stu-id="85911-172">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>

|<span data-ttu-id="85911-173">Se gli operandi sono</span><span class="sxs-lookup"><span data-stu-id="85911-173">If operands are</span></span>|<span data-ttu-id="85911-174">Il confronto è</span><span class="sxs-lookup"><span data-stu-id="85911-174">Comparison is</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="85911-175">Sia`String`</span><span class="sxs-lookup"><span data-stu-id="85911-175">Both `String`</span></span>|<span data-ttu-id="85911-176">Confronto di ordinamento basato sulle caratteristiche di ordinamento delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="85911-176">Sort comparison based on string sorting characteristics.</span></span>|
|<span data-ttu-id="85911-177">Entrambi numerici</span><span class="sxs-lookup"><span data-stu-id="85911-177">Both numeric</span></span>|<span data-ttu-id="85911-178">Oggetti convertiti in `Double` , confronto numerico.</span><span class="sxs-lookup"><span data-stu-id="85911-178">Objects converted to `Double`, numeric comparison.</span></span>|
|<span data-ttu-id="85911-179">Uno numerico e uno`String`</span><span class="sxs-lookup"><span data-stu-id="85911-179">One numeric and one `String`</span></span>|<span data-ttu-id="85911-180">`String`Viene convertito in un oggetto `Double` e il confronto numerico viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="85911-180">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="85911-181">Se `String` non è possibile convertire in `Double` , <xref:System.InvalidCastException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="85911-181">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|
|<span data-ttu-id="85911-182">Uno o entrambi sono tipi di riferimento diversi da`String`</span><span class="sxs-lookup"><span data-stu-id="85911-182">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="85911-183">Viene generato un tipo <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="85911-183">An <xref:System.InvalidCastException> is thrown.</span></span>|

 <span data-ttu-id="85911-184">I confronti numerici considerano `Nothing` come 0.</span><span class="sxs-lookup"><span data-stu-id="85911-184">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="85911-185">I confronti di stringhe considerano `Nothing` come `""` (una stringa vuota).</span><span class="sxs-lookup"><span data-stu-id="85911-185">String comparisons treat `Nothing` as `""` (an empty string).</span></span>

## <a name="overloading"></a><span data-ttu-id="85911-186">Overload</span><span class="sxs-lookup"><span data-stu-id="85911-186">Overloading</span></span>
 <span data-ttu-id="85911-187">Operatori di confronto relazionale ( `<` .</span><span class="sxs-lookup"><span data-stu-id="85911-187">The relational comparison operators (`<`.</span></span> <span data-ttu-id="85911-188">`<=`, `>` , `>=` , `=` , `<>` ) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="85911-188">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="85911-189">Se il codice usa uno di questi operatori in una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="85911-189">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="85911-190">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="85911-190">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

 <span data-ttu-id="85911-191">Si noti che è possibile eseguire l'overload dell' [operatore =](assignment-operator.md) solo come operatore di confronto relazionale, non come operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="85911-191">Notice that the [= Operator](assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>

## <a name="example"></a><span data-ttu-id="85911-192">Esempio</span><span class="sxs-lookup"><span data-stu-id="85911-192">Example</span></span>
 <span data-ttu-id="85911-193">Nell'esempio seguente vengono illustrati diversi utilizzi degli operatori di confronto relazionali, utilizzati per confrontare le espressioni.</span><span class="sxs-lookup"><span data-stu-id="85911-193">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="85911-194">Gli operatori di confronto relazionale restituiscono un `Boolean` risultato che indica se l'espressione specificata restituisce o meno `True` .</span><span class="sxs-lookup"><span data-stu-id="85911-194">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="85911-195">Quando si applicano `>` gli `<` operatori e alle stringhe, il confronto viene eseguito usando il normale ordinamento alfabetico delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="85911-195">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="85911-196">Questo ordine può dipendere dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="85911-196">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="85911-197">Indica se l'ordinamento fa distinzione tra maiuscole e minuscole o non dipende dall'impostazione [Option Compare](../statements/option-compare-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="85911-197">Whether the sort is case-sensitive or not depends on the [Option Compare](../statements/option-compare-statement.md) setting.</span></span>

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 <span data-ttu-id="85911-198">Nell'esempio precedente, il primo confronto restituisce `False` e i restanti confronti restituiscono `True` .</span><span class="sxs-lookup"><span data-stu-id="85911-198">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>

## <a name="see-also"></a><span data-ttu-id="85911-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85911-199">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="85911-200">= (Operatore)</span><span class="sxs-lookup"><span data-stu-id="85911-200">= Operator</span></span>](assignment-operator.md)
- [<span data-ttu-id="85911-201">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85911-201">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="85911-202">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="85911-202">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="85911-203">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="85911-203">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="85911-204">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85911-204">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
