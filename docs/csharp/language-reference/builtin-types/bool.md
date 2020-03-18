---
title: tipo bool - Informazioni di riferimento su C
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 2ba2e54a6b0f24402fc3728dfe19b548a2368830
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846445"
---
# <a name="bool-c-reference"></a><span data-ttu-id="53121-102">bool (riferimenti per C</span><span class="sxs-lookup"><span data-stu-id="53121-102">bool (C# reference)</span></span>

<span data-ttu-id="53121-103">La `bool` parola chiave type è <xref:System.Boolean?displayProperty=nameWithType> un alias per il tipo di `true` struttura `false`.NET che rappresenta un valore booleano, che può essere o .</span><span class="sxs-lookup"><span data-stu-id="53121-103">The `bool` type keyword is an alias for the .NET <xref:System.Boolean?displayProperty=nameWithType> structure type that represents a Boolean value, which can be either `true` or `false`.</span></span>

<span data-ttu-id="53121-104">Per eseguire operazioni logiche `bool` con valori del tipo, utilizzare operatori [logici booleani.](../operators/boolean-logical-operators.md)</span><span class="sxs-lookup"><span data-stu-id="53121-104">To perform logical operations with values of the `bool` type, use [Boolean logical](../operators/boolean-logical-operators.md) operators.</span></span> <span data-ttu-id="53121-105">Il `bool` tipo è il tipo di risultato degli operatori di [confronto](../operators/comparison-operators.md) e [uguaglianza.](../operators/equality-operators.md)</span><span class="sxs-lookup"><span data-stu-id="53121-105">The `bool` type is the result type of [comparison](../operators/comparison-operators.md) and [equality](../operators/equality-operators.md) operators.</span></span> <span data-ttu-id="53121-106">Un'espressione `bool` può essere un'espressione condizionale di controllo nelle istruzioni [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md)e [for](../keywords/for.md) e [nell'operatore `?:`condizionale ](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="53121-106">A `bool` expression can be a controlling conditional expression in the [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md), and [for](../keywords/for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="53121-107">Il valore predefinito `bool` del `false`tipo è .</span><span class="sxs-lookup"><span data-stu-id="53121-107">The default value of the `bool` type is `false`.</span></span>

## <a name="literals"></a><span data-ttu-id="53121-108">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="53121-108">Literals</span></span>

<span data-ttu-id="53121-109">È possibile `true` utilizzare `false` i valori `bool` letterali e `bool` per inizializzare una variabile o per passare un valore:You can use the and literals to initialize a variable or to pass a value:</span><span class="sxs-lookup"><span data-stu-id="53121-109">You can use the `true` and `false` literals to initialize a `bool` variable or to pass a `bool` value:</span></span>

[!code-csharp-interactive[bool literals](snippets/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a><span data-ttu-id="53121-110">Logica booleana a tre valori</span><span class="sxs-lookup"><span data-stu-id="53121-110">Three-valued Boolean logic</span></span>

<span data-ttu-id="53121-111">Utilizzare il `bool?` tipo nullable, se è necessario supportare la logica a tre valori, ad esempio, quando si utilizzano database che supportano un tipo booleano a tre valori.</span><span class="sxs-lookup"><span data-stu-id="53121-111">Use the nullable `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="53121-112">Per gli operandi `bool?`, gli operatori `&` e `|` predefiniti supportano la logica a tre valori.</span><span class="sxs-lookup"><span data-stu-id="53121-112">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="53121-113">Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="53121-113">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="53121-114">Per ulteriori informazioni sui tipi di valore nullable, vedere [Tipi di valore nullable](nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="53121-114">For more information about nullable value types, see [Nullable value types](nullable-value-types.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="53121-115">Conversioni</span><span class="sxs-lookup"><span data-stu-id="53121-115">Conversions</span></span>

<span data-ttu-id="53121-116">In C' sono disponibili solo `bool` due conversioni che coinvolgono il tipo.</span><span class="sxs-lookup"><span data-stu-id="53121-116">C# provides only two conversions that involve the `bool` type.</span></span> <span data-ttu-id="53121-117">Si tratta di una conversione `bool?` implicita nel tipo `bool?` nullable corrispondente e di una conversione esplicita dal tipo.</span><span class="sxs-lookup"><span data-stu-id="53121-117">Those are an implicit conversion to the corresponding nullable `bool?` type and an explicit conversion from the `bool?` type.</span></span> <span data-ttu-id="53121-118">Tuttavia, .NET fornisce metodi aggiuntivi che è `bool` possibile utilizzare per eseguire la conversione da o verso il tipo.</span><span class="sxs-lookup"><span data-stu-id="53121-118">However, .NET provides additional methods that you can use to convert to or from the `bool` type.</span></span> <span data-ttu-id="53121-119">Per altre informazioni, vedere la sezione [Conversione da e verso valori booleani](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) della pagina di riferimento dell'API. <xref:System.Boolean?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="53121-119">For more information, see the [Converting to and from Boolean values](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) section of the <xref:System.Boolean?displayProperty=nameWithType> API reference page.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="53121-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="53121-120">C# language specification</span></span>

<span data-ttu-id="53121-121">Per ulteriori informazioni, vedere la sezione [relativa al tipo bool](~/_csharplang/spec/types.md#the-bool-type) della specifica del [linguaggio C.](~/_csharplang/spec/introduction.md)</span><span class="sxs-lookup"><span data-stu-id="53121-121">For more information, see [The bool type](~/_csharplang/spec/types.md#the-bool-type) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="53121-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53121-122">See also</span></span>

- [<span data-ttu-id="53121-123">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="53121-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="53121-124">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="53121-124">Value types</span></span>](value-types.md)
- [<span data-ttu-id="53121-125">Operatori true e false</span><span class="sxs-lookup"><span data-stu-id="53121-125">true and false operators</span></span>](../operators/true-false-operators.md)
