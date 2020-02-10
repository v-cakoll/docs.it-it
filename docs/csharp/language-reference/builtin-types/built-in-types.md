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
# <a name="built-in-types-c-reference"></a>Tipi predefiniti (C# riferimento)

Nella tabella seguente sono elencati C# i tipi di [valore](value-types.md) predefiniti:

|C#parola chiave Type|Tipo .NET|
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

Nella tabella seguente sono elencati C# i tipi di [riferimento](../keywords/reference-types.md) incorporati:

|C#parola chiave Type|Tipo .NET|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

Nelle tabelle precedenti ogni C# parola chiave Type della colonna Left è un alias per il tipo .NET corrispondente. Sono intercambiabili. Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:

```csharp
int a = 123;
System.Int32 b = 123;
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Valori predefiniti dei C# tipi](default-values.md)
- [`dynamic` - Parola chiave](reference-types.md#the-dynamic-type)
