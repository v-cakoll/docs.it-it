---
title: Tipi incorporati - Informazioni di riferimento su C
description: Imparare i tipi di riferimento e valori predefiniti di C
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: bf8823c6674b1ff3f0028a50df8ce8d0f803cfc1
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389485"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="8a2c6-103">Tipi incorporati (riferimenti in C</span><span class="sxs-lookup"><span data-stu-id="8a2c6-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="8a2c6-104">Nella tabella seguente sono elencati i tipi di [valore](value-types.md) incorporati di C' :</span><span class="sxs-lookup"><span data-stu-id="8a2c6-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="8a2c6-105">Parola chiave del tipo C</span><span class="sxs-lookup"><span data-stu-id="8a2c6-105">C# type keyword</span></span>|<span data-ttu-id="8a2c6-106">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="8a2c6-106">.NET type</span></span>|
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

<span data-ttu-id="8a2c6-107">Nella tabella seguente sono elencati i tipi di [riferimento](../keywords/reference-types.md) incorporati in C' :</span><span class="sxs-lookup"><span data-stu-id="8a2c6-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="8a2c6-108">Parola chiave del tipo C</span><span class="sxs-lookup"><span data-stu-id="8a2c6-108">C# type keyword</span></span>|<span data-ttu-id="8a2c6-109">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="8a2c6-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

<span data-ttu-id="8a2c6-110">Nelle tabelle precedenti, ogni parola chiave di tipo C , dalla colonna di sinistra è un alias per il tipo .NET corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8a2c6-110">In the preceding tables, each C# type keyword from the left column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="8a2c6-111">Sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="8a2c6-111">They are interchangeable.</span></span> <span data-ttu-id="8a2c6-112">Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="8a2c6-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="8a2c6-113">La [`void`](void.md) parola chiave rappresenta l'assenza di un tipo.</span><span class="sxs-lookup"><span data-stu-id="8a2c6-113">The [`void`](void.md) keyword represents the absence of a type.</span></span> <span data-ttu-id="8a2c6-114">Utilizzarlo come il tipo restituito di un metodo che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="8a2c6-114">You use it as the return type of a method that doesn't return a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a2c6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a2c6-115">See also</span></span>

- [<span data-ttu-id="8a2c6-116">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="8a2c6-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8a2c6-117">Valori predefiniti dei tipi c'è</span><span class="sxs-lookup"><span data-stu-id="8a2c6-117">Default values of C# types</span></span>](default-values.md)
- [<span data-ttu-id="8a2c6-118">`dynamic`Parola chiave</span><span class="sxs-lookup"><span data-stu-id="8a2c6-118">`dynamic` keyword</span></span>](reference-types.md#the-dynamic-type)
