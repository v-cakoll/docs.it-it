---
title: Tabella dei tipi di valore - Riferimenti per C#
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 98829f30c2c25c0710cf3fe044359d3c7538fe76
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424044"
---
# <a name="value-types-table-c-reference"></a>Tabella dei tipi di valore (Riferimenti per C#)

La tabella seguente mostra i tipi valore di C#:

|Tipo valore|Category|Suffisso del tipo|
|----------------|--------------|-----------------|
|[bool](bool.md)|Booleano||
|[byte](../builtin-types/integral-numeric-types.md)|Senza segno, numerico, [integrale](../builtin-types/integral-numeric-types.md)||
|[char](char.md)|Senza segno, numerico, [integrale](../builtin-types/integral-numeric-types.md)
)||
|[decimal](decimal.md)|Numerico, [virgola mobile](floating-point-types-table.md)|M o m|
|[double](double.md)|Numerico, [virgola mobile](floating-point-types-table.md)|D o d|
|[enum](enum.md)|Enumerazione||
|[float](float.md)|Numerico, [virgola mobile](floating-point-types-table.md)|F o f|
|[int](../builtin-types/integral-numeric-types.md)|Con segno, numerico, [integrale](../builtin-types/integral-numeric-types.md)||
|[long](../builtin-types/integral-numeric-types.md)|Con segno, numerico, [integrale](../builtin-types/integral-numeric-types.md)|L o l|
|[sbyte](../builtin-types/integral-numeric-types.md)|Con segno, numerico, [integrale](../builtin-types/integral-numeric-types.md)||
|[short](../builtin-types/integral-numeric-types.md)|Con segno, numerico, [integrale](../builtin-types/integral-numeric-types.md)||
|[struct](struct.md)|Struttura definita dall'utente||
|[uint](../builtin-types/integral-numeric-types.md)|Senza segno, numerico, [integrale](../builtin-types/integral-numeric-types.md)|U o u|
|[ulong](../builtin-types/integral-numeric-types.md)|Senza segno, numerico, [integrale](../builtin-types/integral-numeric-types.md)|UL, Ul, uL, ul, LU, Lu, lU o lu|
|[ushort](../builtin-types/integral-numeric-types.md)|Senza segno, numerico, [integrale](../builtin-types/integral-numeric-types.md)||

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
