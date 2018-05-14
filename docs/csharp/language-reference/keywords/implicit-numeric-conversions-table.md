---
title: Tabella delle conversioni numeriche implicite (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 2d417a2020656f300de0517526742679388f262e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>Tabella delle conversioni numeriche implicite (Riferimenti per C#)
Nella tabella che segue sono illustrate le conversioni numeriche implicite predefinite. Le conversioni implicite possono avere luogo in numerose situazioni, ad esempio le chiamate di metodi e le istruzioni di assegnazione.  
  
|Da|A|  
|----------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`short`, `int`, `long`, `float`, `double` o `decimal`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`int`, `long`, `float`, `double` o `decimal`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`long`, `float`, `double` o `decimal`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`long`, `ulong`, `float`, `double` o `decimal`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`float`, `double`o `decimal`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`float`, `double`o `decimal`|  
  
## <a name="remarks"></a>Note  
  
-   Nella conversione da `int`, `uint`, `long` o `ulong` a `float` e da `long` o `ulong` a `double` può andare persa la precisione ma non la grandezza.  
  
-   Non esiste alcuna conversione implicita verso il tipo `char`.  
  
-   Non esiste alcuna conversione implicita tra tipi a virgola mobile e il tipo `decimal`.  
  
-   Un'espressione costante di tipo `int` può essere convertita in `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`, a condizione che il valore di tale espressione sia compreso nell'intervallo del tipo di destinazione.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
