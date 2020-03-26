---
title: Valori predefiniti dei tipi C
description: Informazioni sui valori predefiniti dei tipi c'è, ad esempio bool, char, int, float, double e altro ancora.
ms.date: 12/18/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 5e34d291ec15c738f3bc9409df321ede454b6710
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507256"
---
# <a name="default-values-of-c-types-c-reference"></a><span data-ttu-id="c2333-103">Valori predefiniti dei tipi C .</span><span class="sxs-lookup"><span data-stu-id="c2333-103">Default values of C# types (C# reference)</span></span>

<span data-ttu-id="c2333-104">La tabella seguente mostra i valori predefiniti dei tipi C#:</span><span class="sxs-lookup"><span data-stu-id="c2333-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="c2333-105">Type</span><span class="sxs-lookup"><span data-stu-id="c2333-105">Type</span></span>|<span data-ttu-id="c2333-106">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="c2333-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="c2333-107">Qualsiasi tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="c2333-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="c2333-108">Qualsiasi [tipo numerico integrale incorporato](integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="c2333-108">Any [built-in integral numeric type](integral-numeric-types.md)</span></span>|<span data-ttu-id="c2333-109">0 (zero)</span><span class="sxs-lookup"><span data-stu-id="c2333-109">0 (zero)</span></span>|
|<span data-ttu-id="c2333-110">Qualsiasi [tipo numerico a virgola mobile incorporato](floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="c2333-110">Any [built-in floating-point numeric type](floating-point-numeric-types.md)</span></span>|<span data-ttu-id="c2333-111">0 (zero)</span><span class="sxs-lookup"><span data-stu-id="c2333-111">0 (zero)</span></span>|
|[<span data-ttu-id="c2333-112">bool</span><span class="sxs-lookup"><span data-stu-id="c2333-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="c2333-113">char</span><span class="sxs-lookup"><span data-stu-id="c2333-113">char</span></span>](char.md)|<span data-ttu-id="c2333-114">`'\0'` (U+0000)</span><span class="sxs-lookup"><span data-stu-id="c2333-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="c2333-115">Enum</span><span class="sxs-lookup"><span data-stu-id="c2333-115">enum</span></span>](enum.md)|<span data-ttu-id="c2333-116">Valore prodotto dall'espressione `(E)0`, dove `E` è l'identificatore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c2333-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="c2333-117">struct</span><span class="sxs-lookup"><span data-stu-id="c2333-117">struct</span></span>](struct.md)|<span data-ttu-id="c2333-118">Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.</span><span class="sxs-lookup"><span data-stu-id="c2333-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="c2333-119">Qualsiasi [tipo valore nullable](nullable-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="c2333-119">Any [nullable value type](nullable-value-types.md)</span></span>|<span data-ttu-id="c2333-120">Un'istanza per la quale la proprietà <xref:System.Nullable%601.HasValue%2A> è `false` e la proprietà <xref:System.Nullable%601.Value%2A> non è definita.</span><span class="sxs-lookup"><span data-stu-id="c2333-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="c2333-121">Tale valore predefinito è noto anche come valore *null* di un tipo di valore nullable.</span><span class="sxs-lookup"><span data-stu-id="c2333-121">That default value is also known as the *null* value of a nullable value type.</span></span>|

<span data-ttu-id="c2333-122">Utilizzare [ `default` l'operatore](../operators/default.md#default-operator) per produrre il valore predefinito di un tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c2333-122">Use the [`default` operator](../operators/default.md#default-operator) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="c2333-123">A partire dalla versione 7.1 di C, è possibile usare il [ `default` valore letterale](../operators/default.md#default-literal) per inizializzare una variabile con il valore predefinito del relativo tipo:</span><span class="sxs-lookup"><span data-stu-id="c2333-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="c2333-124">Per un tipo valore, anche il costruttore senza parametri implicito produce il valore predefinito del tipo, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c2333-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

<span data-ttu-id="c2333-125">In fase di <xref:System.Type?displayProperty=nameWithType> esecuzione, se l'istanza rappresenta <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> un tipo di valore, è possibile utilizzare il metodo per richiamare il costruttore senza parametri per ottenere il valore predefinito del tipo.</span><span class="sxs-lookup"><span data-stu-id="c2333-125">At run time, if the <xref:System.Type?displayProperty=nameWithType> instance represents a value type, you can use the <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> method to invoke the parameterless constructor to obtain the default value of the type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c2333-126">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c2333-126">C# language specification</span></span>

<span data-ttu-id="c2333-127">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="c2333-127">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="c2333-128">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="c2333-128">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="c2333-129">Costruttori predefiniti</span><span class="sxs-lookup"><span data-stu-id="c2333-129">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="c2333-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2333-130">See also</span></span>

- [<span data-ttu-id="c2333-131">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="c2333-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c2333-132">Costruttori</span><span class="sxs-lookup"><span data-stu-id="c2333-132">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
