---
title: Operatori di accesso ai membri - Riferimenti per C#
description: Informazioni sugli operatori C# che è possibile usare per accedere ai membri di tipo.
ms.date: 09/18/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
- ^_CSharpKeyword
- .._CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
- ^ operator [C#]
- index from end operator [C#]
- hat operator [C#]
- .. operator [C#]
- range operator [C#]
ms.openlocfilehash: 45af31d10d77f4c63b27b34595b97fdd11ef95a1
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71116127"
---
# <a name="member-access-operators-c-reference"></a><span data-ttu-id="c9643-103">Operatori di accesso ai membri (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c9643-103">Member access operators (C# reference)</span></span>

<span data-ttu-id="c9643-104">Quando si accede a un membro di tipo, è possibile utilizzare gli operatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9643-104">You might use the following operators when you access a type member:</span></span>

- <span data-ttu-id="c9643-105">[`.` (accesso ai membri)](#member-access-operator-): per accedere a un membro di uno spazio dei nomi o di tipo</span><span class="sxs-lookup"><span data-stu-id="c9643-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="c9643-106">[`[]` (accesso agli elementi della matrice o a indicizzatori)](#indexer-operator-): per accedere a un elemento della matrice o a un indicizzatore di tipo</span><span class="sxs-lookup"><span data-stu-id="c9643-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="c9643-107">[`?.` e `?[]` (operatori condizionali Null)](#null-conditional-operators--and-): per eseguire un'operazione di accesso a un membro o a un elemento solo se un operando è diverso da Null</span><span class="sxs-lookup"><span data-stu-id="c9643-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="c9643-108">[`()` (chiamata)](#invocation-operator-): per chiamare un metodo a cui si accede o per richiamare un delegato</span><span class="sxs-lookup"><span data-stu-id="c9643-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>
- <span data-ttu-id="c9643-109">[(indice dalla fine): per indicare che la posizione dell'elemento è dalla fine di una sequenza `^` ](#index-from-end-operator-)</span><span class="sxs-lookup"><span data-stu-id="c9643-109">[`^` (index from end)](#index-from-end-operator-): to indicate that the element position is from the end of a sequence</span></span>
- <span data-ttu-id="c9643-110">(intervallo): per specificare un intervallo di indici che è possibile usare per ottenere un intervallo di elementi di sequenza [ `..` ](#range-operator-)</span><span class="sxs-lookup"><span data-stu-id="c9643-110">[`..` (range)](#range-operator-): to specify a range of indices that you can use to obtain a range of sequence elements</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="c9643-111">Operatore di accesso ai membri .</span><span class="sxs-lookup"><span data-stu-id="c9643-111">Member access operator .</span></span>

<span data-ttu-id="c9643-112">Si usa il token `.` per accedere a un membro di uno spazio dei nomi o di un tipo, come illustrano gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9643-112">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="c9643-113">Usare `.` per accedere a uno spazio dei nomi annidato in uno spazio dei nomi, come illustra l'esempio seguente di [direttiva `using`](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="c9643-113">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="c9643-114">Usare `.` per formare un *nome qualificato* per accedere a un tipo in uno spazio dei nomi, come illustra il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c9643-114">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="c9643-115">Usare una [direttiva `using`](../keywords/using-directive.md) per rendere facoltativo l'uso di nomi qualificati.</span><span class="sxs-lookup"><span data-stu-id="c9643-115">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="c9643-116">Usare `.` per accedere ai [membri dei tipi](../../programming-guide/classes-and-structs/index.md#members), statici e non statici, come illustra il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c9643-116">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="c9643-117">È anche possibile usare `.` per accedere a un [metodo di estensione](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-117">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="c9643-118">Operatore indicizzatore []</span><span class="sxs-lookup"><span data-stu-id="c9643-118">Indexer operator []</span></span>

<span data-ttu-id="c9643-119">Le parentesi quadre `[]` vengono in genere usate per l'accesso agli elementi matrice, indicizzatore o puntatore.</span><span class="sxs-lookup"><span data-stu-id="c9643-119">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="c9643-120">Accesso a matrici</span><span class="sxs-lookup"><span data-stu-id="c9643-120">Array access</span></span>

<span data-ttu-id="c9643-121">Nell'esempio seguente viene illustrato come accedere agli elementi matrice:</span><span class="sxs-lookup"><span data-stu-id="c9643-121">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="c9643-122">Se un indice di matrice è fuori dai limiti della dimensione corrispondente di una matrice, viene generata un'eccezione <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="c9643-122">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="c9643-123">Come illustrato nell'esempio precedente, si usano le parentesi quadre anche per dichiarare un tipo di matrice o creare un'istanza di matrice.</span><span class="sxs-lookup"><span data-stu-id="c9643-123">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="c9643-124">Per altre informazioni sulle matrici, vedere [Matrici](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-124">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="c9643-125">Accesso all'indicizzatore</span><span class="sxs-lookup"><span data-stu-id="c9643-125">Indexer access</span></span>

<span data-ttu-id="c9643-126">Nell'esempio seguente viene usato il tipo .NET <xref:System.Collections.Generic.Dictionary%602> per dimostrare l'accesso all'indicizzatore:</span><span class="sxs-lookup"><span data-stu-id="c9643-126">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="c9643-127">Gli indicizzatori consentono di indicizzare le istanze di un tipo definito dall'utente con modalità simili a quelle dell'indicizzazione della matrice.</span><span class="sxs-lookup"><span data-stu-id="c9643-127">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="c9643-128">A differenza degli indici di matrice, che devono essere valori interi, gli argomenti dell'indicizzatore possono essere dichiarati con qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="c9643-128">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="c9643-129">Per altre informazioni sugli indicizzatori, vedere [Indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-129">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="c9643-130">Altri utilizzi di []</span><span class="sxs-lookup"><span data-stu-id="c9643-130">Other usages of []</span></span>

<span data-ttu-id="c9643-131">Per informazioni sull'accesso agli elementi del puntatore, vedere la sezione [Operatore [] (accesso agli elementi del puntatore)](pointer-related-operators.md#pointer-element-access-operator-) dell'articolo [Operatori relativi al puntatore](pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-131">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="c9643-132">Le parentesi quadre possono anche essere usate per specificare [attributi](../../programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="c9643-132">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="c9643-133">Operatori condizionali Null ?.</span><span class="sxs-lookup"><span data-stu-id="c9643-133">Null-conditional operators ?.</span></span> <span data-ttu-id="c9643-134">e ?[]</span><span class="sxs-lookup"><span data-stu-id="c9643-134">and ?[]</span></span>

<span data-ttu-id="c9643-135">Un operatore condizionale Null, disponibile in C# 6 e nelle versioni successive, applica un'operazione di accesso ai membri, `?.`, o di accesso a elementi, `?[]`, al relativo operando solo se l'operando restituisce un valore diverso da Null.</span><span class="sxs-lookup"><span data-stu-id="c9643-135">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="c9643-136">Se l'operando restituisce `null`, il risultato dell'applicazione dell'operatore è `null`.</span><span class="sxs-lookup"><span data-stu-id="c9643-136">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span> <span data-ttu-id="c9643-137">L'operatore di accesso ai membri condizionale Null `?.` è anche noto come operatore Elvis.</span><span class="sxs-lookup"><span data-stu-id="c9643-137">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

<span data-ttu-id="c9643-138">Gli operatori condizionali Null causano corto circuiti.</span><span class="sxs-lookup"><span data-stu-id="c9643-138">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="c9643-139">Vale a dire, se un'operazione in una catena di operazioni condizionali di accesso a un membro o a un elemento restituisce `null`, l'esecuzione delle altre operazioni della catena viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="c9643-139">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="c9643-140">Nell'esempio seguente `B` non viene valutato se `A` restituisce `null` e `C` non viene valutato se `A` oppure `B` restituisce `null`:</span><span class="sxs-lookup"><span data-stu-id="c9643-140">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="c9643-141">Nell'esempio seguente viene illustrato l'uso degli operatori `?.` e `?[]`:</span><span class="sxs-lookup"><span data-stu-id="c9643-141">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="c9643-142">L'esempio precedente mostra anche l'utilizzo dell'[operatore Null di coalescenza](null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-142">The preceding example also shows the usage of the [null-coalescing operator](null-coalescing-operator.md).</span></span> <span data-ttu-id="c9643-143">È possibile utilizzare l'operatore Null di coalescenza per creare un'espressione alternativa da valutare nel caso in cui il risultato dell'operazione condizionale Null sia `null`.</span><span class="sxs-lookup"><span data-stu-id="c9643-143">You might use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="c9643-144">Chiamata a delegati thread-safe</span><span class="sxs-lookup"><span data-stu-id="c9643-144">Thread-safe delegate invocation</span></span>

<span data-ttu-id="c9643-145">Usare l'operatore `?.` per controllare se un delegato è diverso da Null e richiamarlo in un modo thread-safe, ad esempio, quando si [genera un evento](../../../standard/events/how-to-raise-and-consume-events.md), come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c9643-145">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="c9643-146">Il codice equivale alla versione C# 5 o precedente del codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c9643-146">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="c9643-147">Operatore di chiamata ()</span><span class="sxs-lookup"><span data-stu-id="c9643-147">Invocation operator ()</span></span>

<span data-ttu-id="c9643-148">Usare le parentesi, `()`, per chiamare un [metodo](../../programming-guide/classes-and-structs/methods.md) oppure richiamare un [delegato](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-148">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="c9643-149">L'esempio seguente illustra come chiamare un metodo, con o senza argomenti, e come richiamare un delegato:</span><span class="sxs-lookup"><span data-stu-id="c9643-149">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="c9643-150">Le parentesi si usano anche per richiamare un [costruttore](../../programming-guide/classes-and-structs/constructors.md) con l'operatore [`new`](new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-150">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with the [`new`](new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="c9643-151">Altri utilizzi di ()</span><span class="sxs-lookup"><span data-stu-id="c9643-151">Other usages of ()</span></span>

<span data-ttu-id="c9643-152">È anche possibile usare le parentesi per specificare l'ordine in cui valutare le operazioni in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="c9643-152">You also use parentheses to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="c9643-153">Per altre informazioni, vedere [Operatori C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-153">For more information, see [C# operators](index.md).</span></span>

<span data-ttu-id="c9643-154">Anche le [espressioni cast](type-testing-and-cast.md#cast-operator-), che eseguono conversioni dei tipi esplicite, usano le parentesi.</span><span class="sxs-lookup"><span data-stu-id="c9643-154">[Cast expressions](type-testing-and-cast.md#cast-operator-), which perform explicit type conversions, also use parentheses.</span></span>

## <a name="index-from-end-operator-"></a><span data-ttu-id="c9643-155">Index from End Operator ^</span><span class="sxs-lookup"><span data-stu-id="c9643-155">Index from end operator ^</span></span>

<span data-ttu-id="c9643-156">Disponibile in C# 8,0 e versioni successive, `^` l'operatore indica la posizione dell'elemento alla fine di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="c9643-156">Available in C# 8.0 and later, the `^` operator indicates the element position from the end of a sequence.</span></span> <span data-ttu-id="c9643-157">Per una sequenza di lunghezza `length`, `^n` punta all'elemento con offset `length - n` dall'inizio di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="c9643-157">For a sequence of length `length`, `^n` points to the element with offset `length - n` from the start of a sequence.</span></span> <span data-ttu-id="c9643-158">Ad esempio, `^1` punta all'ultimo elemento di una sequenza e `^length` punta al primo elemento di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="c9643-158">For example, `^1` points to the last element of a sequence and `^length` points to the first element of a sequence.</span></span>

[!code-csharp[index from end](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#IndexFromEnd)]

<span data-ttu-id="c9643-159">Come illustrato nell'esempio precedente, Expression `^e` è <xref:System.Index?displayProperty=nameWithType> del tipo.</span><span class="sxs-lookup"><span data-stu-id="c9643-159">As the preceding example shows, expression `^e` is of the <xref:System.Index?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="c9643-160">Nell'espressione `^e`, il risultato di `e` deve `int`essere convertibile in modo implicito in.</span><span class="sxs-lookup"><span data-stu-id="c9643-160">In expression `^e`, the result of `e` must be implicitly convertible to `int`.</span></span>

<span data-ttu-id="c9643-161">Per creare un intervallo di `^` indici, è anche possibile usare l'operatore con l' [operatore Range](#range-operator-) .</span><span class="sxs-lookup"><span data-stu-id="c9643-161">You also can use the `^` operator with the [range operator](#range-operator-) to create a range of indices.</span></span> <span data-ttu-id="c9643-162">Per altre informazioni, vedere [indici e intervalli](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-162">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="range-operator-"></a><span data-ttu-id="c9643-163">Operatore di intervallo..</span><span class="sxs-lookup"><span data-stu-id="c9643-163">Range operator ..</span></span>

<span data-ttu-id="c9643-164">Disponibile in C# 8,0 e versioni successive, `..` l'operatore specifica l'inizio e la fine di un intervallo di indici come operandi.</span><span class="sxs-lookup"><span data-stu-id="c9643-164">Available in C# 8.0 and later, the `..` operator specifies the start and end of a range of indices as its operands.</span></span> <span data-ttu-id="c9643-165">L'operando sinistro è un inizio *inclusivo* di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="c9643-165">The left-hand operand is an *inclusive* start of a range.</span></span> <span data-ttu-id="c9643-166">L'operando destro è una fine *esclusiva* di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="c9643-166">The right-hand operand is an *exclusive* end of a range.</span></span> <span data-ttu-id="c9643-167">Uno degli operandi può essere un indice dall'inizio o dalla fine di una sequenza, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c9643-167">Either of operands can be an index from the start or from the end of a sequence, as the following example shows:</span></span>

[!code-csharp[range examples](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Ranges)]

<span data-ttu-id="c9643-168">Come illustrato nell'esempio precedente, Expression `a..b` è <xref:System.Range?displayProperty=nameWithType> del tipo.</span><span class="sxs-lookup"><span data-stu-id="c9643-168">As the preceding example shows, expression `a..b` is of the <xref:System.Range?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="c9643-169">Nell'espressione `a..b`i risultati di `a` e `b` devono essere convertibili `int` in modo implicito <xref:System.Index>in o.</span><span class="sxs-lookup"><span data-stu-id="c9643-169">In expression `a..b`, the results of `a` and `b` must be implicitly convertible to `int` or <xref:System.Index>.</span></span>

<span data-ttu-id="c9643-170">È possibile omettere gli operandi dell' `..` operatore per ottenere un intervallo aperto:</span><span class="sxs-lookup"><span data-stu-id="c9643-170">You can omit any of the operands of the `..` operator to obtain an open-ended range:</span></span>

- <span data-ttu-id="c9643-171">`a..`equivale a`a..^0`</span><span class="sxs-lookup"><span data-stu-id="c9643-171">`a..` is equivalent to `a..^0`</span></span>
- <span data-ttu-id="c9643-172">`..b`equivale a`0..b`</span><span class="sxs-lookup"><span data-stu-id="c9643-172">`..b` is equivalent to `0..b`</span></span>
- <span data-ttu-id="c9643-173">`..`equivale a`0..^0`</span><span class="sxs-lookup"><span data-stu-id="c9643-173">`..` is equivalent to `0..^0`</span></span>

[!code-csharp[ranges with omitted operands](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#RangesOptional)]

<span data-ttu-id="c9643-174">Per altre informazioni, vedere [indici e intervalli](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-174">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c9643-175">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="c9643-175">Operator overloadability</span></span>

<span data-ttu-id="c9643-176">Non è possibile `^`eseguire l' `..` overload degli `.`operatori, ,e.`()`</span><span class="sxs-lookup"><span data-stu-id="c9643-176">The `.`, `()`, `^`, and `..` operators cannot be overloaded.</span></span> <span data-ttu-id="c9643-177">Anche l'operatore `[]` viene considerato un operatore che non supporta l'overload.</span><span class="sxs-lookup"><span data-stu-id="c9643-177">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="c9643-178">Per il supporto dell'indicizzazione con tipi definiti dall'utente, usare gli [indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="c9643-178">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c9643-179">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c9643-179">C# language specification</span></span>

<span data-ttu-id="c9643-180">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="c9643-180">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="c9643-181">Accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="c9643-181">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="c9643-182">Accesso a elementi</span><span class="sxs-lookup"><span data-stu-id="c9643-182">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="c9643-183">Operatori condizionali Null</span><span class="sxs-lookup"><span data-stu-id="c9643-183">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="c9643-184">Espressioni di chiamata</span><span class="sxs-lookup"><span data-stu-id="c9643-184">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a><span data-ttu-id="c9643-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9643-185">See also</span></span>

- [<span data-ttu-id="c9643-186">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c9643-186">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c9643-187">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="c9643-187">C# operators</span></span>](index.md)
- [<span data-ttu-id="c9643-188"> ?? (operatore null-coalescing)</span><span class="sxs-lookup"><span data-stu-id="c9643-188">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="c9643-189">Operatore ::</span><span class="sxs-lookup"><span data-stu-id="c9643-189">:: operator</span></span>](namespace-alias-qualifier.md)
