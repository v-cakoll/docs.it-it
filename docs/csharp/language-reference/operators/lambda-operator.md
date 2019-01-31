---
title: Operatore =&gt; - Riferimenti per C#
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: fa2e149f5b19e80e3171d08519be3ae249d2a112
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540806"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="5c35a-102">Operatore =&gt; (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5c35a-102">=&gt; operator (C# Reference)</span></span>

<span data-ttu-id="5c35a-103">Il token `=>` è supportato in due forme: come operatore lambda e come separatore tra il nome di un membro e l'implementazione del membro nella definizione del corpo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="5c35a-103">The `=>` token is supported in two forms: as the lambda operator and as a separator of a member name and the member implementation in an expression body definition.</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="5c35a-104">Operatore lambda</span><span class="sxs-lookup"><span data-stu-id="5c35a-104">Lambda operator</span></span>

<span data-ttu-id="5c35a-105">Nelle [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md), l'operatore lambda `=>` separa le variabili di input sul lato sinistro dal corpo dell'espressione lambda sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="5c35a-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input variables on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="5c35a-106">L'esempio seguente illustra l'utilizzo delle espressioni lambda tramite la funzionalità [LINQ](../../programming-guide/concepts/linq/index.md) con la sintassi dei metodi:</span><span class="sxs-lookup"><span data-stu-id="5c35a-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#InferredTypes)]

<span data-ttu-id="5c35a-107">Le variabili di input delle espressioni lambda vengono fortemente tipizzate in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5c35a-107">Input variables of lambda expressions are strongly typed at compile time.</span></span> <span data-ttu-id="5c35a-108">Se il compilatore è in grado di dedurre i tipi delle variabili di input, come nell'esempio precedente, è possibile omettere le dichiarazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="5c35a-108">When the compiler can infer the types of input variables, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="5c35a-109">Se il tipo delle variabili di input deve essere specificato, è necessario farlo per ogni variabile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5c35a-109">If you need to specify the type of input variables, you must do that for each variable, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#ExplicitTypes)]

<span data-ttu-id="5c35a-110">L'esempio seguente illustra come definire un'espressione lambda senza variabili di input:</span><span class="sxs-lookup"><span data-stu-id="5c35a-110">The following example shows how to define a lambda expression without input variables:</span></span>

[!code-csharp-interactive[without input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#WithoutInput)]

<span data-ttu-id="5c35a-111">Per altre informazioni, vedere [Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5c35a-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="5c35a-112">Definizione del corpo dell'espressione</span><span class="sxs-lookup"><span data-stu-id="5c35a-112">Expression body definition</span></span>

<span data-ttu-id="5c35a-113">Una definizione di corpo di espressione presenta la seguente sintassi generale:</span><span class="sxs-lookup"><span data-stu-id="5c35a-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="5c35a-114">dove *expression* è un'espressione valida.</span><span class="sxs-lookup"><span data-stu-id="5c35a-114">where *expression* is a valid expression.</span></span> <span data-ttu-id="5c35a-115">Si noti che *expression* può essere un'*espressione di istruzione* solo se il tipo restituito del membro è `void` o se il membro è un costruttore, un finalizzatore o una funzione di accesso `set` di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c35a-115">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor, a finalizer, or a property `set` accessor.</span></span>

<span data-ttu-id="5c35a-116">L'esempio seguente illustra una definizione del corpo dell'espressione per un metodo `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="5c35a-116">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="5c35a-117">Si tratta di una versione abbreviata della definizione di metodo seguente:</span><span class="sxs-lookup"><span data-stu-id="5c35a-117">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="5c35a-118">Le definizioni del corpo dell'espressione per i metodi e le proprietà di sola lettura sono supportate a partire da C# 6.</span><span class="sxs-lookup"><span data-stu-id="5c35a-118">Expression body definitions for methods and read-only properties are supported starting with C# 6.</span></span> <span data-ttu-id="5c35a-119">Le definizioni del corpo dell'espressione per costruttori, finalizzatori, funzioni di accesso di proprietà e indicizzatori sono supportate a partire da C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="5c35a-119">Expression body definitions for constructors, finalizers, property accessors, and indexers are supported starting with C# 7.0.</span></span>

<span data-ttu-id="5c35a-120">Per altre informazioni, vedere [Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="5c35a-120">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5c35a-121">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="5c35a-121">Operator overloadability</span></span>

<span data-ttu-id="5c35a-122">Non è possibile sottoporre l'operatore `=>` a overload.</span><span class="sxs-lookup"><span data-stu-id="5c35a-122">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5c35a-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="5c35a-123">C# language specification</span></span>

<span data-ttu-id="5c35a-124">Per altre informazioni, vedere la sezione [Espressioni di funzioni anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c35a-124">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5c35a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c35a-125">See also</span></span>

- [<span data-ttu-id="5c35a-126">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="5c35a-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5c35a-127">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5c35a-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5c35a-128">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="5c35a-128">C# Operators</span></span>](index.md)
- [<span data-ttu-id="5c35a-129">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="5c35a-129">Lambda expressions</span></span>](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="5c35a-130">Membri con corpo di espressione</span><span class="sxs-lookup"><span data-stu-id="5c35a-130">Expression-bodied members</span></span>](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)