---
title: Operatori di accesso ai membri ed espressioni-riferimenti per C#
description: Informazioni sugli operatori C# che è possibile usare per accedere ai membri di tipo.
ms.date: 04/17/2020
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
ms.openlocfilehash: 86c8cce79e447bee638e1c5c7cb2fdbc64f630f3
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595897"
---
# <a name="member-access-operators-and-expressions-c-reference"></a><span data-ttu-id="5c6f9-103">Operatori di accesso ai membri ed espressioni (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5c6f9-103">Member access operators and expressions (C# reference)</span></span>

<span data-ttu-id="5c6f9-104">Quando si accede a un membro di un tipo, è possibile utilizzare gli operatori e le espressioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-104">You can use the following operators and expressions when you access a type member:</span></span>

- <span data-ttu-id="5c6f9-105">[(accesso ai membri): per accedere a un membro di uno spazio dei nomi o di un tipo `.` ](#member-access-expression-)</span><span class="sxs-lookup"><span data-stu-id="5c6f9-105">[`.` (member access)](#member-access-expression-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="5c6f9-106">[(accesso all'elemento della matrice o all'indicizzatore): per accedere a un elemento di matrice o a un indicizzatore di tipo `[]` ](#indexer-operator-)</span><span class="sxs-lookup"><span data-stu-id="5c6f9-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="5c6f9-107">[and `?[]` operatori condizionali null): per eseguire un'operazione di accesso a un membro o a un elemento solo se un operando è `?.` ](#null-conditional-operators--and-)non null</span><span class="sxs-lookup"><span data-stu-id="5c6f9-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="5c6f9-108">(chiamata): per chiamare un metodo a cui si accede o richiamare un delegato [ `()` ](#invocation-expression-)</span><span class="sxs-lookup"><span data-stu-id="5c6f9-108">[`()` (invocation)](#invocation-expression-): to call an accessed method or invoke a delegate</span></span>
- <span data-ttu-id="5c6f9-109">[(indice dalla fine): per indicare che la posizione dell'elemento è dalla fine di una sequenza `^` ](#index-from-end-operator-)</span><span class="sxs-lookup"><span data-stu-id="5c6f9-109">[`^` (index from end)](#index-from-end-operator-): to indicate that the element position is from the end of a sequence</span></span>
- <span data-ttu-id="5c6f9-110">(intervallo): per specificare un intervallo di indici che è possibile usare per ottenere un intervallo di elementi di sequenza [ `..` ](#range-operator-)</span><span class="sxs-lookup"><span data-stu-id="5c6f9-110">[`..` (range)](#range-operator-): to specify a range of indices that you can use to obtain a range of sequence elements</span></span>

## <a name="member-access-expression-"></a><span data-ttu-id="5c6f9-111">Espressione di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-111">Member access expression .</span></span>

<span data-ttu-id="5c6f9-112">Si usa il token `.` per accedere a un membro di uno spazio dei nomi o di un tipo, come illustrano gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-112">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="5c6f9-113">Utilizzare `.` per accedere a uno spazio dei nomi annidato all'interno di uno spazio dei nomi, come illustrato nell'esempio seguente di una [ `using` direttiva](../keywords/using-directive.md) :</span><span class="sxs-lookup"><span data-stu-id="5c6f9-113">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](snippets/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="5c6f9-114">Usare `.` per formare un *nome qualificato* per accedere a un tipo in uno spazio dei nomi, come illustra il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-114">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](snippets/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="5c6f9-115">Usare una [ `using` direttiva](../keywords/using-directive.md) per rendere facoltativo l'uso di nomi qualificati.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-115">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="5c6f9-116">Usare `.` per accedere ai [membri dei tipi](../../programming-guide/classes-and-structs/index.md#members), statici e non statici, come illustra il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-116">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](snippets/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="5c6f9-117">È anche possibile usare `.` per accedere a un [metodo di estensione](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-117">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="5c6f9-118">Operatore indicizzatore []</span><span class="sxs-lookup"><span data-stu-id="5c6f9-118">Indexer operator []</span></span>

<span data-ttu-id="5c6f9-119">Le parentesi quadre `[]` vengono in genere usate per l'accesso agli elementi matrice, indicizzatore o puntatore.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-119">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="5c6f9-120">Accesso a matrici</span><span class="sxs-lookup"><span data-stu-id="5c6f9-120">Array access</span></span>

<span data-ttu-id="5c6f9-121">Nell'esempio seguente viene illustrato come accedere agli elementi matrice:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-121">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](snippets/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="5c6f9-122">Se un indice di matrice è fuori dai limiti della dimensione corrispondente di una matrice, viene generata un'eccezione <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-122">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="5c6f9-123">Come illustrato nell'esempio precedente, si usano le parentesi quadre anche per dichiarare un tipo di matrice o creare un'istanza di matrice.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-123">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="5c6f9-124">Per altre informazioni sulle matrici, vedere [Matrici](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-124">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="5c6f9-125">Accesso all'indicizzatore</span><span class="sxs-lookup"><span data-stu-id="5c6f9-125">Indexer access</span></span>

<span data-ttu-id="5c6f9-126">Nell'esempio seguente viene usato il <xref:System.Collections.Generic.Dictionary%602> tipo .NET per dimostrare l'accesso dell'indicizzatore:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-126">The following example uses the .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](snippets/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="5c6f9-127">Gli indicizzatori consentono di indicizzare le istanze di un tipo definito dall'utente con modalità simili a quelle dell'indicizzazione della matrice.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-127">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="5c6f9-128">A differenza degli indici di matrice, che devono essere numeri interi, i parametri dell'indicizzatore possono essere dichiarati come di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-128">Unlike array indices, which must be integer, the indexer parameters can be declared to be of any type.</span></span>

<span data-ttu-id="5c6f9-129">Per altre informazioni sugli indicizzatori, vedere [Indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-129">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="5c6f9-130">Altri utilizzi di []</span><span class="sxs-lookup"><span data-stu-id="5c6f9-130">Other usages of []</span></span>

<span data-ttu-id="5c6f9-131">Per informazioni sull'accesso agli elementi del puntatore, vedere la sezione [Operatore [] (accesso agli elementi del puntatore)](pointer-related-operators.md#pointer-element-access-operator-) dell'articolo [Operatori relativi al puntatore](pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-131">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="5c6f9-132">Le parentesi quadre possono anche essere usate per specificare [attributi](../../programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="5c6f9-132">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="5c6f9-133">Operatori condizionali Null ?.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-133">Null-conditional operators ?.</span></span> <span data-ttu-id="5c6f9-134">e ?[]</span><span class="sxs-lookup"><span data-stu-id="5c6f9-134">and ?[]</span></span>

<span data-ttu-id="5c6f9-135">Disponibile in C# 6 e versioni successive, un operatore condizionale null applica [member access](#member-access-expression-)un'operazione di `?.`accesso ai membri, o `?[]` [l'accesso agli elementi](#indexer-operator-),, all'operando solo se tale operando restituisce un valore non null. in caso contrario, `null`restituisce.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-135">Available in C# 6 and later, a null-conditional operator applies a [member access](#member-access-expression-), `?.`, or [element access](#indexer-operator-), `?[]`, operation to its operand only if that operand evaluates to non-null; otherwise, it returns `null`.</span></span> <span data-ttu-id="5c6f9-136">Cioè</span><span class="sxs-lookup"><span data-stu-id="5c6f9-136">That is,</span></span>

- <span data-ttu-id="5c6f9-137">Se `a` restituisce `null`, il risultato di `a?.x` o `a?[x]` è. `null`</span><span class="sxs-lookup"><span data-stu-id="5c6f9-137">If `a` evaluates to `null`, the result of `a?.x` or `a?[x]` is `null`.</span></span>
- <span data-ttu-id="5c6f9-138">Se `a` restituisce un valore diverso da null, il risultato di `a?.x` o `a?[x]` è uguale al risultato di `a.x` o `a[x]`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-138">If `a` evaluates to non-null, the result of `a?.x` or `a?[x]` is the same as the result of `a.x` or `a[x]`, respectively.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5c6f9-139">Se `a.x` o `a[x]` genera un'eccezione `a?.x` o `a?[x]` genera la stessa eccezione per un valore diverso da null `a`.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-139">If `a.x` or `a[x]` throws an exception, `a?.x` or `a?[x]` would throw the same exception for non-null `a`.</span></span> <span data-ttu-id="5c6f9-140">Se `a` , ad esempio, è un'istanza di matrice non null `x` ed è all'esterno dei limiti `a`di `a?[x]` , genera un' <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-140">For example, if `a` is a non-null array instance and `x` is outside the bounds of `a`, `a?[x]` would throw an <xref:System.IndexOutOfRangeException>.</span></span>

<span data-ttu-id="5c6f9-141">Gli operatori condizionali Null causano corto circuiti.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-141">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="5c6f9-142">Vale a dire, se un'operazione in una catena di operazioni condizionali di accesso a un membro o a un elemento restituisce `null`, l'esecuzione delle altre operazioni della catena viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-142">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="5c6f9-143">Nell'esempio seguente `B` non viene valutato se `A` restituisce `null` e `C` non viene valutato se `A` oppure `B` restituisce `null`:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-143">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="5c6f9-144">Nell'esempio seguente viene illustrato l'uso degli operatori `?.` e `?[]`:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-144">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](snippets/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="5c6f9-145">Nell'esempio precedente viene inoltre usato l' [operatore `??` ](null-coalescing-operator.md) di Unione null per specificare un'espressione alternativa da valutare se il risultato di un'operazione condizionale null è. `null`</span><span class="sxs-lookup"><span data-stu-id="5c6f9-145">The preceding example also uses the [null-coalescing operator `??`](null-coalescing-operator.md) to specify an alternative expression to evaluate in case the result of a null-conditional operation is `null`.</span></span>

<span data-ttu-id="5c6f9-146">Se `a.x` o `a[x]` è di un tipo `T` `a?.x` di valore non nullable oppure `a?[x]` è del tipo `T?`di [valore Nullable](../builtin-types/nullable-value-types.md) corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-146">If `a.x` or `a[x]` is of a non-nullable value type `T`, `a?.x` or `a?[x]` is of the corresponding [nullable value type](../builtin-types/nullable-value-types.md) `T?`.</span></span> <span data-ttu-id="5c6f9-147">Se è necessaria un'espressione di tipo `T`, applicare l'operatore `??` di Unione null a un'espressione condizionale null, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-147">If you need an expression of type `T`, apply the null-coalescing operator `??` to a null-conditional expression, as the following example shows:</span></span>

[!code-csharp-interactive[null-conditional with null-coalescing](snippets/MemberAccessOperators.cs#NullConditionalWithNullCoalescing)]

<span data-ttu-id="5c6f9-148">Nell'esempio precedente, se non `??` si usa l'operatore, `numbers?.Length < 2` restituisce `false` quando `numbers` è. `null`</span><span class="sxs-lookup"><span data-stu-id="5c6f9-148">In the preceding example, if you don't use the `??` operator, `numbers?.Length < 2` evaluates to `false` when `numbers` is `null`.</span></span>

<span data-ttu-id="5c6f9-149">L'operatore di accesso ai membri condizionale Null `?.` è anche noto come operatore Elvis.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-149">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

> [!NOTE]
> <span data-ttu-id="5c6f9-150">In C# 8, gli operatori condizionali null interagiscono con l' [operatore che perdona i valori null](null-forgiving.md) in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-150">In C# 8, the null-conditional operators interacts with the [null-forgiving operator](null-forgiving.md) in an unexpected way.</span></span> <span data-ttu-id="5c6f9-151">Ad esempio, l'espressione `x?.y!.z` viene analizzata come `(x?.y)!.z`.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-151">For example, the expression `x?.y!.z` is parsed as `(x?.y)!.z`.</span></span> <span data-ttu-id="5c6f9-152">A causa di questa interpretazione `z` , viene valutato anche `x` se `null`è, che può produrre un <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-152">Due to this interpretation, `z` is evaluated even if `x` is `null`, which may result in a <xref:System.NullReferenceException>.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="5c6f9-153">Chiamata a delegati thread-safe</span><span class="sxs-lookup"><span data-stu-id="5c6f9-153">Thread-safe delegate invocation</span></span>

<span data-ttu-id="5c6f9-154">Usare l'operatore `?.` per controllare se un delegato è diverso da Null e richiamarlo in un modo thread-safe, ad esempio, quando si [genera un evento](../../../standard/events/how-to-raise-and-consume-events.md), come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-154">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="5c6f9-155">Il codice equivale alla versione C# 5 o precedente del codice seguente:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-155">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

<span data-ttu-id="5c6f9-156">Si tratta di un metodo thread-safe per assicurarsi che venga richiamato solo `handler` un valore non null.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-156">That is a thread-safe way to ensure that only a non-null `handler` is invoked.</span></span> <span data-ttu-id="5c6f9-157">Poiché le istanze di delegati non sono modificabili, nessun thread può modificare il `handler` valore a cui fa riferimento la variabile locale.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-157">Because delegate instances are immutable, no thread can change the value referenced by the `handler` local variable.</span></span> <span data-ttu-id="5c6f9-158">In particolare, se il codice eseguito da un altro thread annulla la sottoscrizione dell' `PropertyChanged` evento e `PropertyChanged` diventa `null` prima `handler` che venga richiamato, il valore a `handler` cui fa riferimento rimane inalterato.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-158">In particular, if the code executed by another thread unsubscribes from the `PropertyChanged` event and `PropertyChanged` becomes `null` before `handler` is invoked, the value referenced by `handler` remains unaffected.</span></span> <span data-ttu-id="5c6f9-159">L' `?.` operatore valuta l'operando sinistro non più di una volta, garantendo che non possa essere modificato in `null` dopo essere stato verificato come non null.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-159">The `?.` operator evaluates its left-hand operand no more than once, guaranteeing that it cannot be changed to `null` after being verified as non-null.</span></span>

## <a name="invocation-expression-"></a><span data-ttu-id="5c6f9-160">Espressione di chiamata ()</span><span class="sxs-lookup"><span data-stu-id="5c6f9-160">Invocation expression ()</span></span>

<span data-ttu-id="5c6f9-161">Usare le parentesi, `()`, per chiamare un [metodo](../../programming-guide/classes-and-structs/methods.md) oppure richiamare un [delegato](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-161">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="5c6f9-162">L'esempio seguente illustra come chiamare un metodo, con o senza argomenti, e come richiamare un delegato:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-162">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](snippets/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="5c6f9-163">Le parentesi si usano anche per richiamare un [costruttore](../../programming-guide/classes-and-structs/constructors.md) con l'operatore [`new`](new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-163">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with the [`new`](new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="5c6f9-164">Altri utilizzi di ()</span><span class="sxs-lookup"><span data-stu-id="5c6f9-164">Other usages of ()</span></span>

<span data-ttu-id="5c6f9-165">È anche possibile usare le parentesi per specificare l'ordine in cui valutare le operazioni in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-165">You also use parentheses to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="5c6f9-166">Per altre informazioni, vedere [Operatori C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-166">For more information, see [C# operators](index.md).</span></span>

<span data-ttu-id="5c6f9-167">Anche le [espressioni cast](type-testing-and-cast.md#cast-expression), che eseguono conversioni dei tipi esplicite, usano le parentesi.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-167">[Cast expressions](type-testing-and-cast.md#cast-expression), which perform explicit type conversions, also use parentheses.</span></span>

## <a name="index-from-end-operator-"></a><span data-ttu-id="5c6f9-168">Index from End Operator ^</span><span class="sxs-lookup"><span data-stu-id="5c6f9-168">Index from end operator ^</span></span>

<span data-ttu-id="5c6f9-169">Disponibile in C# 8,0 e versioni successive, `^` l'operatore indica la posizione dell'elemento alla fine di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-169">Available in C# 8.0 and later, the `^` operator indicates the element position from the end of a sequence.</span></span> <span data-ttu-id="5c6f9-170">Per una sequenza di lunghezza `length`, `^n` punta all'elemento con offset `length - n` dall'inizio di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-170">For a sequence of length `length`, `^n` points to the element with offset `length - n` from the start of a sequence.</span></span> <span data-ttu-id="5c6f9-171">Ad esempio, `^1` punta all'ultimo elemento di una sequenza e `^length` punta al primo elemento di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-171">For example, `^1` points to the last element of a sequence and `^length` points to the first element of a sequence.</span></span>

[!code-csharp[index from end](snippets/MemberAccessOperators.cs#IndexFromEnd)]

<span data-ttu-id="5c6f9-172">Come illustrato nell'esempio precedente, Expression `^e` è del <xref:System.Index?displayProperty=nameWithType> tipo.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-172">As the preceding example shows, expression `^e` is of the <xref:System.Index?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="5c6f9-173">Nell'espressione `^e`, il risultato di `e` deve essere convertibile in modo `int`implicito in.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-173">In expression `^e`, the result of `e` must be implicitly convertible to `int`.</span></span>

<span data-ttu-id="5c6f9-174">Per creare un intervallo di `^` indici, è anche possibile usare l'operatore con l' [operatore Range](#range-operator-) .</span><span class="sxs-lookup"><span data-stu-id="5c6f9-174">You can also use the `^` operator with the [range operator](#range-operator-) to create a range of indices.</span></span> <span data-ttu-id="5c6f9-175">Per altre informazioni, vedere [indici e intervalli](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-175">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="range-operator-"></a><span data-ttu-id="5c6f9-176">Operatore di intervallo..</span><span class="sxs-lookup"><span data-stu-id="5c6f9-176">Range operator ..</span></span>

<span data-ttu-id="5c6f9-177">Disponibile in C# 8,0 e versioni successive, `..` l'operatore specifica l'inizio e la fine di un intervallo di indici come operandi.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-177">Available in C# 8.0 and later, the `..` operator specifies the start and end of a range of indices as its operands.</span></span> <span data-ttu-id="5c6f9-178">L'operando sinistro è un inizio *inclusivo* di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-178">The left-hand operand is an *inclusive* start of a range.</span></span> <span data-ttu-id="5c6f9-179">L'operando destro è una fine *esclusiva* di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-179">The right-hand operand is an *exclusive* end of a range.</span></span> <span data-ttu-id="5c6f9-180">Uno degli operandi può essere un indice dall'inizio o dalla fine di una sequenza, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-180">Either of operands can be an index from the start or from the end of a sequence, as the following example shows:</span></span>

[!code-csharp[range examples](snippets/MemberAccessOperators.cs#Ranges)]

<span data-ttu-id="5c6f9-181">Come illustrato nell'esempio precedente, Expression `a..b` è del <xref:System.Range?displayProperty=nameWithType> tipo.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-181">As the preceding example shows, expression `a..b` is of the <xref:System.Range?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="5c6f9-182">Nell'espressione `a..b` `a` i risultati di `b` e devono essere convertibili in modo implicito in `int` o. <xref:System.Index></span><span class="sxs-lookup"><span data-stu-id="5c6f9-182">In expression `a..b`, the results of `a` and `b` must be implicitly convertible to `int` or <xref:System.Index>.</span></span>

<span data-ttu-id="5c6f9-183">È possibile omettere gli operandi dell' `..` operatore per ottenere un intervallo aperto:</span><span class="sxs-lookup"><span data-stu-id="5c6f9-183">You can omit any of the operands of the `..` operator to obtain an open-ended range:</span></span>

- <span data-ttu-id="5c6f9-184">`a..`equivale a`a..^0`</span><span class="sxs-lookup"><span data-stu-id="5c6f9-184">`a..` is equivalent to `a..^0`</span></span>
- <span data-ttu-id="5c6f9-185">`..b`equivale a`0..b`</span><span class="sxs-lookup"><span data-stu-id="5c6f9-185">`..b` is equivalent to `0..b`</span></span>
- <span data-ttu-id="5c6f9-186">`..`equivale a`0..^0`</span><span class="sxs-lookup"><span data-stu-id="5c6f9-186">`..` is equivalent to `0..^0`</span></span>

[!code-csharp[ranges with omitted operands](snippets/MemberAccessOperators.cs#RangesOptional)]

<span data-ttu-id="5c6f9-187">Per altre informazioni, vedere [indici e intervalli](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-187">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5c6f9-188">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="5c6f9-188">Operator overloadability</span></span>

<span data-ttu-id="5c6f9-189">Non `.`è `()`possibile `^`eseguire l' `..` overload degli operatori,, e.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-189">The `.`, `()`, `^`, and `..` operators cannot be overloaded.</span></span> <span data-ttu-id="5c6f9-190">Anche l'operatore `[]` viene considerato un operatore che non supporta l'overload.</span><span class="sxs-lookup"><span data-stu-id="5c6f9-190">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="5c6f9-191">Per il supporto dell'indicizzazione con tipi definiti dall'utente, usare gli [indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-191">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5c6f9-192">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="5c6f9-192">C# language specification</span></span>

<span data-ttu-id="5c6f9-193">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="5c6f9-193">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="5c6f9-194">Accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="5c6f9-194">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="5c6f9-195">Accesso a elementi</span><span class="sxs-lookup"><span data-stu-id="5c6f9-195">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="5c6f9-196">Operatori condizionali Null</span><span class="sxs-lookup"><span data-stu-id="5c6f9-196">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="5c6f9-197">Espressioni di chiamata</span><span class="sxs-lookup"><span data-stu-id="5c6f9-197">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

<span data-ttu-id="5c6f9-198">Per ulteriori informazioni sugli indici e sugli intervalli, vedere la [Nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-8.0/ranges.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f9-198">For more information about indices and ranges, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5c6f9-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c6f9-199">See also</span></span>

- [<span data-ttu-id="5c6f9-200">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="5c6f9-200">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5c6f9-201">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="5c6f9-201">C# operators</span></span>](index.md)
- <span data-ttu-id="5c6f9-202">[?? (null-coalescing operator)](null-coalescing-operator.md) ?? (operatore null-coalescing)</span><span class="sxs-lookup"><span data-stu-id="5c6f9-202">[?? (null-coalescing operator)](null-coalescing-operator.md)</span></span>
- [<span data-ttu-id="5c6f9-203">Operatore::</span><span class="sxs-lookup"><span data-stu-id="5c6f9-203">:: operator</span></span>](namespace-alias-qualifier.md)
