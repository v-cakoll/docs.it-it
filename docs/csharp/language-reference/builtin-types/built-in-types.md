---
title: Tipi predefiniti-riferimenti per C#
description: Informazioni sui tipi di valore e riferimento incorporati in C#
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 3366f718cd83a28f475fae9b4e65ce37fe7d8c7b
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803197"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="337e7-103">Tipi incorporati (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="337e7-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="337e7-104">Nella tabella seguente sono elencati i tipi di [valore](value-types.md) predefiniti C#:</span><span class="sxs-lookup"><span data-stu-id="337e7-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="337e7-105">Parola chiave di tipo C#</span><span class="sxs-lookup"><span data-stu-id="337e7-105">C# type keyword</span></span>|<span data-ttu-id="337e7-106">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="337e7-106">.NET type</span></span>|
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

<span data-ttu-id="337e7-107">Nella tabella seguente sono elencati i tipi di [riferimento](../keywords/reference-types.md) incorporati in C#:</span><span class="sxs-lookup"><span data-stu-id="337e7-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="337e7-108">Parola chiave di tipo C#</span><span class="sxs-lookup"><span data-stu-id="337e7-108">C# type keyword</span></span>|<span data-ttu-id="337e7-109">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="337e7-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|
|[`dynamic`](reference-types.md#the-dynamic-type)|<xref:System.Object?displayProperty=nameWithType>|

<span data-ttu-id="337e7-110">Nelle tabelle precedenti ogni parola chiave di tipo C# della colonna sinistra è un alias per il tipo .NET corrispondente.</span><span class="sxs-lookup"><span data-stu-id="337e7-110">In the preceding tables, each C# type keyword from the left column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="337e7-111">Sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="337e7-111">They are interchangeable.</span></span> <span data-ttu-id="337e7-112">Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="337e7-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="337e7-113">La [`void`](void.md) parola chiave rappresenta l'assenza di un tipo.</span><span class="sxs-lookup"><span data-stu-id="337e7-113">The [`void`](void.md) keyword represents the absence of a type.</span></span> <span data-ttu-id="337e7-114">Viene usato come tipo restituito di un metodo che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="337e7-114">You use it as the return type of a method that doesn't return a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="337e7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="337e7-115">See also</span></span>

- [<span data-ttu-id="337e7-116">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="337e7-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="337e7-117">Valori predefiniti dei tipi C#</span><span class="sxs-lookup"><span data-stu-id="337e7-117">Default values of C# types</span></span>](default-values.md)
