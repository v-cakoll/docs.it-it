---
title: Tabella dei tipi di valore - Riferimenti per C#
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 959d4840344ba041ae1b01fd6d202f2b53936afc
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422366"
---
# <a name="value-types-table-c-reference"></a>Tabella dei tipi di valore (Riferimenti per C#)

La tabella seguente mostra i tipi valore di C#:

|Tipo valore|Category|Suffisso del tipo|
|----------------|--------------|-----------------|
|[bool](bool.md)|Booleano||
|[byte](byte.md)|Senza segno, numerico, [integrale](integral-types-table.md)||
|[char](char.md)|Senza segno, numerico, [integrale](integral-types-table.md)||
|[decimal](decimal.md)|Numerico, [virgola mobile](floating-point-types-table.md)|M o m|
|[double](double.md)|Numerico, [virgola mobile](floating-point-types-table.md)|D o d|
|[enum](enum.md)|Enumerazione||
|[float](float.md)|Numerico, [virgola mobile](floating-point-types-table.md)|F o f|
|[int](int.md)|Con segno, numerico, [integrale](integral-types-table.md)||
|[long](long.md)|Con segno, numerico, [integrale](integral-types-table.md)|L o l|
|[sbyte](sbyte.md)|Con segno, numerico, [integrale](integral-types-table.md)||
|[short](short.md)|Con segno, numerico, [integrale](integral-types-table.md)||
|[struct](struct.md)|Struttura definita dall'utente||
|[uint](uint.md)|Senza segno, numerico, [integrale](integral-types-table.md)|U o u|
|[ulong](ulong.md)|Senza segno, numerico, [integrale](integral-types-table.md)|UL, Ul, uL, ul, LU, Lu, lU o lu|
|[ushort](ushort.md)|Senza segno, numerico, [integrale](integral-types-table.md)||

## <a name="remarks"></a>Osservazioni

Usare un suffisso del tipo per specificare un tipo di un valore letterale numerico. Ad esempio:

```csharp
decimal a = 0.1M;
```

Se un [valore letterale integer](~/_csharplang/spec/lexical-structure.md#integer-literals) non ha alcun suffisso, il tipo corrisponderà al primo dei tipi seguenti in cui il valore può essere rappresentato: `int`, `uint`, `long`, `ulong`.

Se un [valore letterale numerico reale](~/_csharplang/spec/lexical-structure.md#real-literals) non ha alcun suffisso, il tipo è `double`.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Tabella dei valori predefiniti](default-values-table.md)
- [Tipi valore](value-types.md)
- [Tabella di formattazione dei risultati numerici](formatting-numeric-results-table.md)
