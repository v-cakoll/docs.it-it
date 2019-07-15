---
title: Tabella dei valori predefiniti - Riferimenti per C#
ms.custom: seodec18
description: Informazioni sui valori predefiniti dei tipi valore C#.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: ec5fb4681f0e0562c5aefdf336841416f96bdf98
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661405"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="9a7e6-103">Tabella dei valori predefiniti (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9a7e6-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="9a7e6-104">La tabella seguente mostra i valori predefiniti dei [tipi valore](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="9a7e6-104">The following table shows the default values of [value types](value-types.md).</span></span>

|<span data-ttu-id="9a7e6-105">Tipo valore</span><span class="sxs-lookup"><span data-stu-id="9a7e6-105">Value type</span></span>|<span data-ttu-id="9a7e6-106">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="9a7e6-106">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="9a7e6-107">bool</span><span class="sxs-lookup"><span data-stu-id="9a7e6-107">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="9a7e6-108">byte</span><span class="sxs-lookup"><span data-stu-id="9a7e6-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="9a7e6-109">0</span><span class="sxs-lookup"><span data-stu-id="9a7e6-109">0</span></span>|
|[<span data-ttu-id="9a7e6-110">char</span><span class="sxs-lookup"><span data-stu-id="9a7e6-110">char</span></span>](char.md)|<span data-ttu-id="9a7e6-111">'\0'</span><span class="sxs-lookup"><span data-stu-id="9a7e6-111">'\0'</span></span>|
|[<span data-ttu-id="9a7e6-112">decimal</span><span class="sxs-lookup"><span data-stu-id="9a7e6-112">decimal</span></span>](../builtin-types/floating-point-numeric-types.md)|<span data-ttu-id="9a7e6-113">0M</span><span class="sxs-lookup"><span data-stu-id="9a7e6-113">0M</span></span>|
|[<span data-ttu-id="9a7e6-114">double</span><span class="sxs-lookup"><span data-stu-id="9a7e6-114">double</span></span>](../builtin-types/floating-point-numeric-types.md)|<span data-ttu-id="9a7e6-115">0.0D</span><span class="sxs-lookup"><span data-stu-id="9a7e6-115">0.0D</span></span>|
|[<span data-ttu-id="9a7e6-116">enum</span><span class="sxs-lookup"><span data-stu-id="9a7e6-116">enum</span></span>](enum.md)|<span data-ttu-id="9a7e6-117">Valore prodotto dall'espressione `(E)0`, dove `E` è l'identificatore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-117">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="9a7e6-118">float</span><span class="sxs-lookup"><span data-stu-id="9a7e6-118">float</span></span>](../builtin-types/floating-point-numeric-types.md)|<span data-ttu-id="9a7e6-119">0.0F</span><span class="sxs-lookup"><span data-stu-id="9a7e6-119">0.0F</span></span>|
|[<span data-ttu-id="9a7e6-120">int</span><span class="sxs-lookup"><span data-stu-id="9a7e6-120">int</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="9a7e6-121">0</span><span class="sxs-lookup"><span data-stu-id="9a7e6-121">0</span></span>|
|[<span data-ttu-id="9a7e6-122">long</span><span class="sxs-lookup"><span data-stu-id="9a7e6-122">long</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="9a7e6-123">0L</span><span class="sxs-lookup"><span data-stu-id="9a7e6-123">0L</span></span>|
|[<span data-ttu-id="9a7e6-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="9a7e6-124">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="9a7e6-125">0</span><span class="sxs-lookup"><span data-stu-id="9a7e6-125">0</span></span>|
|[<span data-ttu-id="9a7e6-126">short</span><span class="sxs-lookup"><span data-stu-id="9a7e6-126">short</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="9a7e6-127">0</span><span class="sxs-lookup"><span data-stu-id="9a7e6-127">0</span></span>|
|[<span data-ttu-id="9a7e6-128">struct</span><span class="sxs-lookup"><span data-stu-id="9a7e6-128">struct</span></span>](struct.md)|<span data-ttu-id="9a7e6-129">Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-129">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="9a7e6-130">uint</span><span class="sxs-lookup"><span data-stu-id="9a7e6-130">uint</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="9a7e6-131">0</span><span class="sxs-lookup"><span data-stu-id="9a7e6-131">0</span></span>|
|[<span data-ttu-id="9a7e6-132">ulong</span><span class="sxs-lookup"><span data-stu-id="9a7e6-132">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="9a7e6-133">0</span><span class="sxs-lookup"><span data-stu-id="9a7e6-133">0</span></span>|
|[<span data-ttu-id="9a7e6-134">ushort</span><span class="sxs-lookup"><span data-stu-id="9a7e6-134">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="9a7e6-135">0</span><span class="sxs-lookup"><span data-stu-id="9a7e6-135">0</span></span>|

## <a name="remarks"></a><span data-ttu-id="9a7e6-136">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9a7e6-136">Remarks</span></span>

<span data-ttu-id="9a7e6-137">Non è possibile usare le variabili non inizializzate in C#.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-137">You cannot use uninitialized variables in C#.</span></span> <span data-ttu-id="9a7e6-138">È possibile inizializzare una variabile con il valore predefinito del relativo tipo.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-138">You can initialize a variable with the default value of its type.</span></span> <span data-ttu-id="9a7e6-139">È anche possibile usare il valore predefinito di un tipo per specificare il valore predefinito di un [argomento facoltativo](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments) del metodo.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-139">You also can use the default value of a type to specify the default value of a method's [optional argument](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments).</span></span>

<span data-ttu-id="9a7e6-140">Usare l'[espressione valore predefinito](../../programming-guide/statements-expressions-operators/default-value-expressions.md) per produrre il valore predefinito di un tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9a7e6-140">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="9a7e6-141">A partire da C# 7.1 è possibile usare il [ valore letterale `default`](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) per inizializzare una variabile con il valore predefinito del relativo tipo:</span><span class="sxs-lookup"><span data-stu-id="9a7e6-141">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="9a7e6-142">È anche possibile usare il costruttore senza parametri o il costruttore senza parametri implicito per generare il valore predefinito di un tipo valore, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-142">You also can use the parameterless constructor or the implicit parameterless constructor to produce the default value of a value type, as the following example shows.</span></span> <span data-ttu-id="9a7e6-143">Per altre informazioni sui costruttori, vedere l'articolo [Costruttori](../../programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="9a7e6-143">For more information about constructors, see the [Constructors](../../programming-guide/classes-and-structs/constructors.md) article.</span></span>

```csharp
int a = new int();
```

<span data-ttu-id="9a7e6-144">Il valore predefinito di un qualsiasi [tipo di riferimento](reference-types.md) è `null`.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-144">The default value of any [reference type](reference-types.md) is `null`.</span></span> <span data-ttu-id="9a7e6-145">Il valore predefinito di un [tipo nullable](../../programming-guide/nullable-types/index.md) è un'istanza per la quale la proprietà <xref:System.Nullable%601.HasValue%2A> è `false` e la proprietà <xref:System.Nullable%601.Value%2A> non è definita.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-145">The default value of a [nullable type](../../programming-guide/nullable-types/index.md) is an instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a7e6-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a7e6-146">See also</span></span>

- [<span data-ttu-id="9a7e6-147">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="9a7e6-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9a7e6-148">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9a7e6-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9a7e6-149">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="9a7e6-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9a7e6-150">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="9a7e6-150">Value types</span></span>](value-types.md)
- [<span data-ttu-id="9a7e6-151">Tabella dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="9a7e6-151">Value types table</span></span>](value-types-table.md)
- [<span data-ttu-id="9a7e6-152">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="9a7e6-152">Built-in types table</span></span>](built-in-types-table.md)
