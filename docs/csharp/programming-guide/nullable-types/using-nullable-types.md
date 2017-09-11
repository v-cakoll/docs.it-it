---
title: Utilizzo dei tipi nullable (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0721d9f60abc4e158135d6b050953b3e63ab8cb5
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="2491a-102">Utilizzo dei tipi nullable (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2491a-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="2491a-103">I tipi nullable possono rappresentare tutti i valori di un tipo sottostante e un valore [null](../../../csharp/language-reference/keywords/null.md) aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="2491a-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="2491a-104">I tipi nullable vengono dichiarati in una delle due modalità riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="2491a-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="2491a-105">-oppure-</span><span class="sxs-lookup"><span data-stu-id="2491a-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="2491a-106">`T` è il tipo sottostante del tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="2491a-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="2491a-107">`T` può essere qualsiasi tipo di valore, incluso `struct`; non può essere un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="2491a-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="2491a-108">Per un esempio di quando è possibile usare un tipo nullable, considerare una comune variabile booleana che supporta solo due valori: true e false.</span><span class="sxs-lookup"><span data-stu-id="2491a-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="2491a-109">Non esiste alcun valore corrispondente a "non definito".</span><span class="sxs-lookup"><span data-stu-id="2491a-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="2491a-110">In molte applicazioni di programmazione, in particolare nelle interazioni tra database, le variabili possono avere uno stato non definito.</span><span class="sxs-lookup"><span data-stu-id="2491a-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="2491a-111">Ad esempio un campo di un database può contenere i valori true o false, ma può anche non contenere alcun valore.</span><span class="sxs-lookup"><span data-stu-id="2491a-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="2491a-112">Allo stesso modo è possibile impostare i tipi di riferimento su `null` per indicare che non sono inizializzati.</span><span class="sxs-lookup"><span data-stu-id="2491a-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="2491a-113">Questa disparità può comportare un lavoro di programmazione aggiuntivo e l'aggiunta di variabili per l'archiviazione delle informazioni sullo stato, dell'uso di valori speciali e così via.</span><span class="sxs-lookup"><span data-stu-id="2491a-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="2491a-114">Il modificatore del tipo nullable in C# consente di creare variabili di tipo valore che indicano un valore indefinito.</span><span class="sxs-lookup"><span data-stu-id="2491a-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="2491a-115">Esempi di tipi nullable</span><span class="sxs-lookup"><span data-stu-id="2491a-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="2491a-116">È possibile usare come base per un tipo nullable qualsiasi tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="2491a-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="2491a-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2491a-117">For example:</span></span>  
  
 <span data-ttu-id="2491a-118">[!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2491a-118">[!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]</span></span>  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="2491a-119">Membri dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="2491a-119">The Members of Nullable Types</span></span>  
 <span data-ttu-id="2491a-120">Ogni istanza di un tipo nullable ha due proprietà pubbliche di sola lettura:</span><span class="sxs-lookup"><span data-stu-id="2491a-120">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="2491a-121">`HasValue` è di tipo `bool`.</span><span class="sxs-lookup"><span data-stu-id="2491a-121">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="2491a-122">È impostata su `true` quando la variabile contiene un valore diverso da null.</span><span class="sxs-lookup"><span data-stu-id="2491a-122">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="2491a-123">`Value` è dello stesso tipo del tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="2491a-123">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="2491a-124">Se `HasValue` è `true`, `Value` contiene un valore significativo.</span><span class="sxs-lookup"><span data-stu-id="2491a-124">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="2491a-125">Se `HasValue` è `false`, l'accesso a `Value` genera un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="2491a-125">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="2491a-126">In questo esempio il membro `HasValue` viene usato per verificare se la variabile contiene un valore prima che tenti di visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="2491a-126">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 <span data-ttu-id="2491a-127">[!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2491a-127">[!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]</span></span>  
  
 <span data-ttu-id="2491a-128">La verifica della presenza del valore può anche essere eseguita come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2491a-128">Testing for a value can also be done as in the following example:</span></span>  
  
 <span data-ttu-id="2491a-129">[!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="2491a-129">[!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]</span></span>  
  
## <a name="explicit-conversions"></a><span data-ttu-id="2491a-130">Conversioni esplicite</span><span class="sxs-lookup"><span data-stu-id="2491a-130">Explicit Conversions</span></span>  
 <span data-ttu-id="2491a-131">È possibile eseguire il cast di un tipo nullable in un tipo normale, in modo esplicito tramite il cast o con la proprietà `Value`.</span><span class="sxs-lookup"><span data-stu-id="2491a-131">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="2491a-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2491a-132">For example:</span></span>  
  
 <span data-ttu-id="2491a-133">[!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="2491a-133">[!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]</span></span>  
  
 <span data-ttu-id="2491a-134">Se viene impostata una conversione definita dall'utente tra due tipi di dati, la stessa conversione può essere usata anche con le versioni nullable di questi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="2491a-134">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="2491a-135">Conversioni implicite</span><span class="sxs-lookup"><span data-stu-id="2491a-135">Implicit Conversions</span></span>  
 <span data-ttu-id="2491a-136">Una variabile di tipo nullable può essere impostata su null con la parola chiave `null`, come visualizzato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2491a-136">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 <span data-ttu-id="2491a-137">[!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="2491a-137">[!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]</span></span>  
  
 <span data-ttu-id="2491a-138">La conversione da un tipo normale a un tipo nullable è implicita.</span><span class="sxs-lookup"><span data-stu-id="2491a-138">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 <span data-ttu-id="2491a-139">[!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="2491a-139">[!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]</span></span>  
  
## <a name="operators"></a><span data-ttu-id="2491a-140">Operatori</span><span class="sxs-lookup"><span data-stu-id="2491a-140">Operators</span></span>  
 <span data-ttu-id="2491a-141">Gli operatori unari e binari predefiniti e gli eventuali operatori definiti dall'utente esistenti per i tipi di valore possono essere usati anche dai tipi nullable.</span><span class="sxs-lookup"><span data-stu-id="2491a-141">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="2491a-142">Questi operatori generano un valore null se gli operandi sono null. In caso contrario, l'operatore usa il valore contenuto per calcolare il risultato.</span><span class="sxs-lookup"><span data-stu-id="2491a-142">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="2491a-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2491a-143">For example:</span></span>  
  
 <span data-ttu-id="2491a-144">[!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="2491a-144">[!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]</span></span>  
  
 <span data-ttu-id="2491a-145">Quando si eseguono confronti con tipi nullable, se il valore di uno dei tipi nullable è null e l'altro non lo è, tutti i confronti restituiscono `false` ad eccezione di `!=` (diverso da).</span><span class="sxs-lookup"><span data-stu-id="2491a-145">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="2491a-146">È importante non presupporre che poiché un particolare confronto restituisce `false` il caso opposto restituirà `true`.</span><span class="sxs-lookup"><span data-stu-id="2491a-146">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="2491a-147">Nell'esempio seguente, 10 non è maggiore, minore né uguale a null.</span><span class="sxs-lookup"><span data-stu-id="2491a-147">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="2491a-148">Solo `num1 != num2` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="2491a-148">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 <span data-ttu-id="2491a-149">[!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="2491a-149">[!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]</span></span>  
  
 <span data-ttu-id="2491a-150">Un confronto di uguaglianza tra due tipi nullable che sono entrambi null restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="2491a-150">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="2491a-151">Operatore</span><span class="sxs-lookup"><span data-stu-id="2491a-151">The ??</span></span> <span data-ttu-id="2491a-152">??</span><span class="sxs-lookup"><span data-stu-id="2491a-152">Operator</span></span>  
 <span data-ttu-id="2491a-153">L'operatore `??` definisce un valore predefinito restituito quando un tipo nullable è assegnato a un tipo non nullable.</span><span class="sxs-lookup"><span data-stu-id="2491a-153">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 <span data-ttu-id="2491a-154">[!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="2491a-154">[!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]</span></span>  
  
 <span data-ttu-id="2491a-155">L'operatore può essere usato anche con più tipi nullable.</span><span class="sxs-lookup"><span data-stu-id="2491a-155">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="2491a-156">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2491a-156">For example:</span></span>  
  
 <span data-ttu-id="2491a-157">[!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="2491a-157">[!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]</span></span>  
  
## <a name="the-bool-type"></a><span data-ttu-id="2491a-158">Tipo bool?</span><span class="sxs-lookup"><span data-stu-id="2491a-158">The bool? type</span></span>  
 <span data-ttu-id="2491a-159">Il tipo nullable `bool?` può contenere tre valori diversi: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) e [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="2491a-159">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="2491a-160">Per informazioni su come eseguire il cast da bool? a bool, vedere [Procedura: Eseguire il cast sicuro da bool? a bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span><span class="sxs-lookup"><span data-stu-id="2491a-160">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="2491a-161">I valori nullable booleani sono come il tipo di variabile booleano usato in SQL.</span><span class="sxs-lookup"><span data-stu-id="2491a-161">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="2491a-162">Per garantire che i risultati prodotti dagli operatori `&` e `|` siano coerenti con il tipo booleano a tre valori in SQL, sono disponibili gli operatori predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2491a-162">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="2491a-163">Nella seguente tabella vengono elencati i risultati di questi operatori:</span><span class="sxs-lookup"><span data-stu-id="2491a-163">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="2491a-164">X</span><span class="sxs-lookup"><span data-stu-id="2491a-164">X</span></span>|<span data-ttu-id="2491a-165">y</span><span class="sxs-lookup"><span data-stu-id="2491a-165">y</span></span>|<span data-ttu-id="2491a-166">x&y</span><span class="sxs-lookup"><span data-stu-id="2491a-166">x&y</span></span>|<span data-ttu-id="2491a-167">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="2491a-167">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="2491a-168">true</span><span class="sxs-lookup"><span data-stu-id="2491a-168">true</span></span>|<span data-ttu-id="2491a-169">true</span><span class="sxs-lookup"><span data-stu-id="2491a-169">true</span></span>|<span data-ttu-id="2491a-170">true</span><span class="sxs-lookup"><span data-stu-id="2491a-170">true</span></span>|<span data-ttu-id="2491a-171">true</span><span class="sxs-lookup"><span data-stu-id="2491a-171">true</span></span>|  
|<span data-ttu-id="2491a-172">true</span><span class="sxs-lookup"><span data-stu-id="2491a-172">true</span></span>|<span data-ttu-id="2491a-173">false</span><span class="sxs-lookup"><span data-stu-id="2491a-173">false</span></span>|<span data-ttu-id="2491a-174">false</span><span class="sxs-lookup"><span data-stu-id="2491a-174">false</span></span>|<span data-ttu-id="2491a-175">true</span><span class="sxs-lookup"><span data-stu-id="2491a-175">true</span></span>|  
|<span data-ttu-id="2491a-176">true</span><span class="sxs-lookup"><span data-stu-id="2491a-176">true</span></span>|<span data-ttu-id="2491a-177">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-177">null</span></span>|<span data-ttu-id="2491a-178">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-178">null</span></span>|<span data-ttu-id="2491a-179">true</span><span class="sxs-lookup"><span data-stu-id="2491a-179">true</span></span>|  
|<span data-ttu-id="2491a-180">false</span><span class="sxs-lookup"><span data-stu-id="2491a-180">false</span></span>|<span data-ttu-id="2491a-181">true</span><span class="sxs-lookup"><span data-stu-id="2491a-181">true</span></span>|<span data-ttu-id="2491a-182">false</span><span class="sxs-lookup"><span data-stu-id="2491a-182">false</span></span>|<span data-ttu-id="2491a-183">true</span><span class="sxs-lookup"><span data-stu-id="2491a-183">true</span></span>|  
|<span data-ttu-id="2491a-184">false</span><span class="sxs-lookup"><span data-stu-id="2491a-184">false</span></span>|<span data-ttu-id="2491a-185">false</span><span class="sxs-lookup"><span data-stu-id="2491a-185">false</span></span>|<span data-ttu-id="2491a-186">false</span><span class="sxs-lookup"><span data-stu-id="2491a-186">false</span></span>|<span data-ttu-id="2491a-187">false</span><span class="sxs-lookup"><span data-stu-id="2491a-187">false</span></span>|  
|<span data-ttu-id="2491a-188">false</span><span class="sxs-lookup"><span data-stu-id="2491a-188">false</span></span>|<span data-ttu-id="2491a-189">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-189">null</span></span>|<span data-ttu-id="2491a-190">false</span><span class="sxs-lookup"><span data-stu-id="2491a-190">false</span></span>|<span data-ttu-id="2491a-191">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-191">null</span></span>|  
|<span data-ttu-id="2491a-192">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-192">null</span></span>|<span data-ttu-id="2491a-193">true</span><span class="sxs-lookup"><span data-stu-id="2491a-193">true</span></span>|<span data-ttu-id="2491a-194">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-194">null</span></span>|<span data-ttu-id="2491a-195">true</span><span class="sxs-lookup"><span data-stu-id="2491a-195">true</span></span>|  
|<span data-ttu-id="2491a-196">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-196">null</span></span>|<span data-ttu-id="2491a-197">false</span><span class="sxs-lookup"><span data-stu-id="2491a-197">false</span></span>|<span data-ttu-id="2491a-198">false</span><span class="sxs-lookup"><span data-stu-id="2491a-198">false</span></span>|<span data-ttu-id="2491a-199">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-199">null</span></span>|  
|<span data-ttu-id="2491a-200">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-200">null</span></span>|<span data-ttu-id="2491a-201">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-201">null</span></span>|<span data-ttu-id="2491a-202">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-202">null</span></span>|<span data-ttu-id="2491a-203">Null</span><span class="sxs-lookup"><span data-stu-id="2491a-203">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2491a-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2491a-204">See Also</span></span>  
 <span data-ttu-id="2491a-205">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2491a-205">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2491a-206">[Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="2491a-206">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 <span data-ttu-id="2491a-207">[Conversione boxing dei tipi nullable](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md) </span><span class="sxs-lookup"><span data-stu-id="2491a-207">[Boxing Nullable Types](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md) </span></span>  
 [<span data-ttu-id="2491a-208">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="2491a-208">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)

