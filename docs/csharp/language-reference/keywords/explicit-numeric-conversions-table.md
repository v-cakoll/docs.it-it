---
title: Tabella delle conversioni numeriche esplicite (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 7363df3e4b2449924222745de409fd68349b93de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="explicit-numeric-conversions-table-c-reference"></a>Tabella delle conversioni numeriche esplicite (Riferimenti per C#)
La conversione numerica esplicita viene usata per convertire qualsiasi tipo numerico in qualsiasi altro tipo numerico, per il quale non c'è alcuna conversione implicita, usando un'espressione cast. La tabella seguente illustra queste conversioni.  
  
 Per altre informazioni sulle conversioni, vedere [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
|Da|A|  
|----------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`byte`, `ushort`, `uint`, `ulong` o `char`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`Sbyte` o `char`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` o `char`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`sbyte`, `byte`, `short` o `char`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` o `char`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`sbyte`, `byte`, `short`, `ushort`, `int` o `char`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` o `char`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` o `char`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`sbyte`, `byte`o `short`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` o `decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `decimal`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `double`|  
  
## <a name="remarks"></a>Note  
  
-   La conversione numerica esplicita può causare una perdita nella precisione o comportare la generazione di eccezioni.  
  
-   Quando si esegue una conversione da un valore `decimal` a un tipo integrale, il valore viene arrotondato per difetto al valore integrale più vicino. Se il valore integrale risultante non rientra nell'intervallo del tipo di destinazione, viene generata un'eccezione <xref:System.OverflowException>.  
  
-   Quando si esegue una conversione da un valore `double` o `float` a un tipo integrale, il valore viene troncato. Se il valore integrale risultante non rientra nell'intervallo del valore di destinazione, il risultato dipende dal contesto di controllo dell'overflow. In un contesto controllato (checked) viene generata un'eccezione `OverflowException`, mentre in un contesto non controllato (unckecked) il risultato è un valore non specificato del tipo di destinazione.  
  
-   Per una conversione da `double` a `float`, il valore `double` viene arrotondato al valore `float` più vicino. Se il valore `double` è troppo piccolo o troppo grande per essere contenuto nel tipo di destinazione, il risultato sarà zero o infinito.  
  
-   Quando si esegue una conversione da `float` o `double` a `decimal`, il valore di origine viene convertito nella rappresentazione `decimal` e arrotondato al numero più vicino successivo alla ventottesima posizione decimale, se necessario. A seconda dell'entità del valore di origine, è possibile che si verifichi uno dei risultati seguenti:  
  
    -   Se il valore di origine è troppo piccolo per essere rappresentato come `decimal`, il risultato diventa zero.  
  
    -   Se il valore di origine è NaN (non un numero), infinito o troppo grande per essere rappresentato come `decimal`, viene generata un'eccezione `OverflowException`.  
  
-   Quando si esegue una conversione da `decimal` a `float` o `double`, il valore `decimal` viene arrotondato al valore `double` o `float` più vicino.  
  
 Per altre informazioni sulla conversione esplicita, vedere Explicit nella specifica del linguaggio C#. Per altre informazioni su come accedere alla specifica, vedere [Specifica del linguaggio C#](../../../csharp/language-reference/language-specification/index.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [Operatore ()](../../../csharp/language-reference/operators/invocation-operator.md)  
 [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
