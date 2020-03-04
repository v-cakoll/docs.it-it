---
title: ?? e? = Operators C# -riferimento
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: ce16f732fae0eec38b2a55af055e51c5fe70773a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239157"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="84b0d-103">??</span><span class="sxs-lookup"><span data-stu-id="84b0d-103">??</span></span> <span data-ttu-id="84b0d-104">e? = OperatorsC# (riferimento)</span><span class="sxs-lookup"><span data-stu-id="84b0d-104">and ??= operators (C# reference)</span></span>

<span data-ttu-id="84b0d-105">L'operatore null-coalescing `??` restituisce il valore dell'operando a sinistra se non è `null`; in caso contrario, valuta l'operando a destra e ne restituisce il risultato.</span><span class="sxs-lookup"><span data-stu-id="84b0d-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="84b0d-106">L'operatore `??` non valuta l'operando a destra se l'operando a sinistra restituisce un valore non null.</span><span class="sxs-lookup"><span data-stu-id="84b0d-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="84b0d-107">Disponibile in C# 8,0 e versioni successive, l'operatore di assegnazione con unione null `??=` assegna il valore dell'operando destro all'operando sinistro solo se l'operando sinistro restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="84b0d-107">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="84b0d-108">L'operatore `??=` non valuta l'operando a destra se l'operando a sinistra restituisce un valore non null.</span><span class="sxs-lookup"><span data-stu-id="84b0d-108">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](~/samples/snippets/csharp/language-reference/operators/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="84b0d-109">L'operando sinistro dell'operatore di `??=` deve essere una variabile, una [Proprietà](../../programming-guide/classes-and-structs/properties.md)o un elemento dell' [indicizzatore](../../programming-guide/indexers/index.md) .</span><span class="sxs-lookup"><span data-stu-id="84b0d-109">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span>

<span data-ttu-id="84b0d-110">In C# 7,3 e versioni precedenti, il tipo dell'operando sinistro dell'operatore di `??` deve essere un tipo di [riferimento](../keywords/reference-types.md) o un [tipo di valore Nullable](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="84b0d-110">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a [reference type](../keywords/reference-types.md) or a [nullable value type](../builtin-types/nullable-value-types.md).</span></span> <span data-ttu-id="84b0d-111">A partire C# da 8,0, il requisito viene sostituito con quanto segue: il tipo dell'operando sinistro degli operatori `??` e `??=` non può essere un tipo di valore non nullable.</span><span class="sxs-lookup"><span data-stu-id="84b0d-111">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="84b0d-112">In particolare, a partire C# da 8,0, è possibile usare gli operatori di Unione null con parametri di tipo non vincolati:</span><span class="sxs-lookup"><span data-stu-id="84b0d-112">In particular, beginning with C# 8.0, you can use the null-coalescing operators with unconstrained type parameters:</span></span>

[!code-csharp[unconstrained type parameter](~/samples/snippets/csharp/language-reference/operators/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="84b0d-113">Gli operatori che uniscono i valori null sono associativi a destra.</span><span class="sxs-lookup"><span data-stu-id="84b0d-113">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="84b0d-114">Ovvero espressioni nel formato</span><span class="sxs-lookup"><span data-stu-id="84b0d-114">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="84b0d-115">vengono valutati come</span><span class="sxs-lookup"><span data-stu-id="84b0d-115">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="84b0d-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="84b0d-116">Examples</span></span>

<span data-ttu-id="84b0d-117">Gli operatori `??` e `??=` possono essere utili negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="84b0d-117">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="84b0d-118">Nelle espressioni con gli [operatori condizionali null?. e? []](member-access-operators.md#null-conditional-operators--and-), è possibile usare l'operatore `??` per fornire un'espressione alternativa da valutare se il risultato dell'espressione con operazioni condizionali null è `null`:</span><span class="sxs-lookup"><span data-stu-id="84b0d-118">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the `??` operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/snippets/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="84b0d-119">Quando si utilizzano [tipi di valore Nullable](../builtin-types/nullable-value-types.md) ed è necessario fornire un valore di un tipo di valore sottostante, utilizzare l'operatore `??` per specificare il valore da fornire nel caso in cui venga `null`un valore di tipo Nullable:</span><span class="sxs-lookup"><span data-stu-id="84b0d-119">When you work with [nullable value types](../builtin-types/nullable-value-types.md) and need to provide a value of an underlying value type, use the `??` operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/snippets/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="84b0d-120">Usare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> se il valore da usare quando un valore di tipo nullable è `null` deve essere il valore predefinito del tipo valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="84b0d-120">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="84b0d-121">A partire C# da 7,0, è possibile usare un' [espressione`throw`](../keywords/throw.md#the-throw-expression) come operando destro dell'operatore `??` per rendere più conciso il codice per il controllo degli argomenti:</span><span class="sxs-lookup"><span data-stu-id="84b0d-121">Beginning with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the `??` operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/snippets/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="84b0d-122">L'esempio precedente dimostra anche come usare [membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) per definire una proprietà.</span><span class="sxs-lookup"><span data-stu-id="84b0d-122">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="84b0d-123">A partire C# da 8,0, è possibile usare l'operatore `??=` per sostituire il codice del modulo</span><span class="sxs-lookup"><span data-stu-id="84b0d-123">Beginning with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="84b0d-124">con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="84b0d-124">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="84b0d-125">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="84b0d-125">Operator overloadability</span></span>

<span data-ttu-id="84b0d-126">Non è possibile eseguire l'overload degli operatori `??` e `??=`.</span><span class="sxs-lookup"><span data-stu-id="84b0d-126">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="84b0d-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="84b0d-127">C# language specification</span></span>

<span data-ttu-id="84b0d-128">Per ulteriori informazioni sull'operatore `??`, vedere la sezione relativa all'operatore di Unione [null](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) nella [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="84b0d-128">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="84b0d-129">Per ulteriori informazioni sull'operatore `??=`, vedere la [Nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span><span class="sxs-lookup"><span data-stu-id="84b0d-129">For more information about the `??=` operator, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84b0d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84b0d-130">See also</span></span>

- [<span data-ttu-id="84b0d-131">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="84b0d-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="84b0d-132">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="84b0d-132">C# operators</span></span>](index.md)
- <span data-ttu-id="84b0d-133">[Operatori ?. e ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="84b0d-133">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="84b0d-134">Operatore ?:</span><span class="sxs-lookup"><span data-stu-id="84b0d-134">?: operator</span></span>](conditional-operator.md)
