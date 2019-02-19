---
title: Tabella delle conversioni numeriche implicite - Riferimenti per C#
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 703f60f48e1e569e0ffcab66ff7ccc91d4a49514
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2019
ms.locfileid: "56093554"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>Tabella delle conversioni numeriche implicite (Riferimenti per C#)

Nella tabella che segue sono illustrate le conversioni implicite predefinite tra i tipi numerici .NET.
  
|Da|A|  
|----------|--------|  
|[sbyte](sbyte.md)|`short`, `int`, `long`, `float`, `double` o `decimal`|  
|[byte](byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[char](char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[short](short.md)|`int`, `long`, `float`, `double` o `decimal`|  
|[ushort](ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[int](int.md)|`long`, `float`, `double` o `decimal`|  
|[uint](uint.md)|`long`, `ulong`, `float`, `double` o `decimal`|  
|[long](long.md)|`float`, `double`o `decimal`|  
|[ulong](ulong.md)|`float`, `double`o `decimal`|  
|[float](float.md)|`double`|  
  
## <a name="remarks"></a>Osservazioni  

- Qualunque [tipo integrale](integral-types-table.md) è implicitamente convertibile in qualunque [tipo a virgola mobile](floating-point-types-table.md).

- Nella conversione da `int`, `uint`, `long` o `ulong` a `float` e da `long` o `ulong` a `double` può andare persa la precisione ma non la grandezza.  
  
- Non esiste alcuna conversione implicita verso i tipi `char`, `byte` e `sbyte`.  

- Non esiste alcuna conversione implicita dai tipi `double` e `decimal`.
  
- Non esiste alcuna conversione implicita tra il tipo `decimal` e i tipi `float` o `double`.  
  
- Un valore di un'espressione costante di tipo `int` (ad esempio, un valore rappresentato da un valore letterale intero) possono essere convertiti in `sbyte`, `byte`, `short`, `ushort`, `uint`, o `ulong`, purché rientri all'interno dell'intervallo del tipo di destinazione:

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

Per altre informazioni sulle conversioni implicite, vedere la sezione [conversioni implicite](~/_csharplang/spec/conversions.md#implicit-conversions) della [specifica del linguaggio C#](../language-specification/index.md).
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Tabella dei tipi integrali](integral-types-table.md)
- [Tabella dei tipi a virgola mobile](floating-point-types-table.md)
- [Tabella dei tipi incorporati](built-in-types-table.md)
- [Tabella delle conversioni numeriche esplicite](explicit-numeric-conversions-table.md)
- [Cast e conversioni di tipi](../../programming-guide/types/casting-and-type-conversions.md)
