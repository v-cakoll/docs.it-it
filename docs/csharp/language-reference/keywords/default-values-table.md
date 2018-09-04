---
title: Tabella dei valori predefiniti (Riferimenti per C#)
description: Informazioni sui valori predefiniti dei tipi valore C#.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 184a9f42ddd3654a81aef0b7ce35e404de2d4bb9
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935839"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="52580-103">Tabella dei valori predefiniti (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="52580-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="52580-104">La tabella seguente mostra i valori predefiniti dei [tipi valore](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="52580-104">The following table shows the default values of [value types](value-types.md).</span></span>

|<span data-ttu-id="52580-105">Tipo valore</span><span class="sxs-lookup"><span data-stu-id="52580-105">Value type</span></span>|<span data-ttu-id="52580-106">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="52580-106">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="52580-107">bool</span><span class="sxs-lookup"><span data-stu-id="52580-107">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="52580-108">byte</span><span class="sxs-lookup"><span data-stu-id="52580-108">byte</span></span>](byte.md)|<span data-ttu-id="52580-109">0</span><span class="sxs-lookup"><span data-stu-id="52580-109">0</span></span>|
|[<span data-ttu-id="52580-110">char</span><span class="sxs-lookup"><span data-stu-id="52580-110">char</span></span>](char.md)|<span data-ttu-id="52580-111">'\0'</span><span class="sxs-lookup"><span data-stu-id="52580-111">'\0'</span></span>|
|[<span data-ttu-id="52580-112">decimal</span><span class="sxs-lookup"><span data-stu-id="52580-112">decimal</span></span>](decimal.md)|<span data-ttu-id="52580-113">0M</span><span class="sxs-lookup"><span data-stu-id="52580-113">0M</span></span>|
|[<span data-ttu-id="52580-114">double</span><span class="sxs-lookup"><span data-stu-id="52580-114">double</span></span>](double.md)|<span data-ttu-id="52580-115">0.0D</span><span class="sxs-lookup"><span data-stu-id="52580-115">0.0D</span></span>|
|[<span data-ttu-id="52580-116">enum</span><span class="sxs-lookup"><span data-stu-id="52580-116">enum</span></span>](enum.md)|<span data-ttu-id="52580-117">Valore prodotto dall'espressione `(E)0`, dove `E` è l'identificatore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="52580-117">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="52580-118">float</span><span class="sxs-lookup"><span data-stu-id="52580-118">float</span></span>](float.md)|<span data-ttu-id="52580-119">0.0F</span><span class="sxs-lookup"><span data-stu-id="52580-119">0.0F</span></span>|
|[<span data-ttu-id="52580-120">int</span><span class="sxs-lookup"><span data-stu-id="52580-120">int</span></span>](int.md)|<span data-ttu-id="52580-121">0</span><span class="sxs-lookup"><span data-stu-id="52580-121">0</span></span>|
|[<span data-ttu-id="52580-122">long</span><span class="sxs-lookup"><span data-stu-id="52580-122">long</span></span>](long.md)|<span data-ttu-id="52580-123">0L</span><span class="sxs-lookup"><span data-stu-id="52580-123">0L</span></span>|
|[<span data-ttu-id="52580-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="52580-124">sbyte</span></span>](sbyte.md)|<span data-ttu-id="52580-125">0</span><span class="sxs-lookup"><span data-stu-id="52580-125">0</span></span>|
|[<span data-ttu-id="52580-126">short</span><span class="sxs-lookup"><span data-stu-id="52580-126">short</span></span>](short.md)|<span data-ttu-id="52580-127">0</span><span class="sxs-lookup"><span data-stu-id="52580-127">0</span></span>|
|[<span data-ttu-id="52580-128">struct</span><span class="sxs-lookup"><span data-stu-id="52580-128">struct</span></span>](struct.md)|<span data-ttu-id="52580-129">Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.</span><span class="sxs-lookup"><span data-stu-id="52580-129">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="52580-130">uint</span><span class="sxs-lookup"><span data-stu-id="52580-130">uint</span></span>](uint.md)|<span data-ttu-id="52580-131">0</span><span class="sxs-lookup"><span data-stu-id="52580-131">0</span></span>|
|[<span data-ttu-id="52580-132">ulong</span><span class="sxs-lookup"><span data-stu-id="52580-132">ulong</span></span>](ulong.md)|<span data-ttu-id="52580-133">0</span><span class="sxs-lookup"><span data-stu-id="52580-133">0</span></span>|
|[<span data-ttu-id="52580-134">ushort</span><span class="sxs-lookup"><span data-stu-id="52580-134">ushort</span></span>](ushort.md)|<span data-ttu-id="52580-135">0</span><span class="sxs-lookup"><span data-stu-id="52580-135">0</span></span>|

## <a name="remarks"></a><span data-ttu-id="52580-136">Note</span><span class="sxs-lookup"><span data-stu-id="52580-136">Remarks</span></span>

<span data-ttu-id="52580-137">Non è possibile usare le variabili non inizializzate in C#.</span><span class="sxs-lookup"><span data-stu-id="52580-137">You cannot use uninitialized variables in C#.</span></span> <span data-ttu-id="52580-138">È possibile inizializzare una variabile con il valore predefinito del relativo tipo.</span><span class="sxs-lookup"><span data-stu-id="52580-138">You can initialize a variable with the default value of its type.</span></span> <span data-ttu-id="52580-139">È anche possibile usare il valore predefinito di un tipo per specificare il valore predefinito di un [argomento facoltativo](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments) del metodo.</span><span class="sxs-lookup"><span data-stu-id="52580-139">You also can use the default value of a type to specify the default value of a method's [optional argument](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments).</span></span>

<span data-ttu-id="52580-140">Usare l'[espressione valore predefinito](../../programming-guide/statements-expressions-operators/default-value-expressions.md) per produrre il valore predefinito di un tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="52580-140">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="52580-141">A partire da C# 7.1 è possibile usare il [ valore letterale `default`](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) per inizializzare una variabile con il valore predefinito del relativo tipo:</span><span class="sxs-lookup"><span data-stu-id="52580-141">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="52580-142">È anche possibile usare il costruttore predefinito o il costruttore predefinito implicito per produrre il valore predefinito di un tipo valore, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="52580-142">You also can use the default constructor or the implicit default constructor to produce the default value of a value type, as the following example shows.</span></span> <span data-ttu-id="52580-143">Per altre informazioni sui costruttori, vedere l'articolo [Costruttori](../../programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="52580-143">For more information about constructors, see the [Constructors](../../programming-guide/classes-and-structs/constructors.md) article.</span></span>

```csharp
int a = new int();
```

<span data-ttu-id="52580-144">Il valore predefinito di un qualsiasi [tipo di riferimento](reference-types.md) è `null`.</span><span class="sxs-lookup"><span data-stu-id="52580-144">The default value of any [reference type](reference-types.md) is `null`.</span></span> <span data-ttu-id="52580-145">Il valore predefinito di un [tipo nullable](../../programming-guide/nullable-types/index.md) è un'istanza per la quale la proprietà <xref:System.Nullable%601.HasValue%2A> è `false` e la proprietà <xref:System.Nullable%601.Value%2A> non è definita.</span><span class="sxs-lookup"><span data-stu-id="52580-145">The default value of a [nullable type](../../programming-guide/nullable-types/index.md) is an instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>

## <a name="see-also"></a><span data-ttu-id="52580-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52580-146">See also</span></span>

- [<span data-ttu-id="52580-147">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="52580-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="52580-148">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="52580-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="52580-149">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="52580-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="52580-150">Tabelle di riferimento per i tipi</span><span class="sxs-lookup"><span data-stu-id="52580-150">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="52580-151">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="52580-151">Value types</span></span>](value-types.md)
- [<span data-ttu-id="52580-152">Tabella dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="52580-152">Value types table</span></span>](value-types-table.md)
- [<span data-ttu-id="52580-153">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="52580-153">Built-in types table</span></span>](built-in-types-table.md)
