---
title: Operatori di accesso ai membri - Riferimenti per C#
description: Informazioni sugli operatori C# che è possibile usare per accedere ai membri di tipo.
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
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
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
ms.openlocfilehash: a76c2855196b229918ee0a6a7d2a4dc66d87d059
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881038"
---
# <a name="member-access-operators-c-reference"></a><span data-ttu-id="814c7-103">Operatori di accesso ai membri (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="814c7-103">Member access operators (C# Reference)</span></span>

<span data-ttu-id="814c7-104">Quando si accede a un membro di tipo, è possibile utilizzare gli operatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="814c7-104">You might use the following operators when you access a type member:</span></span>

- <span data-ttu-id="814c7-105">[`.` (accesso ai membri)](#member-access-operator-): per accedere a un membro di uno spazio dei nomi o di tipo</span><span class="sxs-lookup"><span data-stu-id="814c7-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="814c7-106">[`[]` (accesso agli elementi della matrice o a indicizzatori)](#indexer-operator-): per accedere a un elemento della matrice o a un indicizzatore di tipo</span><span class="sxs-lookup"><span data-stu-id="814c7-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="814c7-107">[`?.` e `?[]` (operatori condizionali Null)](#null-conditional-operators--and-): per eseguire un'operazione di accesso a un membro o a un elemento solo se un operando è diverso da Null</span><span class="sxs-lookup"><span data-stu-id="814c7-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="814c7-108">[`()` (chiamata)](#invocation-operator-): per chiamare un metodo a cui si accede o per richiamare un delegato</span><span class="sxs-lookup"><span data-stu-id="814c7-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="814c7-109">Operatore di accesso ai membri .</span><span class="sxs-lookup"><span data-stu-id="814c7-109">Member access operator .</span></span>

<span data-ttu-id="814c7-110">Si usa il token `.` per accedere a un membro di uno spazio dei nomi o di un tipo, come illustrano gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="814c7-110">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="814c7-111">Usare `.` per accedere a uno spazio dei nomi annidato in uno spazio dei nomi, come illustra l'esempio seguente di [direttiva `using`](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="814c7-111">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="814c7-112">Usare `.` per formare un *nome qualificato* per accedere a un tipo in uno spazio dei nomi, come illustra il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="814c7-112">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="814c7-113">Usare una [direttiva `using`](../keywords/using-directive.md) per rendere facoltativo l'uso di nomi qualificati.</span><span class="sxs-lookup"><span data-stu-id="814c7-113">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="814c7-114">Usare `.` per accedere ai [membri dei tipi](../../programming-guide/classes-and-structs/index.md#members), statici e non statici, come illustra il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="814c7-114">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="814c7-115">È anche possibile usare `.` per accedere a un [metodo di estensione](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="814c7-115">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="814c7-116">Operatore indicizzatore []</span><span class="sxs-lookup"><span data-stu-id="814c7-116">Indexer operator []</span></span>

<span data-ttu-id="814c7-117">Le parentesi quadre `[]` vengono in genere usate per l'accesso agli elementi matrice, indicizzatore o puntatore.</span><span class="sxs-lookup"><span data-stu-id="814c7-117">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="814c7-118">Accesso a matrici</span><span class="sxs-lookup"><span data-stu-id="814c7-118">Array access</span></span>

<span data-ttu-id="814c7-119">Nell'esempio seguente viene illustrato come accedere agli elementi matrice:</span><span class="sxs-lookup"><span data-stu-id="814c7-119">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="814c7-120">Se un indice di matrice è fuori dai limiti della dimensione corrispondente di una matrice, viene generata un'eccezione <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="814c7-120">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="814c7-121">Come illustrato nell'esempio precedente, si usano le parentesi quadre anche per dichiarare un tipo di matrice o creare un'istanza di matrice.</span><span class="sxs-lookup"><span data-stu-id="814c7-121">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="814c7-122">Per altre informazioni sulle matrici, vedere [Matrici](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="814c7-122">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="814c7-123">Accesso all'indicizzatore</span><span class="sxs-lookup"><span data-stu-id="814c7-123">Indexer access</span></span>

<span data-ttu-id="814c7-124">Nell'esempio seguente viene usato il tipo .NET <xref:System.Collections.Generic.Dictionary%602> per dimostrare l'accesso all'indicizzatore:</span><span class="sxs-lookup"><span data-stu-id="814c7-124">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="814c7-125">Gli indicizzatori consentono di indicizzare le istanze di un tipo definito dall'utente con modalità simili a quelle dell'indicizzazione della matrice.</span><span class="sxs-lookup"><span data-stu-id="814c7-125">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="814c7-126">A differenza degli indici di matrice, che devono essere valori interi, gli argomenti dell'indicizzatore possono essere dichiarati con qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="814c7-126">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="814c7-127">Per altre informazioni sugli indicizzatori, vedere [Indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="814c7-127">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="814c7-128">Altri utilizzi di []</span><span class="sxs-lookup"><span data-stu-id="814c7-128">Other usages of []</span></span>

<span data-ttu-id="814c7-129">Per informazioni sull'accesso agli elementi del puntatore, vedere la sezione [Operatore [] (accesso agli elementi del puntatore)](pointer-related-operators.md#pointer-element-access-operator-) dell'articolo [Operatori relativi al puntatore](pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="814c7-129">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="814c7-130">Le parentesi quadre possono anche essere usate per specificare [attributi](../../programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="814c7-130">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="814c7-131">Operatori condizionali Null ?.</span><span class="sxs-lookup"><span data-stu-id="814c7-131">Null-conditional operators ?.</span></span> <span data-ttu-id="814c7-132">e ?[]</span><span class="sxs-lookup"><span data-stu-id="814c7-132">and ?[]</span></span>

<span data-ttu-id="814c7-133">Un operatore condizionale Null, disponibile in C# 6 e nelle versioni successive, applica un'operazione di accesso ai membri, `?.`, o di accesso a elementi, `?[]`, al relativo operando solo se l'operando restituisce un valore diverso da Null.</span><span class="sxs-lookup"><span data-stu-id="814c7-133">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="814c7-134">Se l'operando restituisce `null`, il risultato dell'applicazione dell'operatore è `null`.</span><span class="sxs-lookup"><span data-stu-id="814c7-134">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span>

<span data-ttu-id="814c7-135">Gli operatori condizionali Null causano corto circuiti.</span><span class="sxs-lookup"><span data-stu-id="814c7-135">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="814c7-136">Vale a dire, se un'operazione in una catena di operazioni condizionali di accesso a un membro o a un elemento restituisce `null`, l'esecuzione delle altre operazioni della catena viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="814c7-136">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="814c7-137">Nell'esempio seguente `B` non viene valutato se `A` restituisce `null` e `C` non viene valutato se `A` oppure `B` restituisce `null`:</span><span class="sxs-lookup"><span data-stu-id="814c7-137">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="814c7-138">Nell'esempio seguente viene illustrato l'uso degli operatori `?.` e `?[]`:</span><span class="sxs-lookup"><span data-stu-id="814c7-138">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="814c7-139">L'esempio precedente mostra anche l'utilizzo dell'[operatore Null di coalescenza](null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="814c7-139">The preceding example also shows the usage of the [null-coalescing operator](null-coalescing-operator.md).</span></span> <span data-ttu-id="814c7-140">È possibile utilizzare l'operatore Null di coalescenza per creare un'espressione alternativa da valutare nel caso in cui il risultato dell'operazione condizionale Null sia `null`.</span><span class="sxs-lookup"><span data-stu-id="814c7-140">You might use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="814c7-141">Chiamata a delegati thread-safe</span><span class="sxs-lookup"><span data-stu-id="814c7-141">Thread-safe delegate invocation</span></span>

<span data-ttu-id="814c7-142">Usare l'operatore `?.` per controllare se un delegato è diverso da Null e richiamarlo in un modo thread-safe, ad esempio, quando si [genera un evento](../../../standard/events/how-to-raise-and-consume-events.md), come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="814c7-142">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="814c7-143">Il codice equivale alla versione C# 5 o precedente del codice seguente:</span><span class="sxs-lookup"><span data-stu-id="814c7-143">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="814c7-144">Operatore di chiamata ()</span><span class="sxs-lookup"><span data-stu-id="814c7-144">Invocation operator ()</span></span>

<span data-ttu-id="814c7-145">Usare le parentesi, `()`, per chiamare un [metodo](../../programming-guide/classes-and-structs/methods.md) oppure richiamare un [delegato](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="814c7-145">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="814c7-146">L'esempio seguente illustra come chiamare un metodo, con o senza argomenti, e come richiamare un delegato:</span><span class="sxs-lookup"><span data-stu-id="814c7-146">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="814c7-147">Le parentesi si usano anche per richiamare un [costruttore](../../programming-guide/classes-and-structs/constructors.md) con un operatore [`new`](../keywords/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="814c7-147">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="814c7-148">Altri utilizzi di ()</span><span class="sxs-lookup"><span data-stu-id="814c7-148">Other usages of ()</span></span>

<span data-ttu-id="814c7-149">È anche possibile usare le parentesi per specificare l'ordine in cui valutare le operazioni in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="814c7-149">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="814c7-150">Per altre informazioni, vedere la sezione [Aggiunta di parentesi](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) dell'articolo [Operatori](../../programming-guide/statements-expressions-operators/operators.md).</span><span class="sxs-lookup"><span data-stu-id="814c7-150">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="814c7-151">Per l'elenco degli operatori ordinati in base al livello di precedenza, vedere [ Operatori C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="814c7-151">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

<span data-ttu-id="814c7-152">Anche le [espressioni cast](invocation-operator.md#cast-expression), che richiamano un operatore di conversione, utilizzano le parentesi.</span><span class="sxs-lookup"><span data-stu-id="814c7-152">[Cast expressions](invocation-operator.md#cast-expression), which invoke a conversion operator, also use parentheses.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="814c7-153">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="814c7-153">Operator overloadability</span></span>

<span data-ttu-id="814c7-154">Gli operatori `.` e `()` non possono essere sottoposti a overload.</span><span class="sxs-lookup"><span data-stu-id="814c7-154">The `.` and `()` operators cannot be overloaded.</span></span> <span data-ttu-id="814c7-155">Anche l'operatore `[]` viene considerato un operatore che non supporta l'overload.</span><span class="sxs-lookup"><span data-stu-id="814c7-155">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="814c7-156">Per il supporto dell'indicizzazione con tipi definiti dall'utente, usare gli [indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="814c7-156">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="814c7-157">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="814c7-157">C# language specification</span></span>

<span data-ttu-id="814c7-158">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="814c7-158">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="814c7-159">Accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="814c7-159">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="814c7-160">Accesso a elementi</span><span class="sxs-lookup"><span data-stu-id="814c7-160">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="814c7-161">Operatori condizionali Null</span><span class="sxs-lookup"><span data-stu-id="814c7-161">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="814c7-162">Espressioni di chiamata</span><span class="sxs-lookup"><span data-stu-id="814c7-162">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a><span data-ttu-id="814c7-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="814c7-163">See also</span></span>

- [<span data-ttu-id="814c7-164">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="814c7-164">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="814c7-165">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="814c7-165">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="814c7-166">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="814c7-166">C# Operators</span></span>](index.md)
- [<span data-ttu-id="814c7-167"> ?? (operatore null-coalescing)</span><span class="sxs-lookup"><span data-stu-id="814c7-167">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
