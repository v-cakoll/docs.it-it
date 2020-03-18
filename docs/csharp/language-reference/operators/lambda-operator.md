---
title: Operatore => Riferimenti per C#
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 15c02e11610866f359e3e3a7e2751ded918154b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846253"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d303b-102">Operatore => (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d303b-102">=> operator (C# reference)</span></span>

<span data-ttu-id="d303b-103">Il `=>` token è supportato in due formati: come [operatore lambda](#lambda-operator) e come separatore del nome di un membro e dell'implementazione del membro in una definizione del [corpo dell'espressione.](#expression-body-definition)</span><span class="sxs-lookup"><span data-stu-id="d303b-103">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="d303b-104">Operatore lambda</span><span class="sxs-lookup"><span data-stu-id="d303b-104">Lambda operator</span></span>

<span data-ttu-id="d303b-105">Nelle [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md), `=>` l'operatore lambda separa i parametri di input sul lato sinistro dal corpo dell'espressione lambda sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="d303b-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="d303b-106">L'esempio seguente illustra l'utilizzo delle espressioni lambda tramite la funzionalità [LINQ](../../programming-guide/concepts/linq/index.md) con la sintassi dei metodi:</span><span class="sxs-lookup"><span data-stu-id="d303b-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](snippets/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="d303b-107">I parametri di input di un'espressione lambda sono fortemente tipizzati in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d303b-107">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="d303b-108">Quando il compilatore può dedurre i tipi di parametri di input, come nell'esempio precedente, è possibile omettere le dichiarazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="d303b-108">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="d303b-109">Se è necessario specificare il tipo di parametri di input, è necessario farlo per ogni parametro, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d303b-109">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](snippets/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="d303b-110">L'esempio seguente mostra come definire un'espressione lambda senza parametri di input:The following example shows how to define a lambda expression without input parameters:</span><span class="sxs-lookup"><span data-stu-id="d303b-110">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](snippets/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="d303b-111">Per altre informazioni, vedere [Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d303b-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="d303b-112">Definizione del corpo dell'espressione</span><span class="sxs-lookup"><span data-stu-id="d303b-112">Expression body definition</span></span>

<span data-ttu-id="d303b-113">Una definizione di corpo di espressione presenta la seguente sintassi generale:</span><span class="sxs-lookup"><span data-stu-id="d303b-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="d303b-114">dove `expression` è un'espressione valida.</span><span class="sxs-lookup"><span data-stu-id="d303b-114">where `expression` is a valid expression.</span></span> <span data-ttu-id="d303b-115">Il tipo restituito di `expression` deve essere convertibile in modo implicito nel tipo restituito del membro.</span><span class="sxs-lookup"><span data-stu-id="d303b-115">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="d303b-116">Se il tipo restituito `void` del membro è o se il membro è `set` un `expression` costruttore, un finalizzatore o una funzione di accesso alla proprietà, deve essere [*un'espressione*](~/_csharplang/spec/statements.md#expression-statements)di istruzione , che può essere di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="d303b-116">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements), which can be of any type.</span></span>

<span data-ttu-id="d303b-117">L'esempio seguente illustra una definizione del corpo dell'espressione per un metodo `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="d303b-117">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="d303b-118">Si tratta di una versione abbreviata della definizione di metodo seguente:</span><span class="sxs-lookup"><span data-stu-id="d303b-118">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="d303b-119">Le definizioni del corpo dell'espressione per metodi, operatori e proprietà di sola lettura sono supportate a partire da C .</span><span class="sxs-lookup"><span data-stu-id="d303b-119">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="d303b-120">Le definizioni del corpo dell'espressione per i costruttori, i finalizzatori e le funzioni di accesso di proprietà e indicizzatore sono supportate a partire da C .</span><span class="sxs-lookup"><span data-stu-id="d303b-120">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="d303b-121">Per altre informazioni, vedere [Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="d303b-121">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d303b-122">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="d303b-122">Operator overloadability</span></span>

<span data-ttu-id="d303b-123">Non è possibile eseguire l'overload dell'operatore `=>`.</span><span class="sxs-lookup"><span data-stu-id="d303b-123">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d303b-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d303b-124">C# language specification</span></span>

<span data-ttu-id="d303b-125">Per ulteriori informazioni sull'operatore lambda, vedere la sezione [Espressioni di funzione anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della specifica del [linguaggio C.](~/_csharplang/spec/introduction.md)</span><span class="sxs-lookup"><span data-stu-id="d303b-125">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d303b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d303b-126">See also</span></span>

- [<span data-ttu-id="d303b-127">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="d303b-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d303b-128">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="d303b-128">C# operators</span></span>](index.md)
