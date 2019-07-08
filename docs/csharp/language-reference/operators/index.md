---
title: Operatori C# - Riferimenti per C#
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 0cd0a06dc919ecf11f1a3d343fe8ff023a5f8524
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2019
ms.locfileid: "67609909"
---
# <a name="c-operators-c-reference"></a><span data-ttu-id="bce9f-102">Operatori C# (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bce9f-102">C# operators (C# reference)</span></span>

<span data-ttu-id="bce9f-103">C# fornisce una serie di operatori predefiniti supportati dai tipi incorporati.</span><span class="sxs-lookup"><span data-stu-id="bce9f-103">C# provides a number of predefined operators supported by the built-in types.</span></span> <span data-ttu-id="bce9f-104">Ad esempio, gli [operatori aritmetici](arithmetic-operators.md) eseguono operazioni aritmetiche con gli operandi di tipi numerici incorporati e gli [operatori logici booleani](boolean-logical-operators.md) eseguono operazioni logiche con gli operandi [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="bce9f-104">For example, [arithmetic operators](arithmetic-operators.md) perform arithmetic operations with operands of built-in numeric types and [Boolean logical operators](boolean-logical-operators.md) perform logical operations with the [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="bce9f-105">Un tipo definito dall'utente può eseguire l'overload di operatori specifici per definire il comportamento corrispondente per gli operandi di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="bce9f-105">A user-defined type can overload certain operators to define the corresponding behavior for the operands of that type.</span></span> <span data-ttu-id="bce9f-106">Per altre informazioni, vedere [Overload degli operatori](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="bce9f-106">For more information, see [Operator overloading](operator-overloading.md).</span></span>

<span data-ttu-id="bce9f-107">Le sezioni seguenti elencano gli operatori C# da quelli con la precedenza più alta a quelli con la più bassa.</span><span class="sxs-lookup"><span data-stu-id="bce9f-107">The following sections list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="bce9f-108">Gli operatori di ogni sezione condividono lo stesso livello di precedenza.</span><span class="sxs-lookup"><span data-stu-id="bce9f-108">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="bce9f-109">Operatori primari</span><span class="sxs-lookup"><span data-stu-id="bce9f-109">Primary operators</span></span>

<span data-ttu-id="bce9f-110">Sono gli operatori con la precedenza più alta.</span><span class="sxs-lookup"><span data-stu-id="bce9f-110">These are the highest precedence operators.</span></span>

<span data-ttu-id="bce9f-111">[x.y](member-access-operators.md#member-access-operator-): accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="bce9f-111">[x.y](member-access-operators.md#member-access-operator-) – member access.</span></span>

<span data-ttu-id="bce9f-112">[x?.y](member-access-operators.md#null-conditional-operators--and-): accesso ai membri condizionali null.</span><span class="sxs-lookup"><span data-stu-id="bce9f-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) – null conditional member access.</span></span> <span data-ttu-id="bce9f-113">Restituisce `null` se l'operando sul lato sinistro è `null`.</span><span class="sxs-lookup"><span data-stu-id="bce9f-113">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="bce9f-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-): elemento di matrice condizionale null o accesso al tipo di indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) - null conditional array element or type indexer access.</span></span> <span data-ttu-id="bce9f-115">Restituisce `null` se l'operando sul lato sinistro è `null`.</span><span class="sxs-lookup"><span data-stu-id="bce9f-115">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="bce9f-116">[f(x)](member-access-operators.md#invocation-operator-): chiamata di metodo o chiamata a un delegato.</span><span class="sxs-lookup"><span data-stu-id="bce9f-116">[f(x)](member-access-operators.md#invocation-operator-) – method call or delegate invocation.</span></span>

<span data-ttu-id="bce9f-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-): elemento di matrice o accesso al tipo di indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-) – array element or type indexer access.</span></span>

<span data-ttu-id="bce9f-118">[x++](arithmetic-operators.md#increment-operator-): incremento suffisso.</span><span class="sxs-lookup"><span data-stu-id="bce9f-118">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="bce9f-119">Restituisce il valore di x e quindi aggiorna la posizione di archiviazione con il valore di x che risulta maggiore (in genere aggiunge il numero intero 1).</span><span class="sxs-lookup"><span data-stu-id="bce9f-119">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="bce9f-120">[x--](arithmetic-operators.md#decrement-operator---): decremento suffisso.</span><span class="sxs-lookup"><span data-stu-id="bce9f-120">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="bce9f-121">Restituisce il valore di x e quindi aggiorna la posizione di archiviazione con il valore di x che risulta minore (in genere sottrae il numero intero 1).</span><span class="sxs-lookup"><span data-stu-id="bce9f-121">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="bce9f-122">[new](new-operator.md): creazione di un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="bce9f-122">[new](new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="bce9f-123">[typeof](type-testing-and-conversion-operators.md#typeof-operator): restituisce l'oggetto <xref:System.Type> che rappresenta l'operando.</span><span class="sxs-lookup"><span data-stu-id="bce9f-123">[typeof](type-testing-and-conversion-operators.md#typeof-operator) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="bce9f-124">[checked](../keywords/checked.md): abilita il controllo di overflow per le operazioni con numeri interi.</span><span class="sxs-lookup"><span data-stu-id="bce9f-124">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="bce9f-125">[unchecked](../keywords/unchecked.md): disabilita il controllo di overflow per le operazioni con numeri interi.</span><span class="sxs-lookup"><span data-stu-id="bce9f-125">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="bce9f-126">Questo è il comportamento predefinito per il compilatore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-126">This is the default compiler behavior.</span></span>

<span data-ttu-id="bce9f-127">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md): genera il valore predefinito del tipo T.</span><span class="sxs-lookup"><span data-stu-id="bce9f-127">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="bce9f-128">[nameof](../keywords/nameof.md): ottiene il nome semplice (non qualificato) di una variabile, di un tipo o di un membro come stringa costante.</span><span class="sxs-lookup"><span data-stu-id="bce9f-128">[nameof](../keywords/nameof.md) - obtains the simple (unqualified) name of a variable, type, or member as a constant string.</span></span>

<span data-ttu-id="bce9f-129">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md): dichiara e restituisce un'istanza di delegato.</span><span class="sxs-lookup"><span data-stu-id="bce9f-129">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="bce9f-130">[sizeof](../keywords/sizeof.md): restituisce le dimensioni in byte dell'operando type.</span><span class="sxs-lookup"><span data-stu-id="bce9f-130">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="bce9f-131">[stackalloc](stackalloc.md): alloca un blocco di memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="bce9f-131">[stackalloc](stackalloc.md) - allocates a block of memory on the stack.</span></span>

<span data-ttu-id="bce9f-132">[->](pointer-related-operators.md#pointer-member-access-operator--): riferimento indiretto al puntatore combinato con l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="bce9f-132">[->](pointer-related-operators.md#pointer-member-access-operator--) – pointer indirection combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="bce9f-133">Operatori unari</span><span class="sxs-lookup"><span data-stu-id="bce9f-133">Unary operators</span></span>

<span data-ttu-id="bce9f-134">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-134">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-135">[+x](addition-operator.md): restituisce il valore di x.</span><span class="sxs-lookup"><span data-stu-id="bce9f-135">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="bce9f-136">[-x](subtraction-operator.md): negazione numerica.</span><span class="sxs-lookup"><span data-stu-id="bce9f-136">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="bce9f-137">[\!x](boolean-logical-operators.md#logical-negation-operator-): negazione logica.</span><span class="sxs-lookup"><span data-stu-id="bce9f-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="bce9f-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-): complemento bit per bit.</span><span class="sxs-lookup"><span data-stu-id="bce9f-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="bce9f-139">[~x](arithmetic-operators.md#increment-operator-): incremento prefisso.</span><span class="sxs-lookup"><span data-stu-id="bce9f-139">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="bce9f-140">Restituisce il valore di x dopo avere aggiornato la posizione di archiviazione con il valore di x che risulta maggiore (in genere aggiunge il numero intero 1).</span><span class="sxs-lookup"><span data-stu-id="bce9f-140">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="bce9f-141">[--x](arithmetic-operators.md#decrement-operator---): decremento prefisso.</span><span class="sxs-lookup"><span data-stu-id="bce9f-141">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="bce9f-142">Restituisce il valore di x dopo avere aggiornato la posizione di archiviazione con il valore di x che risulta minore (in genere sottrae il numero intero 1).</span><span class="sxs-lookup"><span data-stu-id="bce9f-142">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="bce9f-143">[(T)x](type-testing-and-conversion-operators.md#cast-operator-): cast di tipo.</span><span class="sxs-lookup"><span data-stu-id="bce9f-143">[(T)x](type-testing-and-conversion-operators.md#cast-operator-) – type casting.</span></span>

<span data-ttu-id="bce9f-144">[await](../keywords/await.md): attende un oggetto `Task`.</span><span class="sxs-lookup"><span data-stu-id="bce9f-144">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="bce9f-145">[&x](pointer-related-operators.md#address-of-operator-): indirizzo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="bce9f-145">[&x](pointer-related-operators.md#address-of-operator-) – address of a variable.</span></span>

<span data-ttu-id="bce9f-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-): riferimento indiretto al puntatore o dereferenziazione.</span><span class="sxs-lookup"><span data-stu-id="bce9f-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-) – pointer indirection, or dereference.</span></span>

<span data-ttu-id="bce9f-147">[Operatore true](true-false-operators.md): restituisce il valore [bool](../keywords/bool.md) `true` per indicare che un operando è senza dubbio true.</span><span class="sxs-lookup"><span data-stu-id="bce9f-147">[true operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="bce9f-148">[Operatore false](true-false-operators.md): restituisce il valore [bool](../keywords/bool.md) `true` per indicare che un operando è senza dubbio false.</span><span class="sxs-lookup"><span data-stu-id="bce9f-148">[false operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="bce9f-149">Operatori moltiplicativi</span><span class="sxs-lookup"><span data-stu-id="bce9f-149">Multiplicative operators</span></span>

<span data-ttu-id="bce9f-150">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-150">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-151">[x \* y](arithmetic-operators.md#multiplication-operator-): moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="bce9f-151">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="bce9f-152">[x / y](arithmetic-operators.md#division-operator-): divisione.</span><span class="sxs-lookup"><span data-stu-id="bce9f-152">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="bce9f-153">Se gli operandi sono numeri interi, il risultato è un numero intero troncato verso zero (ad esempio, `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="bce9f-153">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="bce9f-154">[x % y](arithmetic-operators.md#remainder-operator-): resto.</span><span class="sxs-lookup"><span data-stu-id="bce9f-154">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="bce9f-155">Se gli operandi sono numeri interi, restituisce il resto della divisione di x per y.</span><span class="sxs-lookup"><span data-stu-id="bce9f-155">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="bce9f-156">Se `q = x / y` e `r = x % y`, allora `x = q * y + r`</span><span class="sxs-lookup"><span data-stu-id="bce9f-156">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="bce9f-157">Operatori additivi</span><span class="sxs-lookup"><span data-stu-id="bce9f-157">Additive operators</span></span>

<span data-ttu-id="bce9f-158">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-158">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-159">[x + y](arithmetic-operators.md#addition-operator-): addizione.</span><span class="sxs-lookup"><span data-stu-id="bce9f-159">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="bce9f-160">[x – y](arithmetic-operators.md#subtraction-operator--): sottrazione.</span><span class="sxs-lookup"><span data-stu-id="bce9f-160">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="bce9f-161">Operatori shift</span><span class="sxs-lookup"><span data-stu-id="bce9f-161">Shift operators</span></span>

<span data-ttu-id="bce9f-162">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-162">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-): spostamento dei bit a sinistra e inserimento di zero a destra.</span><span class="sxs-lookup"><span data-stu-id="bce9f-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="bce9f-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-): spostamento dei bit a destra.</span><span class="sxs-lookup"><span data-stu-id="bce9f-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="bce9f-165">Se l'operando di sinistra è `int` o `long`, i bit di sinistra vengono riempiti con il bit più significativo.</span><span class="sxs-lookup"><span data-stu-id="bce9f-165">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="bce9f-166">Se l'operando di sinistra è `uint` o `ulong`, i bit di sinistra vengono riempiti con zero.</span><span class="sxs-lookup"><span data-stu-id="bce9f-166">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="bce9f-167">Operatori relazionali e operatori di test del tipo</span><span class="sxs-lookup"><span data-stu-id="bce9f-167">Relational and type-testing operators</span></span>

<span data-ttu-id="bce9f-168">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-168">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-169">[x \< y](comparison-operators.md#less-than-operator-): minore di (true se x è minore di y).</span><span class="sxs-lookup"><span data-stu-id="bce9f-169">[x \< y](comparison-operators.md#less-than-operator-) – less than (true if x is less than y).</span></span>

<span data-ttu-id="bce9f-170">[x > y](comparison-operators.md#greater-than-operator-): maggiore di (true se x è maggiore di y).</span><span class="sxs-lookup"><span data-stu-id="bce9f-170">[x > y](comparison-operators.md#greater-than-operator-) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="bce9f-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-): minore o uguale a.</span><span class="sxs-lookup"><span data-stu-id="bce9f-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – less than or equal to.</span></span>

<span data-ttu-id="bce9f-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-): maggiore o uguale a.</span><span class="sxs-lookup"><span data-stu-id="bce9f-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – greater than or equal to.</span></span>

<span data-ttu-id="bce9f-173">[is](type-testing-and-conversion-operators.md#is-operator): compatibilità del tipo.</span><span class="sxs-lookup"><span data-stu-id="bce9f-173">[is](type-testing-and-conversion-operators.md#is-operator) – type compatibility.</span></span> <span data-ttu-id="bce9f-174">Restituisce `true` se è possibile eseguire il cast dell'operando di sinistra valutato al tipo specificato dall'operando di destra.</span><span class="sxs-lookup"><span data-stu-id="bce9f-174">Returns `true` if the evaluated left operand can be cast to the type specified by the right operand.</span></span>

<span data-ttu-id="bce9f-175">[as](type-testing-and-conversion-operators.md#as-operator): conversione di tipi.</span><span class="sxs-lookup"><span data-stu-id="bce9f-175">[as](type-testing-and-conversion-operators.md#as-operator) – type conversion.</span></span> <span data-ttu-id="bce9f-176">Restituisce il cast dell'operando di sinistra al tipo specificato dall'operando di destra, ma `as` restituisce `null` dove `(T)x` genererebbe un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="bce9f-176">Returns the left operand cast to the type specified by the right operand, but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="bce9f-177">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="bce9f-177">Equality operators</span></span>

<span data-ttu-id="bce9f-178">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-178">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-179">[x == y](equality-operators.md#equality-operator-): uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="bce9f-179">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="bce9f-180">Per impostazione predefinita, per i tipi di riferimento diversi da `string`, restituisce l'uguaglianza dei riferimenti (test dell'identità).</span><span class="sxs-lookup"><span data-stu-id="bce9f-180">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="bce9f-181">Tuttavia, i tipi possono eseguire l'overload di `==`, quindi, se si prevede di testare l'identità, è meglio usare il metodo `ReferenceEquals` su `object`.</span><span class="sxs-lookup"><span data-stu-id="bce9f-181">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="bce9f-182">[x != y](equality-operators.md#inequality-operator-): diverso da.</span><span class="sxs-lookup"><span data-stu-id="bce9f-182">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="bce9f-183">Vedere il commento per `==`.</span><span class="sxs-lookup"><span data-stu-id="bce9f-183">See comment for `==`.</span></span> <span data-ttu-id="bce9f-184">Se un tipo esegue l'overload di `==`, deve eseguire l'overload di `!=`.</span><span class="sxs-lookup"><span data-stu-id="bce9f-184">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="bce9f-185">AND (operatore logico)</span><span class="sxs-lookup"><span data-stu-id="bce9f-185">Logical AND operator</span></span>

<span data-ttu-id="bce9f-186">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-187">`x & y`: [AND logico](boolean-logical-operators.md#logical-and-operator-) per gli operandi `bool` o [AND logico bit per bit](bitwise-and-shift-operators.md#logical-and-operator-) per gli operandi dei tipi di dati integrali.</span><span class="sxs-lookup"><span data-stu-id="bce9f-187">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="bce9f-188">Operatore XOR logico</span><span class="sxs-lookup"><span data-stu-id="bce9f-188">Logical XOR operator</span></span>

<span data-ttu-id="bce9f-189">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-190">`x ^ y`: [XOR logico](boolean-logical-operators.md#logical-exclusive-or-operator-) per gli operandi `bool` o [XOR logico bit per bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) per gli operandi dei tipi di dati integrali.</span><span class="sxs-lookup"><span data-stu-id="bce9f-190">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="bce9f-191">Operatore logico OR</span><span class="sxs-lookup"><span data-stu-id="bce9f-191">Logical OR operator</span></span>

<span data-ttu-id="bce9f-192">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-193">`x | y`: [OR logico](boolean-logical-operators.md#logical-or-operator-) per gli operandi `bool` o [OR logico bit per bit](bitwise-and-shift-operators.md#logical-or-operator-) per gli operandi dei tipi di dati integrali.</span><span class="sxs-lookup"><span data-stu-id="bce9f-193">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="bce9f-194">Operatore AND condizionale</span><span class="sxs-lookup"><span data-stu-id="bce9f-194">Conditional AND operator</span></span>

<span data-ttu-id="bce9f-195">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-195">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-): AND logico.</span><span class="sxs-lookup"><span data-stu-id="bce9f-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="bce9f-197">Se `x` è `false`, `y` non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="bce9f-197">If `x` evaluates to `false`, then `y` is not evaluated.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="bce9f-198">Operatore OR condizionale</span><span class="sxs-lookup"><span data-stu-id="bce9f-198">Conditional OR operator</span></span>

<span data-ttu-id="bce9f-199">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-199">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-): OR logico.</span><span class="sxs-lookup"><span data-stu-id="bce9f-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="bce9f-201">Se `x` è `true`, `y` non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="bce9f-201">If `x` evaluates to `true`, then `y` is not evaluated.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="bce9f-202">Operatore null-coalescing</span><span class="sxs-lookup"><span data-stu-id="bce9f-202">Null-coalescing operator</span></span>

<span data-ttu-id="bce9f-203">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-204">[x ?? y](null-coalescing-operator.md): restituisce `x` se è non `null`. In caso contrario, restituisce `y`.</span><span class="sxs-lookup"><span data-stu-id="bce9f-204">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="bce9f-205">Operatore condizionale</span><span class="sxs-lookup"><span data-stu-id="bce9f-205">Conditional operator</span></span>

<span data-ttu-id="bce9f-206">Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-206">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-207">[t ? x : y](conditional-operator.md): se `t` di test è true, valuta e restituisce `x`. In caso contrario, valuta e restituisce `y`.</span><span class="sxs-lookup"><span data-stu-id="bce9f-207">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="bce9f-208">Operatori di assegnazione e lambda</span><span class="sxs-lookup"><span data-stu-id="bce9f-208">Assignment and lambda operators</span></span>

<span data-ttu-id="bce9f-209">Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bce9f-209">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bce9f-210">[x = y](assignment-operator.md): assegnazione.</span><span class="sxs-lookup"><span data-stu-id="bce9f-210">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="bce9f-211">[x += y](arithmetic-operators.md#compound-assignment): incremento.</span><span class="sxs-lookup"><span data-stu-id="bce9f-211">[x += y](arithmetic-operators.md#compound-assignment) – increment.</span></span> <span data-ttu-id="bce9f-212">Aggiunge il valore di `y` al valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-212">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="bce9f-213">Se `x` indica un elemento [event](../keywords/event.md), `y` deve essere un metodo appropriato che C# aggiunge come gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="bce9f-213">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# adds as an event handler.</span></span>

<span data-ttu-id="bce9f-214">[x -= y](arithmetic-operators.md#compound-assignment): decremento.</span><span class="sxs-lookup"><span data-stu-id="bce9f-214">[x -= y](arithmetic-operators.md#compound-assignment) – decrement.</span></span> <span data-ttu-id="bce9f-215">Sottrae il valore di `y` dal valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-215">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="bce9f-216">Se `x` indica un elemento [event](../keywords/event.md), `y` deve essere un metodo appropriato che C# rimuove come gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="bce9f-216">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# removes as an event handler.</span></span>

<span data-ttu-id="bce9f-217">[x \*= y](arithmetic-operators.md#compound-assignment): assegnazione di moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="bce9f-217">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="bce9f-218">Moltiplica il valore di `y` per il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-218">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bce9f-219">[x /= y](arithmetic-operators.md#compound-assignment): assegnazione di divisione.</span><span class="sxs-lookup"><span data-stu-id="bce9f-219">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="bce9f-220">Divide il valore di `x` per il valore di `y`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-220">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bce9f-221">[x %= y](arithmetic-operators.md#compound-assignment): assegnazione di resto.</span><span class="sxs-lookup"><span data-stu-id="bce9f-221">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="bce9f-222">Divide il valore di `x` per il valore di `y`, archivia il resto in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-222">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="bce9f-223">[x &= y](boolean-logical-operators.md#compound-assignment): assegnazione dell'operatore AND.</span><span class="sxs-lookup"><span data-stu-id="bce9f-223">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="bce9f-224">Applica AND al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-224">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bce9f-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment): assegnazione dell'operatore OR.</span><span class="sxs-lookup"><span data-stu-id="bce9f-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="bce9f-226">Applica OR al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-226">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bce9f-227">[x ^= y](boolean-logical-operators.md#compound-assignment): assegnazione dell'operatore XOR.</span><span class="sxs-lookup"><span data-stu-id="bce9f-227">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="bce9f-228">Applica XOR al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-228">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bce9f-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment): assegnazione di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="bce9f-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="bce9f-230">Sposta il valore di `x` verso sinistra di `y` posti, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-230">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bce9f-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment): assegnazione di spostamento a destra.</span><span class="sxs-lookup"><span data-stu-id="bce9f-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="bce9f-232">Sposta il valore di `x` verso destra di `y` posti, archivia il risultato in `x` e restituisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="bce9f-232">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bce9f-233">[=>](lambda-operator.md): dichiarazione lambda.</span><span class="sxs-lookup"><span data-stu-id="bce9f-233">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="bce9f-234">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bce9f-234">See also</span></span>

- [<span data-ttu-id="bce9f-235">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="bce9f-235">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bce9f-236">Operatori</span><span class="sxs-lookup"><span data-stu-id="bce9f-236">Operators</span></span>](../../programming-guide/statements-expressions-operators/operators.md)
