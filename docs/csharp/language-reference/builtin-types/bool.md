---
title: tipo bool- C# riferimento
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 720ece2f7f47961e0ab6ebf03c8afeb5fa3a6271
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093266"
---
# <a name="bool-c-reference"></a><span data-ttu-id="d7b68-102">bool (C# riferimento)</span><span class="sxs-lookup"><span data-stu-id="d7b68-102">bool (C# reference)</span></span>

<span data-ttu-id="d7b68-103">La parola chiave `bool` Type è un alias per il tipo di struttura <xref:System.Boolean?displayProperty=nameWithType> .NET che rappresenta un valore booleano, che può essere `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="d7b68-103">The `bool` type keyword is an alias for the .NET <xref:System.Boolean?displayProperty=nameWithType> structure type that represents a Boolean value, which can be either `true` or `false`.</span></span>

<span data-ttu-id="d7b68-104">Per eseguire operazioni logiche con valori del tipo di `bool`, utilizzare operatori [logici booleani](../operators/boolean-logical-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="d7b68-104">To perform logical operations with values of the `bool` type, use [Boolean logical](../operators/boolean-logical-operators.md) operators.</span></span> <span data-ttu-id="d7b68-105">Il tipo di `bool` è il tipo di risultato degli operatori di [confronto](../operators/comparison-operators.md) e di [uguaglianza](../operators/equality-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="d7b68-105">The `bool` type is the result type of [comparison](../operators/comparison-operators.md) and [equality](../operators/equality-operators.md) operators.</span></span> <span data-ttu-id="d7b68-106">Un'espressione `bool` può essere un'espressione condizionale di controllo nelle istruzioni [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md)e [for](../keywords/for.md) e nell' [operatore condizionale `?:`](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="d7b68-106">A `bool` expression can be a controlling conditional expression in the [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md), and [for](../keywords/for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="d7b68-107">Il valore predefinito del tipo di `bool` è `false`.</span><span class="sxs-lookup"><span data-stu-id="d7b68-107">The default value of the `bool` type is `false`.</span></span>

## <a name="literals"></a><span data-ttu-id="d7b68-108">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="d7b68-108">Literals</span></span>

<span data-ttu-id="d7b68-109">È possibile usare i valori letterali `true` e `false` per inizializzare una variabile di `bool` o per passare un valore di `bool`:</span><span class="sxs-lookup"><span data-stu-id="d7b68-109">You can use the `true` and `false` literals to initialize a `bool` variable or to pass a `bool` value:</span></span>

[!code-csharp-interactive[bool literals](~/samples/csharp/language-reference/builtin-types/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a><span data-ttu-id="d7b68-110">Logica booleana a tre valori</span><span class="sxs-lookup"><span data-stu-id="d7b68-110">Three-valued Boolean logic</span></span>

<span data-ttu-id="d7b68-111">Usare il tipo Nullable `bool?`, se è necessario supportare la logica a tre valori, ad esempio quando si lavora con database che supportano un tipo booleano a tre valori.</span><span class="sxs-lookup"><span data-stu-id="d7b68-111">Use the nullable `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="d7b68-112">Per gli operandi `bool?`, gli operatori `&` e `|` predefiniti supportano la logica a tre valori.</span><span class="sxs-lookup"><span data-stu-id="d7b68-112">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="d7b68-113">Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="d7b68-113">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="d7b68-114">Per ulteriori informazioni sui tipi di valore Nullable, vedere [tipi di valore Nullable](nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="d7b68-114">For more information about nullable value types, see [Nullable value types](nullable-value-types.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="d7b68-115">Conversioni</span><span class="sxs-lookup"><span data-stu-id="d7b68-115">Conversions</span></span>

<span data-ttu-id="d7b68-116">C#fornisce solo due conversioni che coinvolgono il tipo di `bool`.</span><span class="sxs-lookup"><span data-stu-id="d7b68-116">C# provides only two conversions that involve the `bool` type.</span></span> <span data-ttu-id="d7b68-117">Si tratta di una conversione implicita al tipo di `bool?` nullable corrispondente e a una conversione esplicita dal tipo di `bool?`.</span><span class="sxs-lookup"><span data-stu-id="d7b68-117">Those are an implicit conversion to the corresponding nullable `bool?` type and an explicit conversion from the `bool?` type.</span></span> <span data-ttu-id="d7b68-118">.NET fornisce tuttavia metodi aggiuntivi che è possibile usare per eseguire la conversione da o verso il tipo di `bool`.</span><span class="sxs-lookup"><span data-stu-id="d7b68-118">However, .NET provides additional methods that you can use to convert to or from the `bool` type.</span></span> <span data-ttu-id="d7b68-119">Per ulteriori informazioni, vedere la sezione [conversione da e verso valori booleani](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) della pagina di riferimento dell'API <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d7b68-119">For more information, see the [Converting to and from Boolean values](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) section of the <xref:System.Boolean?displayProperty=nameWithType> API reference page.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d7b68-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d7b68-120">C# language specification</span></span>

<span data-ttu-id="d7b68-121">Per ulteriori informazioni, vedere [la sezione tipo bool](~/_csharplang/spec/types.md#the-bool-type) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d7b68-121">For more information, see [The bool type](~/_csharplang/spec/types.md#the-bool-type) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7b68-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7b68-122">See also</span></span>

- [<span data-ttu-id="d7b68-123">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d7b68-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d7b68-124">Tipi di valore</span><span class="sxs-lookup"><span data-stu-id="d7b68-124">Value types</span></span>](value-types.md)
- [<span data-ttu-id="d7b68-125">Operatori true e false</span><span class="sxs-lookup"><span data-stu-id="d7b68-125">true and false operators</span></span>](../operators/true-false-operators.md)
