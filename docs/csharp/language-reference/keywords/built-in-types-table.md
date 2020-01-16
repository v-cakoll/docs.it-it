---
title: Tabella dei tipi predefiniti - Riferimenti per C#
description: Parole chiave per i tipi C# incorporati
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 1836458972c453b733287e58e783f32892d27fde
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964378"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="99700-103">Tabella dei tipi incorporati (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="99700-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="99700-104">Nella tabella seguente vengono illustrate le parole chiave per C# i tipi incorporati, ovvero alias di tipi predefiniti nello spazio dei nomi <xref:System>:</span><span class="sxs-lookup"><span data-stu-id="99700-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace:</span></span>

|<span data-ttu-id="99700-105">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="99700-105">C# type</span></span>|<span data-ttu-id="99700-106">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="99700-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="99700-107">bool</span><span class="sxs-lookup"><span data-stu-id="99700-107">bool</span></span>](../builtin-types/bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-108">byte</span><span class="sxs-lookup"><span data-stu-id="99700-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="99700-109">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-110">char</span><span class="sxs-lookup"><span data-stu-id="99700-110">char</span></span>](../builtin-types/char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-111">decimal</span><span class="sxs-lookup"><span data-stu-id="99700-111">decimal</span></span>](../builtin-types/floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-112">double</span><span class="sxs-lookup"><span data-stu-id="99700-112">double</span></span>](../builtin-types/floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-113">float</span><span class="sxs-lookup"><span data-stu-id="99700-113">float</span></span>](../builtin-types/floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-114">int</span><span class="sxs-lookup"><span data-stu-id="99700-114">int</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-115">uint</span><span class="sxs-lookup"><span data-stu-id="99700-115">uint</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-116">long</span><span class="sxs-lookup"><span data-stu-id="99700-116">long</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-117">ulong</span><span class="sxs-lookup"><span data-stu-id="99700-117">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-118">object</span><span class="sxs-lookup"><span data-stu-id="99700-118">object</span></span>](../builtin-types/reference-types.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-119">short</span><span class="sxs-lookup"><span data-stu-id="99700-119">short</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-120">ushort</span><span class="sxs-lookup"><span data-stu-id="99700-120">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="99700-121">string</span><span class="sxs-lookup"><span data-stu-id="99700-121">string</span></span>](../builtin-types/reference-types.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="99700-122">Note</span><span class="sxs-lookup"><span data-stu-id="99700-122">Remarks</span></span>

<span data-ttu-id="99700-123">Tutti i tipi nella tabella, ad eccezione di `object` e `string`, sono detti tipi semplici.</span><span class="sxs-lookup"><span data-stu-id="99700-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>

<span data-ttu-id="99700-124">I tipi .NET e i relativi alias per le parole chiave per i tipi C# sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="99700-124">The .NET types and their C# type keyword aliases are interchangeable.</span></span> <span data-ttu-id="99700-125">Ad esempio, è possibile dichiarare una variabile integer, usando le seguenti dichiarazioni:</span><span class="sxs-lookup"><span data-stu-id="99700-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="99700-126">Usare l'operatore [typeof](../operators/type-testing-and-cast.md#typeof-operator) per ottenere l'istanza <xref:System.Type?displayProperty=nameWithType> che rappresenta il tipo specificato:</span><span class="sxs-lookup"><span data-stu-id="99700-126">Use the [typeof](../operators/type-testing-and-cast.md#typeof-operator) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="99700-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99700-127">See also</span></span>

- [<span data-ttu-id="99700-128">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="99700-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="99700-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="99700-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="99700-130">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="99700-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="99700-131">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="99700-131">Value types</span></span>](value-types.md)
- [<span data-ttu-id="99700-132">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="99700-132">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="99700-133">Valori predefiniti dei C# tipi</span><span class="sxs-lookup"><span data-stu-id="99700-133">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="99700-134">dynamic</span><span class="sxs-lookup"><span data-stu-id="99700-134">dynamic</span></span>](../builtin-types/reference-types.md#the-dynamic-type)
