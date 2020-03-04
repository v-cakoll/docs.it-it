---
title: Operatori correlati ai puntatori - Riferimento C#
description: Di seguito sono descritti gli operatori C# che è possibile usare con i puntatori.
ms.date: 05/20/2019
author: pkulikov
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- pointer related operators [C#]
- address-of operator [C#]
- '& operator [C#]'
- pointer indirection operator [C#]
- dereference operator [C#]
- '* operator [C#]'
- pointer member access operator [C#]
- -> operator [C#]
- pointer element access [C#]
- '[] operator [C#]'
- pointer arithmetic [C#]
- pointer increment [C#]
- pointer decrement [C#]
- pointer comparison [C#]
ms.openlocfilehash: 51e6aeda7699d9e2fe3c46ced93e1783a52e6743
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78238962"
---
# <a name="pointer-related-operators-c-reference"></a><span data-ttu-id="42b5a-103">Operatori correlati ai puntatori (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="42b5a-103">Pointer related operators (C# reference)</span></span>

<span data-ttu-id="42b5a-104">È possibile usare gli operatori seguenti con i puntatori:</span><span class="sxs-lookup"><span data-stu-id="42b5a-104">You can use the following operators to work with pointers:</span></span>

- <span data-ttu-id="42b5a-105">Operatore [`&` (address-of)](#address-of-operator-) unario: per ottenere l'indirizzo di una variabile</span><span class="sxs-lookup"><span data-stu-id="42b5a-105">Unary [`&` (address-of)](#address-of-operator-) operator: to get the address of a variable</span></span>
- <span data-ttu-id="42b5a-106">Operatore [`*` (riferimento indiretto al puntatore)](#pointer-indirection-operator-): per ottenere la variabile indicata da un puntatore</span><span class="sxs-lookup"><span data-stu-id="42b5a-106">Unary [`*` (pointer indirection)](#pointer-indirection-operator-) operator: to obtain the variable pointed by a pointer</span></span>
- <span data-ttu-id="42b5a-107">Operatori [`->` (accesso ai membri)](#pointer-member-access-operator--) e [`[]` (accesso agli elementi)](#pointer-element-access-operator-)</span><span class="sxs-lookup"><span data-stu-id="42b5a-107">The [`->` (member access)](#pointer-member-access-operator--) and [`[]` (element access)](#pointer-element-access-operator-) operators</span></span>
- <span data-ttu-id="42b5a-108">Operatori aritmetici [`+`, `-`, `++` e `--`](#pointer-arithmetic-operators)</span><span class="sxs-lookup"><span data-stu-id="42b5a-108">Arithmetic operators [`+`, `-`, `++`, and `--`](#pointer-arithmetic-operators)</span></span>
- <span data-ttu-id="42b5a-109">Operatori di confronto [`==`, `!=`, `<`, `>`, `<=` e `>=`](#pointer-comparison-operators)</span><span class="sxs-lookup"><span data-stu-id="42b5a-109">Comparison operators [`==`, `!=`, `<`, `>`, `<=`, and `>=`](#pointer-comparison-operators)</span></span>

<span data-ttu-id="42b5a-110">Per informazioni sui tipi di puntatori, vedere [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="42b5a-110">For information about pointer types, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

> [!NOTE]
> <span data-ttu-id="42b5a-111">Qualsiasi operazione con i puntatori richiede un contesto [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="42b5a-111">Any operation with pointers requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="42b5a-112">Il codice che contiene blocchi unsafe deve essere compilato con l'opzione del compilatore [`-unsafe`](../compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="42b5a-112">The code that contains unsafe blocks must be compiled with the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

## <a name="address-of-operator-"></a> <span data-ttu-id="42b5a-113">Operatore address-of &amp;</span><span class="sxs-lookup"><span data-stu-id="42b5a-113">Address-of operator &amp;</span></span>

<span data-ttu-id="42b5a-114">L'operatore `&` unario restituisce l'indirizzo del relativo operando:</span><span class="sxs-lookup"><span data-stu-id="42b5a-114">The unary `&` operator returns the address of its operand:</span></span>

[!code-csharp[address of local](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#AddressOf)]

<span data-ttu-id="42b5a-115">L'operando dell'operatore `&` deve essere una variabile fissa.</span><span class="sxs-lookup"><span data-stu-id="42b5a-115">The operand of the `&` operator must be a fixed variable.</span></span> <span data-ttu-id="42b5a-116">Le variabili *fisse* sono variabili che si trovano in posizioni di archiviazione non interessate dall'operazione di [Garbage Collector](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="42b5a-116">*Fixed* variables are variables that reside in storage locations that are unaffected by operation of the [garbage collector](../../../standard/garbage-collection/index.md).</span></span> <span data-ttu-id="42b5a-117">Nell'esempio precedente la variabile locale `number` è una variabile fissa perché si trova nello stack.</span><span class="sxs-lookup"><span data-stu-id="42b5a-117">In the preceding example, the local variable `number` is a fixed variable, because it resides on the stack.</span></span> <span data-ttu-id="42b5a-118">Le variabili che si trovano in posizioni di archiviazione che possono essere influenzate da Garbage Collector (ad esempio rilocate) sono chiamate variabili *mobili*.</span><span class="sxs-lookup"><span data-stu-id="42b5a-118">Variables that reside in storage locations that can be affected by the garbage collector (for example, relocated) are called *movable* variables.</span></span> <span data-ttu-id="42b5a-119">I campi degli oggetti e gli elementi delle matrici sono esempi di variabili mobili.</span><span class="sxs-lookup"><span data-stu-id="42b5a-119">Object fields and array elements are examples of movable variables.</span></span> <span data-ttu-id="42b5a-120">È possibile ottenere l'indirizzo di una variabile mobile se si "corregge", o "pin", con un' [istruzione`fixed`](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="42b5a-120">You can get the address of a movable variable if you "fix", or "pin", it with a [`fixed` statement](../keywords/fixed-statement.md).</span></span> <span data-ttu-id="42b5a-121">L'indirizzo ottenuto è valido solo all'interno del blocco di un'istruzione `fixed`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-121">The obtained address is valid only inside the block of a `fixed` statement.</span></span> <span data-ttu-id="42b5a-122">Nell'esempio seguente viene illustrato come utilizzare un'istruzione `fixed` e l'operatore `&`:</span><span class="sxs-lookup"><span data-stu-id="42b5a-122">The following example shows how to use a `fixed` statement and the `&` operator:</span></span>

[!code-csharp[address of fixed](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#AddressOfFixed)]

<span data-ttu-id="42b5a-123">Non è possibile ottenere l'indirizzo di una costante o di un valore.</span><span class="sxs-lookup"><span data-stu-id="42b5a-123">You can't get the address of a constant or a value.</span></span>

<span data-ttu-id="42b5a-124">Per altre informazioni sulle variabili fisse e mobili, vedere la sezione [Variabili fisse e mobili](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) dell'articolo relativo alla [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="42b5a-124">For more information about fixed and movable variables, see the [Fixed and moveable variables](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="42b5a-125">L'operatore `&` binario calcola l'[AND logico](boolean-logical-operators.md#logical-and-operator-) dei relativi operandi booleani o l'[AND logico bit per bit](bitwise-and-shift-operators.md#logical-and-operator-) dei relativi operandi integrali.</span><span class="sxs-lookup"><span data-stu-id="42b5a-125">The binary `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its Boolean operands or the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its integral operands.</span></span>

## <a name="pointer-indirection-operator-"></a><span data-ttu-id="42b5a-126">Operatore \* (riferimento indiretto a puntatore)</span><span class="sxs-lookup"><span data-stu-id="42b5a-126">Pointer indirection operator \*</span></span>

<span data-ttu-id="42b5a-127">L'operatore di riferimento indiretto a puntatore unario `*` ottiene la variabile a cui punta il relativo operando.</span><span class="sxs-lookup"><span data-stu-id="42b5a-127">The unary pointer indirection operator `*` obtains the variable to which its operand points.</span></span> <span data-ttu-id="42b5a-128">L'operatore è chiamato anche operatore di dereferenziazione.</span><span class="sxs-lookup"><span data-stu-id="42b5a-128">It's also known as the dereference operator.</span></span> <span data-ttu-id="42b5a-129">L'operando dell'operatore `*` deve essere un tipo di puntatore.</span><span class="sxs-lookup"><span data-stu-id="42b5a-129">The operand of the `*` operator must be of a pointer type.</span></span>

[!code-csharp[pointer indirection](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#PointerIndirection)]

<span data-ttu-id="42b5a-130">Non è possibile applicare l'operatore `*` a un'espressione di tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-130">You cannot apply the `*` operator to an expression of type `void*`.</span></span>

<span data-ttu-id="42b5a-131">L'operatore `*` binario calcola il [prodotto](arithmetic-operators.md#multiplication-operator-) dei relativi operandi numerici.</span><span class="sxs-lookup"><span data-stu-id="42b5a-131">The binary `*` operator computes the [product](arithmetic-operators.md#multiplication-operator-) of its numeric operands.</span></span>

## <a name="pointer-member-access-operator--"></a><span data-ttu-id="42b5a-132">Operatore -> (accesso ai membri del puntatore)</span><span class="sxs-lookup"><span data-stu-id="42b5a-132">Pointer member access operator -></span></span>

<span data-ttu-id="42b5a-133">L'operatore `->` unisce il [riferimento indiretto al puntatore](#pointer-indirection-operator-) e l'[accesso ai membri](member-access-operators.md#member-access-operator-).</span><span class="sxs-lookup"><span data-stu-id="42b5a-133">The `->` operator combines [pointer indirection](#pointer-indirection-operator-) and [member access](member-access-operators.md#member-access-operator-).</span></span> <span data-ttu-id="42b5a-134">Ovvero, se `x` è un puntatore di tipo `T*` e `y` è un membro accessibile di tipo `T`, un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="42b5a-134">That is, if `x` is a pointer of type `T*` and `y` is an accessible member of type `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="42b5a-135">equivale a</span><span class="sxs-lookup"><span data-stu-id="42b5a-135">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="42b5a-136">Nell'esempio seguente viene illustrato l'uso dell'operatore `->`:</span><span class="sxs-lookup"><span data-stu-id="42b5a-136">The following example demonstrates the usage of the `->` operator:</span></span>

[!code-csharp[pointer member access](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#MemberAccess)]

<span data-ttu-id="42b5a-137">Non è possibile applicare l'operatore `->` a un'espressione di tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-137">You cannot apply the `->` operator to an expression of type `void*`.</span></span>

## <a name="pointer-element-access-operator-"></a><span data-ttu-id="42b5a-138">Operatore [] (accesso agli elementi del puntatore)</span><span class="sxs-lookup"><span data-stu-id="42b5a-138">Pointer element access operator []</span></span>

<span data-ttu-id="42b5a-139">Per un'espressione `p` di un tipo di puntatore, l'accesso a un elemento del puntatore nella forma `p[n]` viene calcolato come `*(p + n)`, dove `n` deve essere un tipo convertibile in modo implicito in `int`, `uint`, `long` o `ulong`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-139">For an expression `p` of a pointer type, a pointer element access of the form `p[n]` is evaluated as `*(p + n)`, where `n` must be of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="42b5a-140">Per informazioni sul comportamento dell'operatore `+` con i puntatori, vedere la sezione [Addizione o sottrazione di un valore integrale da un puntatore](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer).</span><span class="sxs-lookup"><span data-stu-id="42b5a-140">For information about the behavior of the `+` operator with pointers, see the [Addition or subtraction of an integral value to or from a pointer](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) section.</span></span>

<span data-ttu-id="42b5a-141">L'esempio seguente illustra come accedere agli elementi della matrice con un puntatore e l'operatore `[]`:</span><span class="sxs-lookup"><span data-stu-id="42b5a-141">The following example demonstrates how to access array elements with a pointer and the `[]` operator:</span></span>

[!code-csharp[pointer element access](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#ElementAccess)]

<span data-ttu-id="42b5a-142">L'esempio usa l'operatore [`stackalloc`](stackalloc.md) per allocare un blocco di memoria nello stack.</span><span class="sxs-lookup"><span data-stu-id="42b5a-142">The example uses the [`stackalloc` operator](stackalloc.md) to allocate a block of memory on the stack.</span></span>

> [!NOTE]
> <span data-ttu-id="42b5a-143">L'operatore di accesso agli elementi del puntatore non ricerca gli errori relativi a valori non compresi nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="42b5a-143">The pointer element access operator doesn't check for out-of-bounds errors.</span></span>

<span data-ttu-id="42b5a-144">Non è possibile usare `[]` per l'accesso agli elementi del puntatore con un'espressione di tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-144">You cannot use `[]` for pointer element access with an expression of type `void*`.</span></span>

<span data-ttu-id="42b5a-145">È anche possibile usare l'operatore `[]` per l'[accesso agli elementi di una matrice o all'indicizzatore](member-access-operators.md#indexer-operator-).</span><span class="sxs-lookup"><span data-stu-id="42b5a-145">You also can use the `[]` operator for [array element or indexer access](member-access-operators.md#indexer-operator-).</span></span>

## <a name="pointer-arithmetic-operators"></a><span data-ttu-id="42b5a-146">Operatori aritmetici dei puntatori</span><span class="sxs-lookup"><span data-stu-id="42b5a-146">Pointer arithmetic operators</span></span>

<span data-ttu-id="42b5a-147">È possibile eseguire le operazioni aritmetiche seguenti con i puntatori:</span><span class="sxs-lookup"><span data-stu-id="42b5a-147">You can perform the following arithmetic operations with pointers:</span></span>

- <span data-ttu-id="42b5a-148">Aggiungere o sottrarre un valore integrale da un puntatore</span><span class="sxs-lookup"><span data-stu-id="42b5a-148">Add or subtract an integral value to or from a pointer</span></span>
- <span data-ttu-id="42b5a-149">Sottrarre due puntatori</span><span class="sxs-lookup"><span data-stu-id="42b5a-149">Subtract two pointers</span></span>
- <span data-ttu-id="42b5a-150">Incrementare o decrementare un puntatore</span><span class="sxs-lookup"><span data-stu-id="42b5a-150">Increment or decrement a pointer</span></span>

<span data-ttu-id="42b5a-151">Non è possibile eseguire queste operazioni con puntatori di tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-151">You cannot perform those operations with pointers of type `void*`.</span></span>

<span data-ttu-id="42b5a-152">Per informazioni sulle operazioni aritmetiche supportate con i tipi numerici, vedere [Operatori aritmetici](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="42b5a-152">For information about supported arithmetic operations with numeric types, see [Arithmetic operators](arithmetic-operators.md).</span></span>

### <a name="addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer"></a><span data-ttu-id="42b5a-153">Addizione o sottrazione di un valore integrale da un puntatore</span><span class="sxs-lookup"><span data-stu-id="42b5a-153">Addition or subtraction of an integral value to or from a pointer</span></span>

<span data-ttu-id="42b5a-154">Per un puntatore `p` di tipo `T*` e un'espressione `n` di tipo implicitamente convertibile in `int`, `uint`, `long` o `ulong`, l'addizione e la sottrazione sono definite come segue:</span><span class="sxs-lookup"><span data-stu-id="42b5a-154">For a pointer `p` of type `T*` and an expression `n` of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`, addition and subtraction are defined as follows:</span></span>

- <span data-ttu-id="42b5a-155">Entrambe le espressioni `p + n` e `n + p` producono un puntatore di tipo `T*` risultante dalla somma di `n * sizeof(T)` all'indirizzo specificato da `p`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-155">Both `p + n` and `n + p` expressions produce a pointer of type `T*` that results from adding `n * sizeof(T)` to the address given by `p`.</span></span>
- <span data-ttu-id="42b5a-156">L'espressione `p - n` produce un puntatore di tipo `T*` risultante dalla sottrazione di `n * sizeof(T)` dall'indirizzo specificato da `p`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-156">The `p - n` expression produces a pointer of type `T*` that results from subtracting `n * sizeof(T)` from the address given by `p`.</span></span>

<span data-ttu-id="42b5a-157">L'operatore [`sizeof`](sizeof.md) ottiene la dimensione di un tipo in byte.</span><span class="sxs-lookup"><span data-stu-id="42b5a-157">The [`sizeof` operator](sizeof.md) obtains the size of a type in bytes.</span></span>

<span data-ttu-id="42b5a-158">L'esempio seguente illustra l'uso dell'operatore `+` con un puntatore:</span><span class="sxs-lookup"><span data-stu-id="42b5a-158">The following example demonstrates the usage of the `+` operator with a pointer:</span></span>

[!code-csharp[pointer addition](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#AddNumber)]

### <a name="pointer-subtraction"></a><span data-ttu-id="42b5a-159">Sottrazione di puntatori</span><span class="sxs-lookup"><span data-stu-id="42b5a-159">Pointer subtraction</span></span>

<span data-ttu-id="42b5a-160">Per i due puntatori `p1` e `p2` di tipo `T*`, l'espressione `p1 - p2` produce la differenza tra gli indirizzi specificati da `p1` e `p2` divisi per `sizeof(T)`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-160">For two pointers `p1` and `p2` of type `T*`, the expression `p1 - p2` produces the difference between the addresses given by `p1` and `p2` divided by `sizeof(T)`.</span></span> <span data-ttu-id="42b5a-161">Il tipo del risultato è `long`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-161">The type of the result is `long`.</span></span> <span data-ttu-id="42b5a-162">Ovvero, `p1 - p2` viene calcolato come `((long)(p1) - (long)(p2)) / sizeof(T)`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-162">That is, `p1 - p2` is computed as `((long)(p1) - (long)(p2)) / sizeof(T)`.</span></span>

<span data-ttu-id="42b5a-163">L'esempio seguente illustra la sottrazione del puntatore:</span><span class="sxs-lookup"><span data-stu-id="42b5a-163">The following example demonstrates the pointer subtraction:</span></span>

[!code-csharp[pointer subtraction](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#SubtractPointers)]

### <a name="pointer-increment-and-decrement"></a><span data-ttu-id="42b5a-164">Incremento e decremento dei puntatori</span><span class="sxs-lookup"><span data-stu-id="42b5a-164">Pointer increment and decrement</span></span>

<span data-ttu-id="42b5a-165">L'operatore di incremento `++`[somma](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 al relativo operando puntatore.</span><span class="sxs-lookup"><span data-stu-id="42b5a-165">The `++` increment operator [adds](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 to its pointer operand.</span></span> <span data-ttu-id="42b5a-166">L'operatore di decremento `--`[sottrae](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 dal relativo operando puntatore.</span><span class="sxs-lookup"><span data-stu-id="42b5a-166">The `--` decrement operator [subtracts](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 from its pointer operand.</span></span>

<span data-ttu-id="42b5a-167">Entrambi gli operatori sono supportati in due forme: come suffisso (`p++` e `p--`) e come prefisso (`++p` e `--p`).</span><span class="sxs-lookup"><span data-stu-id="42b5a-167">Both operators are supported in two forms: postfix (`p++` and `p--`) and prefix (`++p` and `--p`).</span></span> <span data-ttu-id="42b5a-168">Il risultato di `p++` e `p--` è il valore di `p` *prima* dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="42b5a-168">The result of `p++` and `p--` is the value of `p` *before* the operation.</span></span> <span data-ttu-id="42b5a-169">Il risultato di `++p` e `--p` è il valore di `p` *dopo* l'operazione.</span><span class="sxs-lookup"><span data-stu-id="42b5a-169">The result of `++p` and `--p` is the value of `p` *after* the operation.</span></span>

<span data-ttu-id="42b5a-170">L'esempio seguente illustra il comportamento di entrambi gli operatori di incremento suffisso e prefisso:</span><span class="sxs-lookup"><span data-stu-id="42b5a-170">The following example demonstrates the behavior of both postfix and prefix increment operators:</span></span>

[!code-csharp[pointer increment](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#Increment)]

## <a name="pointer-comparison-operators"></a><span data-ttu-id="42b5a-171">Operatori di confronto dei puntatori</span><span class="sxs-lookup"><span data-stu-id="42b5a-171">Pointer comparison operators</span></span>

<span data-ttu-id="42b5a-172">È possibile usare gli operatori `==`, `!=`, `<`, `>`, `<=` e `>=` per confrontare gli operandi di qualsiasi tipo di puntatore, incluso `void*`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-172">You can use the `==`, `!=`, `<`, `>`, `<=`, and `>=` operators to compare operands of any pointer type, including `void*`.</span></span> <span data-ttu-id="42b5a-173">Questi operatori confrontano gli indirizzi specificati dai due operandi come se fossero interi senza segno.</span><span class="sxs-lookup"><span data-stu-id="42b5a-173">Those operators compare the addresses given by the two operands as if they were unsigned integers.</span></span>

<span data-ttu-id="42b5a-174">Per informazioni sul comportamento di questi operatori per gli operandi di altri tipi, vedere gli articoli [Operatori di uguaglianza](equality-operators.md) e [Operatori di confronto](comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="42b5a-174">For information about the behavior of those operators for operands of other types, see the [Equality operators](equality-operators.md) and [Comparison operators](comparison-operators.md) articles.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="42b5a-175">Precedenza degli operatori</span><span class="sxs-lookup"><span data-stu-id="42b5a-175">Operator precedence</span></span>

<span data-ttu-id="42b5a-176">Nell'elenco seguente gli operatori correlati ai puntatori sono ordinati dalla precedenza più elevata a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="42b5a-176">The following list orders pointer related operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="42b5a-177">Operatori di incremento `x++` e decremento `x--` suffisso e operatori `->` e `[]`</span><span class="sxs-lookup"><span data-stu-id="42b5a-177">Postfix increment `x++` and decrement `x--` operators and the `->` and `[]` operators</span></span>
- <span data-ttu-id="42b5a-178">Operatori di incremento `++x` e decremento `--x` prefisso e operatori `&` e `*`</span><span class="sxs-lookup"><span data-stu-id="42b5a-178">Prefix increment `++x` and decrement `--x` operators and the `&` and `*` operators</span></span>
- <span data-ttu-id="42b5a-179">Operatori additivi `+` e `-`</span><span class="sxs-lookup"><span data-stu-id="42b5a-179">Additive `+` and `-` operators</span></span>
- <span data-ttu-id="42b5a-180">Operatori di confronto `<`, `>`, `<=` e `>=`</span><span class="sxs-lookup"><span data-stu-id="42b5a-180">Comparison `<`, `>`, `<=`, and `>=` operators</span></span>
- <span data-ttu-id="42b5a-181">Operatori di uguaglianza `==` e `!=`</span><span class="sxs-lookup"><span data-stu-id="42b5a-181">Equality `==` and `!=` operators</span></span>

<span data-ttu-id="42b5a-182">Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza tra gli operatori.</span><span class="sxs-lookup"><span data-stu-id="42b5a-182">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence.</span></span>

<span data-ttu-id="42b5a-183">Per l'elenco completo degli C# operatori ordinati in base al livello di precedenza, vedere la sezione [precedenza](index.md#operator-precedence) degli [ C# operatori](index.md) dell'articolo operatori.</span><span class="sxs-lookup"><span data-stu-id="42b5a-183">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="42b5a-184">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="42b5a-184">Operator overloadability</span></span>

<span data-ttu-id="42b5a-185">Un tipo definito dall'utente non può eseguire l'overload degli operatori correlati ai puntatori `&`, `*`, `->` e `[]`.</span><span class="sxs-lookup"><span data-stu-id="42b5a-185">A user-defined type cannot overload the pointer related operators `&`, `*`, `->`, and `[]`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="42b5a-186">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="42b5a-186">C# language specification</span></span>

<span data-ttu-id="42b5a-187">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="42b5a-187">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="42b5a-188">Variabili fisse e mobili</span><span class="sxs-lookup"><span data-stu-id="42b5a-188">Fixed and moveable variables</span></span>](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)
- [<span data-ttu-id="42b5a-189">Operatore address-of</span><span class="sxs-lookup"><span data-stu-id="42b5a-189">The address-of operator</span></span>](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)
- [<span data-ttu-id="42b5a-190">Riferimento indiretto a puntatore</span><span class="sxs-lookup"><span data-stu-id="42b5a-190">Pointer indirection</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-indirection)
- [<span data-ttu-id="42b5a-191">Accesso ai membri del puntatore</span><span class="sxs-lookup"><span data-stu-id="42b5a-191">Pointer member access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-member-access)
- [<span data-ttu-id="42b5a-192">Accesso agli elementi del puntatore</span><span class="sxs-lookup"><span data-stu-id="42b5a-192">Pointer element access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-element-access)
- [<span data-ttu-id="42b5a-193">Puntatore aritmetico</span><span class="sxs-lookup"><span data-stu-id="42b5a-193">Pointer arithmetic</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-arithmetic)
- [<span data-ttu-id="42b5a-194">Incremento e decremento dei puntatori</span><span class="sxs-lookup"><span data-stu-id="42b5a-194">Pointer increment and decrement</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-increment-and-decrement)
- [<span data-ttu-id="42b5a-195">Confronto tra puntatori</span><span class="sxs-lookup"><span data-stu-id="42b5a-195">Pointer comparison</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-comparison)

## <a name="see-also"></a><span data-ttu-id="42b5a-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42b5a-196">See also</span></span>

- [<span data-ttu-id="42b5a-197">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="42b5a-197">C# reference</span></span>](../index.md)
- [<span data-ttu-id="42b5a-198">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="42b5a-198">C# operators</span></span>](index.md)
- [<span data-ttu-id="42b5a-199">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="42b5a-199">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="42b5a-200">Parola chiave unsafe</span><span class="sxs-lookup"><span data-stu-id="42b5a-200">unsafe keyword</span></span>](../keywords/unsafe.md)
- [<span data-ttu-id="42b5a-201">Parola chiave fixed</span><span class="sxs-lookup"><span data-stu-id="42b5a-201">fixed keyword</span></span>](../keywords/fixed-statement.md)
- [<span data-ttu-id="42b5a-202">Operatore stackalloc</span><span class="sxs-lookup"><span data-stu-id="42b5a-202">stackalloc operator</span></span>](stackalloc.md)
- [<span data-ttu-id="42b5a-203">Operatore sizeof</span><span class="sxs-lookup"><span data-stu-id="42b5a-203">sizeof operator</span></span>](sizeof.md)
