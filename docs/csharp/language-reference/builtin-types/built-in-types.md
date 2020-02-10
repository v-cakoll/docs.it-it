---
title: Tipi incorporati- C# riferimento
description: Informazioni C# sui tipi di valore e riferimento predefiniti
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 4f748373350ed0596a5f1d595c273243ae3227c3
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095309"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="95c2e-103">Tipi predefiniti (C# riferimento)</span><span class="sxs-lookup"><span data-stu-id="95c2e-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="95c2e-104">Nella tabella seguente sono elencati C# i tipi di [valore](value-types.md) predefiniti:</span><span class="sxs-lookup"><span data-stu-id="95c2e-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="95c2e-105">C#parola chiave Type</span><span class="sxs-lookup"><span data-stu-id="95c2e-105">C# type keyword</span></span>|<span data-ttu-id="95c2e-106">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="95c2e-106">.NET type</span></span>|
|--------------|-------------------------|
|[`bool`](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|
|[`byte`](integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|
|[`sbyte`](integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|
|[`char`](char.md)|<xref:System.Char?displayProperty=nameWithType>|
|[`decimal`](floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|
|[`double`](floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|
|[`float`](floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|
|[`int`](integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|
|[`uint`](integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

<span data-ttu-id="95c2e-107">Nella tabella seguente sono elencati C# i tipi di [riferimento](../keywords/reference-types.md) incorporati:</span><span class="sxs-lookup"><span data-stu-id="95c2e-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="95c2e-108">C#parola chiave Type</span><span class="sxs-lookup"><span data-stu-id="95c2e-108">C# type keyword</span></span>|<span data-ttu-id="95c2e-109">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="95c2e-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

<span data-ttu-id="95c2e-110">Nelle tabelle precedenti ogni C# parola chiave Type della colonna Left è un alias per il tipo .NET corrispondente.</span><span class="sxs-lookup"><span data-stu-id="95c2e-110">In the preceding tables, each C# type keyword from the left column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="95c2e-111">Sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="95c2e-111">They are interchangeable.</span></span> <span data-ttu-id="95c2e-112">Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="95c2e-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

## <a name="see-also"></a><span data-ttu-id="95c2e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95c2e-113">See also</span></span>

- [<span data-ttu-id="95c2e-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="95c2e-114">C# reference</span></span>](../index.md)
- [<span data-ttu-id="95c2e-115">Valori predefiniti dei C# tipi</span><span class="sxs-lookup"><span data-stu-id="95c2e-115">Default values of C# types</span></span>](default-values.md)
- [<span data-ttu-id="95c2e-116">`dynamic` - Parola chiave</span><span class="sxs-lookup"><span data-stu-id="95c2e-116">`dynamic` keyword</span></span>](reference-types.md#the-dynamic-type)
