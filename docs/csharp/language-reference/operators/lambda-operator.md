---
title: Operatore => Riferimenti per C#
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 5df1ae60ddc298f75d70db7769ec1bf1d21b8ef2
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239287"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="dd15c-102">Operatore => (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="dd15c-102">=> operator (C# reference)</span></span>

<span data-ttu-id="dd15c-103">Il token `=>` è supportato in due formati: come [operatore lambda](#lambda-operator) e come separatore di un nome di membro e dell'implementazione del membro in una [definizione del corpo dell'espressione](#expression-body-definition).</span><span class="sxs-lookup"><span data-stu-id="dd15c-103">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="dd15c-104">Operatore lambda</span><span class="sxs-lookup"><span data-stu-id="dd15c-104">Lambda operator</span></span>

<span data-ttu-id="dd15c-105">Nelle [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md)l'operatore lambda `=>` separa i parametri di input sul lato sinistro dal corpo dell'espressione lambda sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="dd15c-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="dd15c-106">L'esempio seguente illustra l'utilizzo delle espressioni lambda tramite la funzionalità [LINQ](../../programming-guide/concepts/linq/index.md) con la sintassi dei metodi:</span><span class="sxs-lookup"><span data-stu-id="dd15c-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="dd15c-107">I parametri di input di un'espressione lambda sono fortemente tipizzati in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="dd15c-107">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="dd15c-108">Quando il compilatore può dedurre i tipi di parametri di input, come nell'esempio precedente, è possibile omettere le dichiarazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="dd15c-108">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="dd15c-109">Se è necessario specificare il tipo di parametri di input, è necessario eseguire questa operazione per ogni parametro, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dd15c-109">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="dd15c-110">Nell'esempio seguente viene illustrato come definire un'espressione lambda senza parametri di input:</span><span class="sxs-lookup"><span data-stu-id="dd15c-110">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="dd15c-111">Per altre informazioni, vedere [Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="dd15c-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="dd15c-112">Definizione del corpo dell'espressione</span><span class="sxs-lookup"><span data-stu-id="dd15c-112">Expression body definition</span></span>

<span data-ttu-id="dd15c-113">Una definizione di corpo di espressione presenta la seguente sintassi generale:</span><span class="sxs-lookup"><span data-stu-id="dd15c-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="dd15c-114">dove `expression` è un'espressione valida.</span><span class="sxs-lookup"><span data-stu-id="dd15c-114">where `expression` is a valid expression.</span></span> <span data-ttu-id="dd15c-115">Il tipo restituito di `expression` deve essere convertibile in modo implicito nel tipo restituito del membro.</span><span class="sxs-lookup"><span data-stu-id="dd15c-115">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="dd15c-116">Se il tipo restituito del membro è `void` o se il membro è un costruttore, un finalizzatore o una proprietà `set` funzione di accesso, `expression` deve essere un' [*espressione di istruzione*](~/_csharplang/spec/statements.md#expression-statements), che può essere di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="dd15c-116">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements), which can be of any type.</span></span>

<span data-ttu-id="dd15c-117">L'esempio seguente illustra una definizione del corpo dell'espressione per un metodo `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="dd15c-117">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="dd15c-118">Si tratta di una versione abbreviata della definizione di metodo seguente:</span><span class="sxs-lookup"><span data-stu-id="dd15c-118">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="dd15c-119">Le definizioni del corpo dell'espressione per metodi, operatori e proprietà di sola lettura sono supportate C# a partire da 6.</span><span class="sxs-lookup"><span data-stu-id="dd15c-119">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="dd15c-120">Le definizioni del corpo dell'espressione per costruttori, finalizzatori e funzioni di accesso a proprietà e indicizzatori sono C# supportate a partire da 7,0.</span><span class="sxs-lookup"><span data-stu-id="dd15c-120">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="dd15c-121">Per altre informazioni, vedere [Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="dd15c-121">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="dd15c-122">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="dd15c-122">Operator overloadability</span></span>

<span data-ttu-id="dd15c-123">Non è possibile sottoporre l'operatore `=>` a overload.</span><span class="sxs-lookup"><span data-stu-id="dd15c-123">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="dd15c-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="dd15c-124">C# language specification</span></span>

<span data-ttu-id="dd15c-125">Per ulteriori informazioni sull'operatore lambda, vedere la sezione [espressioni di funzione anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="dd15c-125">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd15c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd15c-126">See also</span></span>

- [<span data-ttu-id="dd15c-127">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="dd15c-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="dd15c-128">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="dd15c-128">C# operators</span></span>](index.md)
