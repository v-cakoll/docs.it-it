---
title: 'Operatori C#'
ms.date: 04/04/2018
f1_keywords:
  - cs.operators
helpviewer_keywords:
  - 'boolean operators [C#]'
  - 'expressions [C#], operators'
  - 'logical operators [C#]'
  - 'operators [C#]'
  - 'Visual C#, operators'
  - 'indirection operators [C#]'
  - 'assignment operators [C#]'
  - 'shift operators [C#]'
  - 'relational operators [C#]'
  - 'bitwise operators [C#]'
  - 'address operators [C#]'
  - 'keywords [C#], operators'
  - 'arithmetic operators [C#]'
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
---
# <a name="c-operators"></a><span data-ttu-id="f5999-102">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="f5999-102">C# operators</span></span>

<span data-ttu-id="f5999-103">C# fornisce diversi operatori, ovvero simboli che specificano quali operazioni (matematiche, indicizzazione, chiamate di funzione e così via) eseguire in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="f5999-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="f5999-104">È possibile eseguire l'[overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) di diversi operatori per cambiarne il significato quando vengono applicati a un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f5999-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="f5999-105">Le operazioni sui tipi integrali (come `==`, `!=`, `<`, `>`, `&`, `|`) sono generalmente consentite sui tipi di enumerazione (`enum`).</span><span class="sxs-lookup"><span data-stu-id="f5999-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="f5999-106">Le sezioni seguenti elencano gli operatori C# da quelli con la precedenza più alta a quelli con la più bassa.</span><span class="sxs-lookup"><span data-stu-id="f5999-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="f5999-107">Gli operatori di ogni sezione condividono lo stesso livello di precedenza.</span><span class="sxs-lookup"><span data-stu-id="f5999-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="f5999-108">Operatori primari</span><span class="sxs-lookup"><span data-stu-id="f5999-108">Primary operators</span></span>

<span data-ttu-id="f5999-109">Sono gli operatori con la precedenza più alta.</span><span class="sxs-lookup"><span data-stu-id="f5999-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="f5999-110">[x.y](member-access-operator.md): accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="f5999-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="f5999-111">[x?.y](null-conditional-operators.md): accesso ai membri condizionali null.</span><span class="sxs-lookup"><span data-stu-id="f5999-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="f5999-112">Restituisce `null` se l'operando sul lato sinistro è `null`.</span><span class="sxs-lookup"><span data-stu-id="f5999-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="f5999-113">[x?[y]](null-conditional-operators.md): accesso all'indice condizionale null.</span><span class="sxs-lookup"><span data-stu-id="f5999-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="f5999-114">Restituisce `null` se l'operando sul lato sinistro è `null`.</span><span class="sxs-lookup"><span data-stu-id="f5999-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="f5999-115">[f(x)](invocation-operator.md): chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="f5999-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="f5999-116">[a&#91;x&#93;](index-operator.md): indicizzazione oggetto aggregato.</span><span class="sxs-lookup"><span data-stu-id="f5999-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="f5999-117">[x++](arithmetic-operators.md#increment-operator-): incremento suffisso.</span><span class="sxs-lookup"><span data-stu-id="f5999-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="f5999-118">Restituisce il valore di x e quindi aggiorna la posizione di archiviazione con il valore di x che risulta maggiore (in genere aggiunge il numero intero 1).</span><span class="sxs-lookup"><span data-stu-id="f5999-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="f5999-119">[x--](arithmetic-operators.md#decrement-operator---): decremento suffisso.</span><span class="sxs-lookup"><span data-stu-id="f5999-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="f5999-120">Restituisce il valore di x e quindi aggiorna la posizione di archiviazione con il valore di x che risulta minore (in genere sottrae il numero intero 1).</span><span class="sxs-lookup"><span data-stu-id="f5999-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="f5999-121">[new](../keywords/new-operator.md): creazione di un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="f5999-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="f5999-122">[typeof](../keywords/typeof.md): restituisce l'oggetto <xref:System.Type> che rappresenta l'operando.</span><span class="sxs-lookup"><span data-stu-id="f5999-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="f5999-123">[checked](../keywords/checked.md): abilita il controllo di overflow per le operazioni con numeri interi.</span><span class="sxs-lookup"><span data-stu-id="f5999-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="f5999-124">[unchecked](../keywords/unchecked.md): disabilita il controllo di overflow per le operazioni con numeri interi.</span><span class="sxs-lookup"><span data-stu-id="f5999-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="f5999-125">Questo è il comportamento predefinito per il compilatore.</span><span class="sxs-lookup"><span data-stu-id="f5999-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="f5999-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md): genera il valore predefinito del tipo T.</span><span class="sxs-lookup"><span data-stu-id="f5999-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="f5999-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md): dichiara e restituisce un'istanza di delegato.</span><span class="sxs-lookup"><span data-stu-id="f5999-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="f5999-128">[sizeof](../keywords/sizeof.md): restituisce le dimensioni in byte dell'operando type.</span><span class="sxs-lookup"><span data-stu-id="f5999-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="f5999-129">[->](dereference-operator.md): dereferenziazione puntatore combinata con l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="f5999-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="f5999-130">Operatori unari</span><span class="sxs-lookup"><span data-stu-id="f5999-130">Unary operators</span></span>

<span data-ttu-id="f5999-131">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-132">[+x](addition-operator.md): restituisce il valore di x.</span><span class="sxs-lookup"><span data-stu-id="f5999-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="f5999-133">[-x](subtraction-operator.md): negazione numerica.</span><span class="sxs-lookup"><span data-stu-id="f5999-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="f5999-134">[\!x](logical-negation-operator.md): negazione logica.</span><span class="sxs-lookup"><span data-stu-id="f5999-134">[\!x](logical-negation-operator.md) – logical negation.</span></span>

<span data-ttu-id="f5999-135">[~x](bitwise-complement-operator.md): complemento bit per bit.</span><span class="sxs-lookup"><span data-stu-id="f5999-135">[~x](bitwise-complement-operator.md) – bitwise complement.</span></span>

<span data-ttu-id="f5999-136">[~x](arithmetic-operators.md#increment-operator-): incremento prefisso.</span><span class="sxs-lookup"><span data-stu-id="f5999-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="f5999-137">Restituisce il valore di x dopo avere aggiornato la posizione di archiviazione con il valore di x che risulta maggiore (in genere aggiunge il numero intero 1).</span><span class="sxs-lookup"><span data-stu-id="f5999-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="f5999-138">[--x](arithmetic-operators.md#decrement-operator---): decremento prefisso.</span><span class="sxs-lookup"><span data-stu-id="f5999-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="f5999-139">Restituisce il valore di x dopo avere aggiornato la posizione di archiviazione con il valore di x che risulta minore (in genere sottrae il numero intero 1).</span><span class="sxs-lookup"><span data-stu-id="f5999-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="f5999-140">[(T)x](invocation-operator.md): cast di tipo.</span><span class="sxs-lookup"><span data-stu-id="f5999-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="f5999-141">[await](../keywords/await.md): attende un oggetto `Task`.</span><span class="sxs-lookup"><span data-stu-id="f5999-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="f5999-142">[&x](and-operator.md): indirizzo.</span><span class="sxs-lookup"><span data-stu-id="f5999-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="f5999-143">[\*x](multiplication-operator.md): dereferenziazione.</span><span class="sxs-lookup"><span data-stu-id="f5999-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="f5999-144">Operatori moltiplicativi</span><span class="sxs-lookup"><span data-stu-id="f5999-144">Multiplicative operators</span></span>

<span data-ttu-id="f5999-145">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-145">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-146">[x \* y](arithmetic-operators.md#multiplication-operator-): moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="f5999-146">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="f5999-147">[x / y](arithmetic-operators.md#division-operator-): divisione.</span><span class="sxs-lookup"><span data-stu-id="f5999-147">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="f5999-148">Se gli operandi sono numeri interi, il risultato è un numero intero troncato verso zero (ad esempio, `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="f5999-148">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="f5999-149">[x % y](arithmetic-operators.md#remainder-operator-): resto.</span><span class="sxs-lookup"><span data-stu-id="f5999-149">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="f5999-150">Se gli operandi sono numeri interi, restituisce il resto della divisione di x per y.</span><span class="sxs-lookup"><span data-stu-id="f5999-150">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="f5999-151">Se `q = x / y` e `r = x % y`, allora `x = q * y + r` </span><span class="sxs-lookup"><span data-stu-id="f5999-151">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="f5999-152">Operatori additivi</span><span class="sxs-lookup"><span data-stu-id="f5999-152">Additive operators</span></span>

<span data-ttu-id="f5999-153">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-153">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-154">[x + y](arithmetic-operators.md#addition-operator-): addizione.</span><span class="sxs-lookup"><span data-stu-id="f5999-154">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="f5999-155">[x – y](arithmetic-operators.md#subtraction-operator--): sottrazione.</span><span class="sxs-lookup"><span data-stu-id="f5999-155">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="f5999-156">Operatori shift</span><span class="sxs-lookup"><span data-stu-id="f5999-156">Shift operators</span></span>

<span data-ttu-id="f5999-157">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-157">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-158">[x <\<  y](left-shift-operator.md): spostamento dei bit a sinistra e inserimento di zero a destra.</span><span class="sxs-lookup"><span data-stu-id="f5999-158">[x <\<  y](left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="f5999-159">[x >> y](right-shift-operator.md): spostamento dei bit a destra.</span><span class="sxs-lookup"><span data-stu-id="f5999-159">[x >> y](right-shift-operator.md) – shift bits right.</span></span> <span data-ttu-id="f5999-160">Se l'operando di sinistra è `int` o `long`, i bit di sinistra vengono riempiti con il bit più significativo.</span><span class="sxs-lookup"><span data-stu-id="f5999-160">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="f5999-161">Se l'operando di sinistra è `uint` o `ulong`, i bit di sinistra vengono riempiti con zero.</span><span class="sxs-lookup"><span data-stu-id="f5999-161">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="f5999-162">Operatori relazionali e operatori di test del tipo</span><span class="sxs-lookup"><span data-stu-id="f5999-162">Relational and type-testing operators</span></span>

<span data-ttu-id="f5999-163">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-163">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-164">[x \< y](less-than-operator.md): minore di (true se x è minore di y).</span><span class="sxs-lookup"><span data-stu-id="f5999-164">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="f5999-165">[x > y](greater-than-operator.md): maggiore di (true se x è maggiore di y).</span><span class="sxs-lookup"><span data-stu-id="f5999-165">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="f5999-166">[x \<= y](less-than-equal-operator.md): minore o uguale a.</span><span class="sxs-lookup"><span data-stu-id="f5999-166">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="f5999-167">[x >= y](greater-than-equal-operator.md): maggiore o uguale a.</span><span class="sxs-lookup"><span data-stu-id="f5999-167">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="f5999-168">[is](../keywords/is.md): compatibilità del tipo.</span><span class="sxs-lookup"><span data-stu-id="f5999-168">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="f5999-169">Restituisce true se è possibile eseguire il cast dell'operando di sinistra valutato al tipo specificato nell'operando di destra (un tipo statico).</span><span class="sxs-lookup"><span data-stu-id="f5999-169">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="f5999-170">[as](../keywords/as.md): conversione di tipi.</span><span class="sxs-lookup"><span data-stu-id="f5999-170">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="f5999-171">Restituisce il cast dell'operando di sinistra al tipo specificato dall'operando di destra (un tipo statico), ma `as` restituisce `null` dove `(T)x` genererebbe un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f5999-171">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="f5999-172">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="f5999-172">Equality operators</span></span>

<span data-ttu-id="f5999-173">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-173">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-174">[x == y](equality-operators.md#equality-operator-): uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="f5999-174">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="f5999-175">Per impostazione predefinita, per i tipi di riferimento diversi da `string`, restituisce l'uguaglianza dei riferimenti (test dell'identità).</span><span class="sxs-lookup"><span data-stu-id="f5999-175">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="f5999-176">Tuttavia, i tipi possono eseguire l'overload di `==`, quindi, se si prevede di testare l'identità, è meglio usare il metodo `ReferenceEquals` su `object`.</span><span class="sxs-lookup"><span data-stu-id="f5999-176">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="f5999-177">[x != y](equality-operators.md#inequality-operator-): diverso da.</span><span class="sxs-lookup"><span data-stu-id="f5999-177">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="f5999-178">Vedere il commento per `==`.</span><span class="sxs-lookup"><span data-stu-id="f5999-178">See comment for `==`.</span></span> <span data-ttu-id="f5999-179">Se un tipo esegue l'overload di `==`, deve eseguire l'overload di `!=`.</span><span class="sxs-lookup"><span data-stu-id="f5999-179">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="f5999-180">AND (operatore logico)</span><span class="sxs-lookup"><span data-stu-id="f5999-180">Logical AND operator</span></span>

<span data-ttu-id="f5999-181">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-181">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-182">[x & y](and-operator.md): AND logico o bit per bit.</span><span class="sxs-lookup"><span data-stu-id="f5999-182">[x & y](and-operator.md) – logical or bitwise AND.</span></span> <span data-ttu-id="f5999-183">Di solito è possibile usarlo con i tipi Integer e con i tipi `enum`.</span><span class="sxs-lookup"><span data-stu-id="f5999-183">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="f5999-184">Operatore XOR logico</span><span class="sxs-lookup"><span data-stu-id="f5999-184">Logical XOR operator</span></span>

<span data-ttu-id="f5999-185">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-185">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-186">[x ^ y](xor-operator.md): XOR logico o bit per bit.</span><span class="sxs-lookup"><span data-stu-id="f5999-186">[x ^ y](xor-operator.md) – logical or bitwise XOR.</span></span> <span data-ttu-id="f5999-187">Di solito è possibile usarlo con i tipi Integer e con i tipi `enum`.</span><span class="sxs-lookup"><span data-stu-id="f5999-187">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="f5999-188">Operatore logico OR</span><span class="sxs-lookup"><span data-stu-id="f5999-188">Logical OR operator</span></span>

<span data-ttu-id="f5999-189">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-190">[x &#124; y](or-operator.md): OR logico o bit per bit.</span><span class="sxs-lookup"><span data-stu-id="f5999-190">[x &#124; y](or-operator.md) – logical or bitwise OR.</span></span> <span data-ttu-id="f5999-191">Di solito è possibile usarlo con i tipi Integer e con i tipi `enum`.</span><span class="sxs-lookup"><span data-stu-id="f5999-191">You can generally use this with integer types and `enum` types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="f5999-192">Operatore AND condizionale</span><span class="sxs-lookup"><span data-stu-id="f5999-192">Conditional AND operator</span></span>

<span data-ttu-id="f5999-193">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-193">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-194">[x && y](conditional-and-operator.md): AND logico.</span><span class="sxs-lookup"><span data-stu-id="f5999-194">[x && y](conditional-and-operator.md) – logical AND.</span></span> <span data-ttu-id="f5999-195">Se il primo operando è false, C# non valuta il secondo operando.</span><span class="sxs-lookup"><span data-stu-id="f5999-195">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="f5999-196">Operatore OR condizionale</span><span class="sxs-lookup"><span data-stu-id="f5999-196">Conditional OR operator</span></span>

<span data-ttu-id="f5999-197">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-197">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-198">[x &#124;&#124; y](conditional-or-operator.md): OR logico.</span><span class="sxs-lookup"><span data-stu-id="f5999-198">[x &#124;&#124; y](conditional-or-operator.md) – logical OR.</span></span> <span data-ttu-id="f5999-199">Se il primo operando è true, C# non valuta il secondo operando.</span><span class="sxs-lookup"><span data-stu-id="f5999-199">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="f5999-200">Operatore null-coalescing</span><span class="sxs-lookup"><span data-stu-id="f5999-200">Null-coalescing operator</span></span>

<span data-ttu-id="f5999-201">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-201">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-202">[x ?? y](null-coalescing-operator.md): restituisce `x` se è non `null`. In caso contrario, restituisce `y`.</span><span class="sxs-lookup"><span data-stu-id="f5999-202">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="f5999-203">Operatore condizionale</span><span class="sxs-lookup"><span data-stu-id="f5999-203">Conditional operator</span></span>

<span data-ttu-id="f5999-204">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-204">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-205">[t ? x : y](conditional-operator.md): se `t` di test è true, valuta e restituisce `x`. In caso contrario, valuta e restituisce `y`.</span><span class="sxs-lookup"><span data-stu-id="f5999-205">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="f5999-206">Operatori di assegnazione e lambda</span><span class="sxs-lookup"><span data-stu-id="f5999-206">Assignment and Lambda operators</span></span>

<span data-ttu-id="f5999-207">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f5999-207">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="f5999-208">[x = y](assignment-operator.md): assegnazione.</span><span class="sxs-lookup"><span data-stu-id="f5999-208">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="f5999-209">[x = y](addition-assignment-operator.md): incremento.</span><span class="sxs-lookup"><span data-stu-id="f5999-209">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="f5999-210">Aggiunge il valore di `y` al valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f5999-210">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="f5999-211">Se `x` designa un oggetto `event`, `y` deve essere una funzione appropriata che C# aggiunge come gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f5999-211">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="f5999-212">[x -= y](subtraction-assignment-operator.md): decremento.</span><span class="sxs-lookup"><span data-stu-id="f5999-212">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="f5999-213">Sottrae il valore di `y` dal valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f5999-213">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="f5999-214">Se `x` designa un oggetto `event`, `y` deve essere una funzione appropriata che C# rimuove come gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f5999-214">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>

<span data-ttu-id="f5999-215">[x -= y](multiplication-assignment-operator.md): assegnazione di moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="f5999-215">[x \*= y](multiplication-assignment-operator.md) – multiplication assignment.</span></span> <span data-ttu-id="f5999-216">Moltiplica il valore di `y` per il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f5999-216">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="f5999-217">[x -= y](arithmetic-operators.md#compound-assignment): assegnazione di divisione.</span><span class="sxs-lookup"><span data-stu-id="f5999-217">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="f5999-218">Divide il valore di `x` per il valore di `y`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f5999-218">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="f5999-219">[x %= y](arithmetic-operators.md#compound-assignment): assegnazione di resto.</span><span class="sxs-lookup"><span data-stu-id="f5999-219">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="f5999-220">Divide il valore di `x` per il valore di `y`, archivia il resto in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f5999-220">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="f5999-221">[x &= y](and-assignment-operator.md): assegnazione dell'operatore AND.</span><span class="sxs-lookup"><span data-stu-id="f5999-221">[x &= y](and-assignment-operator.md) – AND assignment.</span></span> <span data-ttu-id="f5999-222">Applica AND al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f5999-222">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="f5999-223">[x &#124;= y](or-assignment-operator.md): assegnazione dell'operatore OR.</span><span class="sxs-lookup"><span data-stu-id="f5999-223">[x &#124;= y](or-assignment-operator.md) – OR assignment.</span></span> <span data-ttu-id="f5999-224">Applica OR al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f5999-224">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="f5999-225">[x ^= y](xor-assignment-operator.md): assegnazione dell'operatore XOR.</span><span class="sxs-lookup"><span data-stu-id="f5999-225">[x ^= y](xor-assignment-operator.md) – XOR assignment.</span></span> <span data-ttu-id="f5999-226">Applica XOR al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f5999-226">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="f5999-227">[x <<= y](left-shift-assignment-operator.md): assegnazione di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="f5999-227">[x <<= y](left-shift-assignment-operator.md) – left-shift assignment.</span></span> <span data-ttu-id="f5999-228">Sposta il valore di `x` verso sinistra di `y` posti, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f5999-228">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="f5999-229">[x >>= y](right-shift-assignment-operator.md): assegnazione di spostamento a destra.</span><span class="sxs-lookup"><span data-stu-id="f5999-229">[x >>= y](right-shift-assignment-operator.md) – right-shift assignment.</span></span> <span data-ttu-id="f5999-230">Sposta il valore di `x` verso destra di `y` posti, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f5999-230">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="f5999-231">[=>](lambda-operator.md): dichiarazione lambda.</span><span class="sxs-lookup"><span data-stu-id="f5999-231">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5999-232">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5999-232">See also</span></span>

- [<span data-ttu-id="f5999-233">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f5999-233">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f5999-234">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f5999-234">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f5999-235">C#</span><span class="sxs-lookup"><span data-stu-id="f5999-235">C#</span></span>](../../index.md)
- [<span data-ttu-id="f5999-236">Operatori che supportano l'overload</span><span class="sxs-lookup"><span data-stu-id="f5999-236">Overloadable Operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="f5999-237">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="f5999-237">C# Keywords</span></span>](../keywords/index.md)