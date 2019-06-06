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
ms.openlocfilehash: 4fc9a35f69540e047a97c21788015ca8e54068a0
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422027"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="f0856-103">Tabella dei valori predefiniti (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f0856-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="f0856-104">La tabella seguente mostra i valori predefiniti dei [tipi valore](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="f0856-104">The following table shows the default values of [value types](value-types.md).</span></span>

|<span data-ttu-id="f0856-105">Tipo valore</span><span class="sxs-lookup"><span data-stu-id="f0856-105">Value type</span></span>|<span data-ttu-id="f0856-106">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="f0856-106">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="f0856-107">bool</span><span class="sxs-lookup"><span data-stu-id="f0856-107">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="f0856-108">byte</span><span class="sxs-lookup"><span data-stu-id="f0856-108">byte</span></span>](byte.md)|<span data-ttu-id="f0856-109">0</span><span class="sxs-lookup"><span data-stu-id="f0856-109">0</span></span>|
|[<span data-ttu-id="f0856-110">char</span><span class="sxs-lookup"><span data-stu-id="f0856-110">char</span></span>](char.md)|<span data-ttu-id="f0856-111">'\0'</span><span class="sxs-lookup"><span data-stu-id="f0856-111">'\0'</span></span>|
|[<span data-ttu-id="f0856-112">decimal</span><span class="sxs-lookup"><span data-stu-id="f0856-112">decimal</span></span>](decimal.md)|<span data-ttu-id="f0856-113">0M</span><span class="sxs-lookup"><span data-stu-id="f0856-113">0M</span></span>|
|[<span data-ttu-id="f0856-114">double</span><span class="sxs-lookup"><span data-stu-id="f0856-114">double</span></span>](double.md)|<span data-ttu-id="f0856-115">0.0D</span><span class="sxs-lookup"><span data-stu-id="f0856-115">0.0D</span></span>|
|[<span data-ttu-id="f0856-116">enum</span><span class="sxs-lookup"><span data-stu-id="f0856-116">enum</span></span>](enum.md)|<span data-ttu-id="f0856-117">Valore prodotto dall'espressione `(E)0`, dove `E` è l'identificatore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f0856-117">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="f0856-118">float</span><span class="sxs-lookup"><span data-stu-id="f0856-118">float</span></span>](float.md)|<span data-ttu-id="f0856-119">0.0F</span><span class="sxs-lookup"><span data-stu-id="f0856-119">0.0F</span></span>|
|[<span data-ttu-id="f0856-120">int</span><span class="sxs-lookup"><span data-stu-id="f0856-120">int</span></span>](int.md)|<span data-ttu-id="f0856-121">0</span><span class="sxs-lookup"><span data-stu-id="f0856-121">0</span></span>|
|[<span data-ttu-id="f0856-122">long</span><span class="sxs-lookup"><span data-stu-id="f0856-122">long</span></span>](long.md)|<span data-ttu-id="f0856-123">0L</span><span class="sxs-lookup"><span data-stu-id="f0856-123">0L</span></span>|
|[<span data-ttu-id="f0856-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="f0856-124">sbyte</span></span>](sbyte.md)|<span data-ttu-id="f0856-125">0</span><span class="sxs-lookup"><span data-stu-id="f0856-125">0</span></span>|
|[<span data-ttu-id="f0856-126">short</span><span class="sxs-lookup"><span data-stu-id="f0856-126">short</span></span>](short.md)|<span data-ttu-id="f0856-127">0</span><span class="sxs-lookup"><span data-stu-id="f0856-127">0</span></span>|
|[<span data-ttu-id="f0856-128">struct</span><span class="sxs-lookup"><span data-stu-id="f0856-128">struct</span></span>](struct.md)|<span data-ttu-id="f0856-129">Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.</span><span class="sxs-lookup"><span data-stu-id="f0856-129">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="f0856-130">uint</span><span class="sxs-lookup"><span data-stu-id="f0856-130">uint</span></span>](uint.md)|<span data-ttu-id="f0856-131">0</span><span class="sxs-lookup"><span data-stu-id="f0856-131">0</span></span>|
|[<span data-ttu-id="f0856-132">ulong</span><span class="sxs-lookup"><span data-stu-id="f0856-132">ulong</span></span>](ulong.md)|<span data-ttu-id="f0856-133">0</span><span class="sxs-lookup"><span data-stu-id="f0856-133">0</span></span>|
|[<span data-ttu-id="f0856-134">ushort</span><span class="sxs-lookup"><span data-stu-id="f0856-134">ushort</span></span>](ushort.md)|<span data-ttu-id="f0856-135">0</span><span class="sxs-lookup"><span data-stu-id="f0856-135">0</span></span>|

## <a name="remarks"></a><span data-ttu-id="f0856-136">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f0856-136">Remarks</span></span>

<span data-ttu-id="f0856-137">Non è possibile usare le variabili non inizializzate in C#.</span><span class="sxs-lookup"><span data-stu-id="f0856-137">You cannot use uninitialized variables in C#.</span></span> <span data-ttu-id="f0856-138">È possibile inizializzare una variabile con il valore predefinito del relativo tipo.</span><span class="sxs-lookup"><span data-stu-id="f0856-138">You can initialize a variable with the default value of its type.</span></span> <span data-ttu-id="f0856-139">È anche possibile usare il valore predefinito di un tipo per specificare il valore predefinito di un [argomento facoltativo](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments) del metodo.</span><span class="sxs-lookup"><span data-stu-id="f0856-139">You also can use the default value of a type to specify the default value of a method's [optional argument](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments).</span></span>

<span data-ttu-id="f0856-140">Usare l'[espressione valore predefinito](../../programming-guide/statements-expressions-operators/default-value-expressions.md) per produrre il valore predefinito di un tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f0856-140">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="f0856-141">A partire da C# 7.1 è possibile usare il [ valore letterale `default`](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) per inizializzare una variabile con il valore predefinito del relativo tipo:</span><span class="sxs-lookup"><span data-stu-id="f0856-141">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="f0856-142">È anche possibile usare il costruttore senza parametri o il costruttore senza parametri implicito per generare il valore predefinito di un tipo valore, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f0856-142">You also can use the parameterless constructor or the implicit parameterless constructor to produce the default value of a value type, as the following example shows.</span></span> <span data-ttu-id="f0856-143">Per altre informazioni sui costruttori, vedere l'articolo [Costruttori](../../programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="f0856-143">For more information about constructors, see the [Constructors](../../programming-guide/classes-and-structs/constructors.md) article.</span></span>

```csharp
int a = new int();
```

<span data-ttu-id="f0856-144">Il valore predefinito di un qualsiasi [tipo di riferimento](reference-types.md) è `null`.</span><span class="sxs-lookup"><span data-stu-id="f0856-144">The default value of any [reference type](reference-types.md) is `null`.</span></span> <span data-ttu-id="f0856-145">Il valore predefinito di un [tipo nullable](../../programming-guide/nullable-types/index.md) è un'istanza per la quale la proprietà <xref:System.Nullable%601.HasValue%2A> è `false` e la proprietà <xref:System.Nullable%601.Value%2A> non è definita.</span><span class="sxs-lookup"><span data-stu-id="f0856-145">The default value of a [nullable type](../../programming-guide/nullable-types/index.md) is an instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0856-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0856-146">See also</span></span>

- [<span data-ttu-id="f0856-147">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f0856-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f0856-148">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f0856-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f0856-149">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="f0856-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f0856-150">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="f0856-150">Value types</span></span>](value-types.md)
- [<span data-ttu-id="f0856-151">Tabella dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="f0856-151">Value types table</span></span>](value-types-table.md)
- [<span data-ttu-id="f0856-152">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="f0856-152">Built-in types table</span></span>](built-in-types-table.md)
