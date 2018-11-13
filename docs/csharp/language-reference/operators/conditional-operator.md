---
title: 'Operatore ?: (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 3e45ff6eaaefa5829c3ed9415abe1a12b7a1d069
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980622"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="86a39-102">Operatore ?: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="86a39-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="86a39-103">L'operatore condizionale (`?:`), noto come operatore condizionale ternario, restituisce uno di due valori in base al valore di un'espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="86a39-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="86a39-104">Di seguito è riportata la sintassi per l'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="86a39-104">Following is the syntax for the conditional operator.</span></span>  

```csharp
condition ? first_expression : second_expression;  
```

<span data-ttu-id="86a39-105">A partire da C# 7.2, `first_expression` e `second_expression` possono essere [espressioni `ref`](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):</span><span class="sxs-lookup"><span data-stu-id="86a39-105">Beginning with C# 7.2, the `first_expression` and `second_expression` my be [`ref` expressions](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):</span></span>

```csharp
ref condition ? ref first_expression : ref second_expression;  
```

<span data-ttu-id="86a39-106">Il risultato può essere assegnato a una variabile `ref` o `ref readonly` o a una variabile senza modificatori.</span><span class="sxs-lookup"><span data-stu-id="86a39-106">The result may be assigned to a `ref` or `ref readonly` variable, or to a variable with neither modifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="86a39-107">Note</span><span class="sxs-lookup"><span data-stu-id="86a39-107">Remarks</span></span>

<span data-ttu-id="86a39-108">L' oggetto `condition` deve restituire `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="86a39-108">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="86a39-109">Se `condition` è `true`, `first_expression` viene valutato e diventa il risultato.</span><span class="sxs-lookup"><span data-stu-id="86a39-109">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="86a39-110">Se `condition` è `false`, `second_expression` viene valutato e diventa il risultato.</span><span class="sxs-lookup"><span data-stu-id="86a39-110">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="86a39-111">Viene valutata soltanto una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="86a39-111">Only one of the two expressions is evaluated.</span></span> <span data-ttu-id="86a39-112">Ciò è particolarmente importante per le espressioni in cui il risultato è `ref`, come la seguente espressione valida:</span><span class="sxs-lookup"><span data-stu-id="86a39-112">This is particularly important for expressions where the result is a `ref`, as the following is valid:</span></span>

```csharp
ref (storage != null) ? ref storage[3] : ref defaultValue;
```

<span data-ttu-id="86a39-113">Il riferimento a `storage` non viene valutato quando `storage` è Null.</span><span class="sxs-lookup"><span data-stu-id="86a39-113">The reference to `storage` is not evaluated when `storage` is null.</span></span>

<span data-ttu-id="86a39-114">Quando il risultato è un valore, il tipo di `first_expression` e `second_expression` deve corrispondere oppure deve essere presente una conversione implicita da un tipo all'altro.</span><span class="sxs-lookup"><span data-stu-id="86a39-114">When the result is a value, the type of `first_expression` and `second_expression` must be the same, or there must be an implicit conversion from one type to the other.</span></span> <span data-ttu-id="86a39-115">Quando il risultato è `ref`, il tipo di `first_expression` e `second_expression` deve corrispondere.</span><span class="sxs-lookup"><span data-stu-id="86a39-115">When the result is a `ref`, the type of `first_expression` and `second_expression` must be the same.</span></span>

<span data-ttu-id="86a39-116">I calcoli che richiedono una costruzione `if-else` possono essere espressi più concisamente mediante l'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="86a39-116">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="86a39-117">Ad esempio, il codice seguente viene utilizzato prima un'istruzione `if`, quindi un operatore condizionale per classificare un integer come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="86a39-117">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>

```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```

<span data-ttu-id="86a39-118">L'operatore condizionale si associa all'operando a destra.</span><span class="sxs-lookup"><span data-stu-id="86a39-118">The conditional operator is right-associative.</span></span> <span data-ttu-id="86a39-119">L'espressione `a ? b : c ? d : e` viene valutata come `a ? b : (c ? d : e)`, non come `(a ? b : c) ? d : e`.</span><span class="sxs-lookup"><span data-stu-id="86a39-119">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
<span data-ttu-id="86a39-120">Non è possibile eseguire l'overload dell'operatore condizionale.</span><span class="sxs-lookup"><span data-stu-id="86a39-120">The conditional operator cannot be overloaded.</span></span>
  
## <a name="example"></a><span data-ttu-id="86a39-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="86a39-121">Example</span></span>

<span data-ttu-id="86a39-122">L'esempio seguente illustra l'operatore condizionale il cui risultato è un valore:</span><span class="sxs-lookup"><span data-stu-id="86a39-122">The following example shows the conditional operator whose result is a value:</span></span>

[!code-csharp[csRefOperators?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

<span data-ttu-id="86a39-123">L'alternativa seguente illustra l'operatore condizionale il cui risultato è un riferimento:</span><span class="sxs-lookup"><span data-stu-id="86a39-123">The following alternative shows the conditional operator where the result is a reference:</span></span>

[!code-csharp[csRefOperatorsRef?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

## <a name="see-also"></a><span data-ttu-id="86a39-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86a39-124">See Also</span></span>

- [<span data-ttu-id="86a39-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="86a39-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="86a39-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="86a39-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="86a39-127">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="86a39-127">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="86a39-128">if-else</span><span class="sxs-lookup"><span data-stu-id="86a39-128">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
- <span data-ttu-id="86a39-129">[Operatori ?. e ?[]](../../../csharp/language-reference/operators/null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="86a39-129">[?. and ?[] Operators](../../../csharp/language-reference/operators/null-conditional-operators.md)</span></span>  
- [<span data-ttu-id="86a39-130">?? (operatore)</span><span class="sxs-lookup"><span data-stu-id="86a39-130">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)
