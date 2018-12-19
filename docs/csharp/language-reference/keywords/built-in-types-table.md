---
title: Tabella dei tipi predefiniti - Riferimenti per C#
ms.custom: seodec18
description: Parole chiave per i tipi C# incorporati
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: fae0cedfe8bf675dceb9cb9d5835d923cae8b4ab
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235625"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="842fc-103">Tabella dei tipi incorporati (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="842fc-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="842fc-104">La tabella seguente include le parole chiave per i tipi predefiniti di C#, che rappresentano gli alias dei tipi predefiniti nello spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="842fc-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="842fc-105">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="842fc-105">C# type</span></span>|<span data-ttu-id="842fc-106">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="842fc-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="842fc-107">bool</span><span class="sxs-lookup"><span data-stu-id="842fc-107">bool</span></span>](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-108">byte</span><span class="sxs-lookup"><span data-stu-id="842fc-108">byte</span></span>](byte.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="842fc-109">sbyte</span></span>](sbyte.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-110">char</span><span class="sxs-lookup"><span data-stu-id="842fc-110">char</span></span>](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-111">decimal</span><span class="sxs-lookup"><span data-stu-id="842fc-111">decimal</span></span>](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-112">double</span><span class="sxs-lookup"><span data-stu-id="842fc-112">double</span></span>](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-113">float</span><span class="sxs-lookup"><span data-stu-id="842fc-113">float</span></span>](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-114">int</span><span class="sxs-lookup"><span data-stu-id="842fc-114">int</span></span>](int.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-115">uint</span><span class="sxs-lookup"><span data-stu-id="842fc-115">uint</span></span>](uint.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-116">long</span><span class="sxs-lookup"><span data-stu-id="842fc-116">long</span></span>](long.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-117">ulong</span><span class="sxs-lookup"><span data-stu-id="842fc-117">ulong</span></span>](ulong.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-118">object</span><span class="sxs-lookup"><span data-stu-id="842fc-118">object</span></span>](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-119">short</span><span class="sxs-lookup"><span data-stu-id="842fc-119">short</span></span>](short.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-120">ushort</span><span class="sxs-lookup"><span data-stu-id="842fc-120">ushort</span></span>](ushort.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="842fc-121">string</span><span class="sxs-lookup"><span data-stu-id="842fc-121">string</span></span>](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="842fc-122">Note</span><span class="sxs-lookup"><span data-stu-id="842fc-122">Remarks</span></span>

<span data-ttu-id="842fc-123">Tutti i tipi nella tabella, ad eccezione di `object` e `string`, sono detti tipi semplici.</span><span class="sxs-lookup"><span data-stu-id="842fc-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
<span data-ttu-id="842fc-124">Le parole chiave per i tipi C# e i relativi alias sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="842fc-124">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="842fc-125">Ad esempio, è possibile dichiarare una variabile integer, usando le seguenti dichiarazioni:</span><span class="sxs-lookup"><span data-stu-id="842fc-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>  

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="842fc-126">Usare l'operatore [typeof](typeof.md) per ottenere l'istanza <xref:System.Type?displayProperty=nameWithType> che rappresenta il tipo specificato:</span><span class="sxs-lookup"><span data-stu-id="842fc-126">Use the [typeof](typeof.md) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="842fc-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="842fc-127">See also</span></span>

- [<span data-ttu-id="842fc-128">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="842fc-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="842fc-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="842fc-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="842fc-130">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="842fc-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="842fc-131">Tabelle di riferimento per i tipi</span><span class="sxs-lookup"><span data-stu-id="842fc-131">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="842fc-132">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="842fc-132">Value types</span></span>](value-types.md)
- [<span data-ttu-id="842fc-133">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="842fc-133">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="842fc-134">Tabella dei valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="842fc-134">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="842fc-135">dynamic</span><span class="sxs-lookup"><span data-stu-id="842fc-135">dynamic</span></span>](dynamic.md)
