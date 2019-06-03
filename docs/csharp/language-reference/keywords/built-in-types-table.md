---
title: Tabella dei tipi predefiniti - Riferimenti per C#
ms.custom: seodec18
description: Parole chiave per i tipi C# incorporati
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: bd8c52cd798496a4df3086411dfe3be6241fbff5
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422339"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="792d1-103">Tabella dei tipi incorporati (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="792d1-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="792d1-104">La tabella seguente include le parole chiave per i tipi predefiniti di C#, che rappresentano gli alias dei tipi predefiniti nello spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="792d1-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="792d1-105">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="792d1-105">C# type</span></span>|<span data-ttu-id="792d1-106">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="792d1-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="792d1-107">bool</span><span class="sxs-lookup"><span data-stu-id="792d1-107">bool</span></span>](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-108">byte</span><span class="sxs-lookup"><span data-stu-id="792d1-108">byte</span></span>](byte.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="792d1-109">sbyte</span></span>](sbyte.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-110">char</span><span class="sxs-lookup"><span data-stu-id="792d1-110">char</span></span>](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-111">decimal</span><span class="sxs-lookup"><span data-stu-id="792d1-111">decimal</span></span>](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-112">double</span><span class="sxs-lookup"><span data-stu-id="792d1-112">double</span></span>](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-113">float</span><span class="sxs-lookup"><span data-stu-id="792d1-113">float</span></span>](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-114">int</span><span class="sxs-lookup"><span data-stu-id="792d1-114">int</span></span>](int.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-115">uint</span><span class="sxs-lookup"><span data-stu-id="792d1-115">uint</span></span>](uint.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-116">long</span><span class="sxs-lookup"><span data-stu-id="792d1-116">long</span></span>](long.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-117">ulong</span><span class="sxs-lookup"><span data-stu-id="792d1-117">ulong</span></span>](ulong.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-118">object</span><span class="sxs-lookup"><span data-stu-id="792d1-118">object</span></span>](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-119">short</span><span class="sxs-lookup"><span data-stu-id="792d1-119">short</span></span>](short.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-120">ushort</span><span class="sxs-lookup"><span data-stu-id="792d1-120">ushort</span></span>](ushort.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="792d1-121">string</span><span class="sxs-lookup"><span data-stu-id="792d1-121">string</span></span>](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="792d1-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="792d1-122">Remarks</span></span>

<span data-ttu-id="792d1-123">Tutti i tipi nella tabella, ad eccezione di `object` e `string`, sono detti tipi semplici.</span><span class="sxs-lookup"><span data-stu-id="792d1-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
<span data-ttu-id="792d1-124">Le parole chiave per i tipi C# e i relativi alias sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="792d1-124">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="792d1-125">Ad esempio, è possibile dichiarare una variabile integer, usando le seguenti dichiarazioni:</span><span class="sxs-lookup"><span data-stu-id="792d1-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>  

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="792d1-126">Usare l'operatore [typeof](typeof.md) per ottenere l'istanza <xref:System.Type?displayProperty=nameWithType> che rappresenta il tipo specificato:</span><span class="sxs-lookup"><span data-stu-id="792d1-126">Use the [typeof](typeof.md) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="792d1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="792d1-127">See also</span></span>

- [<span data-ttu-id="792d1-128">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="792d1-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="792d1-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="792d1-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="792d1-130">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="792d1-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="792d1-131">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="792d1-131">Value types</span></span>](value-types.md)
- [<span data-ttu-id="792d1-132">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="792d1-132">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="792d1-133">Tabella dei valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="792d1-133">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="792d1-134">dynamic</span><span class="sxs-lookup"><span data-stu-id="792d1-134">dynamic</span></span>](dynamic.md)
