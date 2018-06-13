---
title: Utilizzo dei tipi nullable (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: d2fe0f34c45d3de0516a71ca5ed4dc807df4bf93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336921"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="acbac-102">Utilizzo dei tipi nullable (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="acbac-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="acbac-103">I tipi nullable possono rappresentare tutti i valori di un tipo sottostante e un valore [null](../../../csharp/language-reference/keywords/null.md) aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="acbac-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="acbac-104">I tipi nullable vengono dichiarati in una delle due modalità riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="acbac-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="acbac-105">oppure</span><span class="sxs-lookup"><span data-stu-id="acbac-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="acbac-106">`T` è il tipo sottostante del tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="acbac-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="acbac-107">`T` può essere qualsiasi tipo di valore, incluso `struct`; non può essere un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="acbac-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="acbac-108">Per un esempio di quando è possibile usare un tipo nullable, considerare una comune variabile booleana che supporta solo due valori: true e false.</span><span class="sxs-lookup"><span data-stu-id="acbac-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="acbac-109">Non esiste alcun valore corrispondente a "non definito".</span><span class="sxs-lookup"><span data-stu-id="acbac-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="acbac-110">In molte applicazioni di programmazione, in particolare nelle interazioni tra database, le variabili possono avere uno stato non definito.</span><span class="sxs-lookup"><span data-stu-id="acbac-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="acbac-111">Ad esempio un campo di un database può contenere i valori true o false, ma può anche non contenere alcun valore.</span><span class="sxs-lookup"><span data-stu-id="acbac-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="acbac-112">Allo stesso modo è possibile impostare i tipi di riferimento su `null` per indicare che non sono inizializzati.</span><span class="sxs-lookup"><span data-stu-id="acbac-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="acbac-113">Questa disparità può comportare un lavoro di programmazione aggiuntivo e l'aggiunta di variabili per l'archiviazione delle informazioni sullo stato, dell'uso di valori speciali e così via.</span><span class="sxs-lookup"><span data-stu-id="acbac-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="acbac-114">Il modificatore del tipo nullable in C# consente di creare variabili di tipo valore che indicano un valore indefinito.</span><span class="sxs-lookup"><span data-stu-id="acbac-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="acbac-115">Esempi di tipi nullable</span><span class="sxs-lookup"><span data-stu-id="acbac-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="acbac-116">È possibile usare come base per un tipo nullable qualsiasi tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="acbac-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="acbac-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="acbac-117">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="acbac-118">Membri dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="acbac-118">The Members of Nullable Types</span></span>  
 <span data-ttu-id="acbac-119">Ogni istanza di un tipo nullable ha due proprietà pubbliche di sola lettura:</span><span class="sxs-lookup"><span data-stu-id="acbac-119">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="acbac-120">`HasValue` è di tipo `bool`.</span><span class="sxs-lookup"><span data-stu-id="acbac-120">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="acbac-121">È impostata su `true` quando la variabile contiene un valore diverso da null.</span><span class="sxs-lookup"><span data-stu-id="acbac-121">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="acbac-122">`Value` è dello stesso tipo del tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="acbac-122">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="acbac-123">Se `HasValue` è `true`, `Value` contiene un valore significativo.</span><span class="sxs-lookup"><span data-stu-id="acbac-123">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="acbac-124">Se `HasValue` è `false`, l'accesso a `Value` genera un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="acbac-124">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="acbac-125">In questo esempio il membro `HasValue` viene usato per verificare se la variabile contiene un valore prima che tenti di visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="acbac-125">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 <span data-ttu-id="acbac-126">La verifica della presenza del valore può anche essere eseguita come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="acbac-126">Testing for a value can also be done as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a><span data-ttu-id="acbac-127">Conversioni esplicite</span><span class="sxs-lookup"><span data-stu-id="acbac-127">Explicit Conversions</span></span>  
 <span data-ttu-id="acbac-128">È possibile eseguire il cast di un tipo nullable in un tipo normale, in modo esplicito tramite il cast o con la proprietà `Value`.</span><span class="sxs-lookup"><span data-stu-id="acbac-128">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="acbac-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="acbac-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 <span data-ttu-id="acbac-130">Se viene impostata una conversione definita dall'utente tra due tipi di dati, la stessa conversione può essere usata anche con le versioni nullable di questi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="acbac-130">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="acbac-131">Conversioni implicite</span><span class="sxs-lookup"><span data-stu-id="acbac-131">Implicit Conversions</span></span>  
 <span data-ttu-id="acbac-132">Una variabile di tipo nullable può essere impostata su null con la parola chiave `null`, come visualizzato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="acbac-132">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 <span data-ttu-id="acbac-133">La conversione da un tipo normale a un tipo nullable è implicita.</span><span class="sxs-lookup"><span data-stu-id="acbac-133">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 [!code-csharp[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a><span data-ttu-id="acbac-134">Operatori</span><span class="sxs-lookup"><span data-stu-id="acbac-134">Operators</span></span>  
 <span data-ttu-id="acbac-135">Gli operatori unari e binari predefiniti e gli eventuali operatori definiti dall'utente esistenti per i tipi di valore possono essere usati anche dai tipi nullable.</span><span class="sxs-lookup"><span data-stu-id="acbac-135">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="acbac-136">Questi operatori generano un valore null se gli operandi sono null. In caso contrario, l'operatore usa il valore contenuto per calcolare il risultato.</span><span class="sxs-lookup"><span data-stu-id="acbac-136">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="acbac-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="acbac-137">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 <span data-ttu-id="acbac-138">Quando si eseguono confronti con tipi nullable, se il valore di uno dei tipi nullable è null e l'altro non lo è, tutti i confronti restituiscono `false` ad eccezione di `!=` (diverso da).</span><span class="sxs-lookup"><span data-stu-id="acbac-138">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="acbac-139">È importante non presupporre che poiché un particolare confronto restituisce `false` il caso opposto restituirà `true`.</span><span class="sxs-lookup"><span data-stu-id="acbac-139">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="acbac-140">Nell'esempio seguente, 10 non è maggiore, minore né uguale a null.</span><span class="sxs-lookup"><span data-stu-id="acbac-140">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="acbac-141">Solo `num1 != num2` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="acbac-141">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 <span data-ttu-id="acbac-142">Un confronto di uguaglianza tra due tipi nullable che sono entrambi null restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="acbac-142">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="acbac-143">Operatore</span><span class="sxs-lookup"><span data-stu-id="acbac-143">The ??</span></span> <span data-ttu-id="acbac-144">??</span><span class="sxs-lookup"><span data-stu-id="acbac-144">Operator</span></span>  
 <span data-ttu-id="acbac-145">L'operatore `??` definisce un valore predefinito restituito quando un tipo nullable è assegnato a un tipo non nullable.</span><span class="sxs-lookup"><span data-stu-id="acbac-145">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 [!code-csharp[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 <span data-ttu-id="acbac-146">L'operatore può essere usato anche con più tipi nullable.</span><span class="sxs-lookup"><span data-stu-id="acbac-146">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="acbac-147">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="acbac-147">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a><span data-ttu-id="acbac-148">Tipo bool?</span><span class="sxs-lookup"><span data-stu-id="acbac-148">The bool? type</span></span>  
 <span data-ttu-id="acbac-149">Il tipo nullable `bool?` può contenere tre valori diversi: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) e [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="acbac-149">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="acbac-150">Per informazioni su come eseguire il cast da bool? a bool, vedere [Procedura: Eseguire il cast sicuro da bool? a bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span><span class="sxs-lookup"><span data-stu-id="acbac-150">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="acbac-151">I valori nullable booleani sono come il tipo di variabile booleano usato in SQL.</span><span class="sxs-lookup"><span data-stu-id="acbac-151">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="acbac-152">Per garantire che i risultati prodotti dagli operatori `&` e `|` siano coerenti con il tipo booleano a tre valori in SQL, sono disponibili gli operatori predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="acbac-152">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="acbac-153">Nella seguente tabella vengono elencati i risultati di questi operatori:</span><span class="sxs-lookup"><span data-stu-id="acbac-153">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="acbac-154">x</span><span class="sxs-lookup"><span data-stu-id="acbac-154">X</span></span>|<span data-ttu-id="acbac-155">y</span><span class="sxs-lookup"><span data-stu-id="acbac-155">y</span></span>|<span data-ttu-id="acbac-156">x&y</span><span class="sxs-lookup"><span data-stu-id="acbac-156">x&y</span></span>|<span data-ttu-id="acbac-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="acbac-157">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="acbac-158">true</span><span class="sxs-lookup"><span data-stu-id="acbac-158">true</span></span>|<span data-ttu-id="acbac-159">true</span><span class="sxs-lookup"><span data-stu-id="acbac-159">true</span></span>|<span data-ttu-id="acbac-160">true</span><span class="sxs-lookup"><span data-stu-id="acbac-160">true</span></span>|<span data-ttu-id="acbac-161">true</span><span class="sxs-lookup"><span data-stu-id="acbac-161">true</span></span>|  
|<span data-ttu-id="acbac-162">true</span><span class="sxs-lookup"><span data-stu-id="acbac-162">true</span></span>|<span data-ttu-id="acbac-163">False</span><span class="sxs-lookup"><span data-stu-id="acbac-163">false</span></span>|<span data-ttu-id="acbac-164">false</span><span class="sxs-lookup"><span data-stu-id="acbac-164">false</span></span>|<span data-ttu-id="acbac-165">true</span><span class="sxs-lookup"><span data-stu-id="acbac-165">true</span></span>|  
|<span data-ttu-id="acbac-166">true</span><span class="sxs-lookup"><span data-stu-id="acbac-166">true</span></span>|<span data-ttu-id="acbac-167">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-167">null</span></span>|<span data-ttu-id="acbac-168">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-168">null</span></span>|<span data-ttu-id="acbac-169">true</span><span class="sxs-lookup"><span data-stu-id="acbac-169">true</span></span>|  
|<span data-ttu-id="acbac-170">False</span><span class="sxs-lookup"><span data-stu-id="acbac-170">false</span></span>|<span data-ttu-id="acbac-171">true</span><span class="sxs-lookup"><span data-stu-id="acbac-171">true</span></span>|<span data-ttu-id="acbac-172">False</span><span class="sxs-lookup"><span data-stu-id="acbac-172">false</span></span>|<span data-ttu-id="acbac-173">true</span><span class="sxs-lookup"><span data-stu-id="acbac-173">true</span></span>|  
|<span data-ttu-id="acbac-174">False</span><span class="sxs-lookup"><span data-stu-id="acbac-174">false</span></span>|<span data-ttu-id="acbac-175">False</span><span class="sxs-lookup"><span data-stu-id="acbac-175">false</span></span>|<span data-ttu-id="acbac-176">False</span><span class="sxs-lookup"><span data-stu-id="acbac-176">false</span></span>|<span data-ttu-id="acbac-177">False</span><span class="sxs-lookup"><span data-stu-id="acbac-177">false</span></span>|  
|<span data-ttu-id="acbac-178">False</span><span class="sxs-lookup"><span data-stu-id="acbac-178">false</span></span>|<span data-ttu-id="acbac-179">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-179">null</span></span>|<span data-ttu-id="acbac-180">False</span><span class="sxs-lookup"><span data-stu-id="acbac-180">false</span></span>|<span data-ttu-id="acbac-181">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-181">null</span></span>|  
|<span data-ttu-id="acbac-182">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-182">null</span></span>|<span data-ttu-id="acbac-183">true</span><span class="sxs-lookup"><span data-stu-id="acbac-183">true</span></span>|<span data-ttu-id="acbac-184">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-184">null</span></span>|<span data-ttu-id="acbac-185">true</span><span class="sxs-lookup"><span data-stu-id="acbac-185">true</span></span>|  
|<span data-ttu-id="acbac-186">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-186">null</span></span>|<span data-ttu-id="acbac-187">False</span><span class="sxs-lookup"><span data-stu-id="acbac-187">false</span></span>|<span data-ttu-id="acbac-188">False</span><span class="sxs-lookup"><span data-stu-id="acbac-188">false</span></span>|<span data-ttu-id="acbac-189">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-189">null</span></span>|  
|<span data-ttu-id="acbac-190">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-190">null</span></span>|<span data-ttu-id="acbac-191">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-191">null</span></span>|<span data-ttu-id="acbac-192">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-192">null</span></span>|<span data-ttu-id="acbac-193">Null</span><span class="sxs-lookup"><span data-stu-id="acbac-193">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acbac-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acbac-194">See Also</span></span>  
 [<span data-ttu-id="acbac-195">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="acbac-195">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="acbac-196">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="acbac-196">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="acbac-197">Conversione boxing dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="acbac-197">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
 [<span data-ttu-id="acbac-198">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="acbac-198">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
