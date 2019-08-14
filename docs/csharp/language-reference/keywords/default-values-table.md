---
title: Tabella dei valori predefiniti - Informazioni di riferimento per C#
ms.custom: seodec18
description: Informazioni sui valori predefiniti dei tipi C#.
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 23fba8269670156000cb68b3aa07ae7c770eada1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627736"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="3b046-103">Tabella dei valori predefiniti (Informazioni di riferimento per C#)</span><span class="sxs-lookup"><span data-stu-id="3b046-103">Default values table (C# reference)</span></span>

<span data-ttu-id="3b046-104">La tabella seguente mostra i valori predefiniti dei tipi C#:</span><span class="sxs-lookup"><span data-stu-id="3b046-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="3b046-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="3b046-105">Type</span></span>|<span data-ttu-id="3b046-106">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="3b046-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="3b046-107">Qualsiasi tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="3b046-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="3b046-108">Qualsiasi [tipo numerico integrale incorporato](../builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="3b046-108">Any [built-in integral numeric type](../builtin-types/integral-numeric-types.md)</span></span>|<span data-ttu-id="3b046-109">0 (zero)</span><span class="sxs-lookup"><span data-stu-id="3b046-109">0 (zero)</span></span>|
|<span data-ttu-id="3b046-110">Qualsiasi [tipo numerico a virgola mobile incorporato](../builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="3b046-110">Any [built-in floating-point numeric type](../builtin-types/floating-point-numeric-types.md)</span></span>|<span data-ttu-id="3b046-111">0 (zero)</span><span class="sxs-lookup"><span data-stu-id="3b046-111">0 (zero)</span></span>|
|[<span data-ttu-id="3b046-112">bool</span><span class="sxs-lookup"><span data-stu-id="3b046-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="3b046-113">char</span><span class="sxs-lookup"><span data-stu-id="3b046-113">char</span></span>](char.md)|<span data-ttu-id="3b046-114">`'\0'` (U+0000)</span><span class="sxs-lookup"><span data-stu-id="3b046-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="3b046-115">enum</span><span class="sxs-lookup"><span data-stu-id="3b046-115">enum</span></span>](enum.md)|<span data-ttu-id="3b046-116">Valore prodotto dall'espressione `(E)0`, dove `E` è l'identificatore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3b046-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="3b046-117">struct</span><span class="sxs-lookup"><span data-stu-id="3b046-117">struct</span></span>](struct.md)|<span data-ttu-id="3b046-118">Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.</span><span class="sxs-lookup"><span data-stu-id="3b046-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="3b046-119">Qualsiasi [tipo valore nullable](../../programming-guide/nullable-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="3b046-119">Any [nullable value type](../../programming-guide/nullable-types/index.md)</span></span>|<span data-ttu-id="3b046-120">Un'istanza per la quale la proprietà <xref:System.Nullable%601.HasValue%2A> è `false` e la proprietà <xref:System.Nullable%601.Value%2A> non è definita.</span><span class="sxs-lookup"><span data-stu-id="3b046-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="3b046-121">Il valore predefinito è noto anche come valore *null* del tipo valore nullable.</span><span class="sxs-lookup"><span data-stu-id="3b046-121">That default value is also known as the *null* value of the nullable value type.</span></span>|

<span data-ttu-id="3b046-122">Usare l'[espressione valore predefinito](../../programming-guide/statements-expressions-operators/default-value-expressions.md) per produrre il valore predefinito di un tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3b046-122">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="3b046-123">A partire da C# 7.1 è possibile usare il [ valore letterale `default`](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) per inizializzare una variabile con il valore predefinito del relativo tipo:</span><span class="sxs-lookup"><span data-stu-id="3b046-123">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="3b046-124">Per un tipo valore, anche il costruttore senza parametri implicito produce il valore predefinito del tipo, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3b046-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a><span data-ttu-id="3b046-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3b046-125">C# language specification</span></span>

<span data-ttu-id="3b046-126">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="3b046-126">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="3b046-127">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="3b046-127">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="3b046-128">Costruttori predefiniti</span><span class="sxs-lookup"><span data-stu-id="3b046-128">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="3b046-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b046-129">See also</span></span>

- [<span data-ttu-id="3b046-130">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3b046-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3b046-131">Parole chiave C#</span><span class="sxs-lookup"><span data-stu-id="3b046-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="3b046-132">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="3b046-132">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="3b046-133">Costruttori</span><span class="sxs-lookup"><span data-stu-id="3b046-133">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
