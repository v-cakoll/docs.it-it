---
title: ?? E?? Operatori - Riferimenti per C
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
ms.openlocfilehash: 69294f0fb706868b48b8d7fe8b95fa345af169b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847313"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="3f8f4-103">??</span><span class="sxs-lookup"><span data-stu-id="3f8f4-103">??</span></span> <span data-ttu-id="3f8f4-104">E?? Operatori (riferimenti per C</span><span class="sxs-lookup"><span data-stu-id="3f8f4-104">and ??= operators (C# reference)</span></span>

<span data-ttu-id="3f8f4-105">L'operatore null-coalescing `??` restituisce il valore dell'operando a sinistra se è `null`; in caso contrario, valuta l'operando a destra e ne restituisce il risultato.</span><span class="sxs-lookup"><span data-stu-id="3f8f4-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="3f8f4-106">L'operatore `??` non valuta l'operando a destra se l'operando a sinistra restituisce un valore non null.</span><span class="sxs-lookup"><span data-stu-id="3f8f4-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="3f8f4-107">Disponibile in C, 8.0 e versioni successive, l'operatore `??=` di assegnazione null-coalescing assegna il valore del relativo operando di `null`destra al relativo operando di sinistra solo se l'operando di sinistra restituisce .</span><span class="sxs-lookup"><span data-stu-id="3f8f4-107">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="3f8f4-108">L'operatore `??=` non valuta l'operando a destra se l'operando a sinistra restituisce un valore non null.</span><span class="sxs-lookup"><span data-stu-id="3f8f4-108">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](snippets/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="3f8f4-109">L'operando di sinistra `??=` dell'operatore deve essere una variabile, una [proprietà](../../programming-guide/classes-and-structs/properties.md)o un elemento [dell'indicizzatore.](../../programming-guide/indexers/index.md)</span><span class="sxs-lookup"><span data-stu-id="3f8f4-109">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span>

<span data-ttu-id="3f8f4-110">Nelle versioni precedenti e 7.3 del linguaggio C, il `??` tipo dell'operando a sinistra dell'operatore deve essere un tipo di [riferimento](../keywords/reference-types.md) o un tipo di [valore nullable.](../builtin-types/nullable-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="3f8f4-110">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a [reference type](../keywords/reference-types.md) or a [nullable value type](../builtin-types/nullable-value-types.md).</span></span> <span data-ttu-id="3f8f4-111">A partire dalla versione 8.0 di C, tale requisito viene sostituito con `??` `??=` il seguente: il tipo dell'operando di sinistra degli operatori e non può essere un tipo di valore non nullable.</span><span class="sxs-lookup"><span data-stu-id="3f8f4-111">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="3f8f4-112">In particolare, a partire dalla versione 8.0 di C, è possibile usare gli operatori di null-coalescing con parametri di tipo non vincolati:In particular, beginning with C'è 8.0, you can use the null-coalescing operators with unconstrained type parameters:</span><span class="sxs-lookup"><span data-stu-id="3f8f4-112">In particular, beginning with C# 8.0, you can use the null-coalescing operators with unconstrained type parameters:</span></span>

[!code-csharp[unconstrained type parameter](snippets/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="3f8f4-113">Gli operatori null-coalescing sono associativi a destra.</span><span class="sxs-lookup"><span data-stu-id="3f8f4-113">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="3f8f4-114">Ovvero, le espressioni della forma</span><span class="sxs-lookup"><span data-stu-id="3f8f4-114">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="3f8f4-115">vengono valutati come</span><span class="sxs-lookup"><span data-stu-id="3f8f4-115">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="3f8f4-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="3f8f4-116">Examples</span></span>

<span data-ttu-id="3f8f4-117">Gli `??` `??=` operatori e possono essere utili negli scenari seguenti:The and operators can be useful in the following scenarios:</span><span class="sxs-lookup"><span data-stu-id="3f8f4-117">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="3f8f4-118">Nelle espressioni con gli [operatori null-conditional ?. e ?[]](member-access-operators.md#null-conditional-operators--and-), è possibile utilizzare l'operatore `??` per fornire `null`un'espressione alternativa da valutare nel caso in cui il risultato dell'espressione con operazioni null-conditional sia :</span><span class="sxs-lookup"><span data-stu-id="3f8f4-118">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the `??` operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](snippets/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="3f8f4-119">Quando si utilizzano [tipi di valore nullable](../builtin-types/nullable-value-types.md) ed è necessario `??` fornire un valore di un tipo di valore `null`sottostante, utilizzare l'operatore per specificare il valore da fornire nel caso in cui un valore di tipo nullable sia :</span><span class="sxs-lookup"><span data-stu-id="3f8f4-119">When you work with [nullable value types](../builtin-types/nullable-value-types.md) and need to provide a value of an underlying value type, use the `??` operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](snippets/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="3f8f4-120">Usare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> se il valore da usare quando un valore di tipo nullable è `null` deve essere il valore predefinito del tipo valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="3f8f4-120">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="3f8f4-121">A partire dalla versione 7.0 di C, è possibile usare `??` [ `throw` un'espressione](../keywords/throw.md#the-throw-expression) come operando di destra dell'operatore per rendere più conciso il codice di controllo degli argomenti:At beginning with C' 7.0, you can use a expression as the right-hand operand of the operator to make the argument-checking code more concise:</span><span class="sxs-lookup"><span data-stu-id="3f8f4-121">Beginning with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the `??` operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](snippets/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="3f8f4-122">L'esempio precedente dimostra anche come usare [membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) per definire una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3f8f4-122">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="3f8f4-123">A partire dalla versione 8.0 `??=` di C, è possibile utilizzare l'operatore per sostituire il codice del modulo</span><span class="sxs-lookup"><span data-stu-id="3f8f4-123">Beginning with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="3f8f4-124">con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="3f8f4-124">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="3f8f4-125">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="3f8f4-125">Operator overloadability</span></span>

<span data-ttu-id="3f8f4-126">Gli `??` operatori `??=` e non può essere sottoposto a overload.</span><span class="sxs-lookup"><span data-stu-id="3f8f4-126">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3f8f4-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3f8f4-127">C# language specification</span></span>

<span data-ttu-id="3f8f4-128">Per ulteriori informazioni `??` sull'operatore, vedere [sezione relativa all'operatore coalescing null](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) della specifica del [linguaggio C.](~/_csharplang/spec/introduction.md)</span><span class="sxs-lookup"><span data-stu-id="3f8f4-128">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="3f8f4-129">Per ulteriori informazioni `??=` sull'operatore, vedere la [nota](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md)della proposta di funzionalità .</span><span class="sxs-lookup"><span data-stu-id="3f8f4-129">For more information about the `??=` operator, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3f8f4-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f8f4-130">See also</span></span>

- [<span data-ttu-id="3f8f4-131">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="3f8f4-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3f8f4-132">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="3f8f4-132">C# operators</span></span>](index.md)
- <span data-ttu-id="3f8f4-133">[?. E? [] operatori](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="3f8f4-133">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="3f8f4-134">?: operatore</span><span class="sxs-lookup"><span data-stu-id="3f8f4-134">?: operator</span></span>](conditional-operator.md)
