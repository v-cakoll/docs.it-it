---
title: Tabella delle conversioni numeriche esplicite (Riferimenti per C#)
ms.date: 09/06/2018
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 948961d19518343c1f8ee14cd48dc33ec72cf23d
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2018
ms.locfileid: "49478926"
---
# <a name="explicit-numeric-conversions-table-c-reference"></a>Tabella delle conversioni numeriche esplicite (Riferimenti per C#)

Nella tabella seguente sono illustrate le conversioni esplicite predefinite tra i tipi numerici .NET in cui non è presente alcuna [conversione implicita](implicit-numeric-conversions-table.md).

|Da|A|  
|----------|--------|  
|[sbyte](sbyte.md)|`byte`, `ushort`, `uint`, `ulong` o `char`|  
|[byte](byte.md)|`sbyte` o `char`|  
|[short](short.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` o `char`|  
|[ushort](ushort.md)|`sbyte`, `byte`, `short` o `char`|  
|[int](int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` o `char`|  
|[uint](uint.md)|`sbyte`, `byte`, `short`, `ushort`, `int` o `char`|  
|[long](long.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` o `char`|  
|[ulong](ulong.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` o `char`|  
|[char](char.md)|`sbyte`, `byte`o `short`|  
|[float](float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` o `decimal`|  
|[double](double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `decimal`|  
|[decimal](decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `double`|  
  
## <a name="remarks"></a>Note  
  
- La conversione numerica esplicita può causare una perdita nella precisione o comportare la generazione di un'eccezione, generalmente un'<xref:System.OverflowException>.  

- Quando si converte un valore di tipo integrale a un altro tipo integrale, il risultato dipende dal [contesto di controllo](checked-and-unchecked.md) dell'overflow. In un contesto controllato, la conversione ha esito positivo se il valore di origine è compreso nell'intervallo del tipo di destinazione. In caso contrario, verrà generata un'eccezione <xref:System.OverflowException>. In un contesto non controllato, la conversione ha sempre esito positivo e procede nel modo seguente:

  - Se il tipo di origine è maggiore del tipo di destinazione, il valore di origine viene troncato rimuovendo i relativi "extra" bit più rilevanti. Il risultato viene quindi trattato come un valore del tipo di destinazione.

  - Se il tipo di origine è inferiore al tipo di destinazione, il valore di origine ha estensione firma o estensione zero in modo da avere le stesse dimensioni del tipo di destinazione. L'estensione firma viene usata se il tipo di origine dispone della firma; l'estensione zero viene usata se il tipo di origine è privo di firma. Il risultato viene quindi trattato come un valore del tipo di destinazione.

  - Se il tipo di origine ha le stesse dimensioni del tipo di destinazione, il valore di origine viene considerato un valore del tipo di destinazione.
  
- Quando si esegue una conversione da un valore `decimal` a un tipo integrale, il valore viene arrotondato per difetto al valore integrale più vicino. Se il valore integrale risultante non rientra nell'intervallo del tipo di destinazione, viene generata un'eccezione <xref:System.OverflowException>.  
  
- Quando si esegue una conversione da un valore `double` o `float` a un tipo integrale, il valore viene arrotondato per difetto al valore integrale più vicino. Se il valore integrale risultante non rientra nell'intervallo del tipo di destinazione, il risultato dipende dal [contesto di controllo](checked-and-unchecked.md) dell'overflow. In un contesto controllato (checked) viene generata un'eccezione <xref:System.OverflowException>, mentre in un contesto non controllato (unckecked) il risultato è un valore non specificato del tipo di destinazione.  
  
- Per una conversione da `double` a `float`, il valore `double` viene arrotondato al valore `float` più vicino. Se il valore `double` è troppo piccolo o troppo grande per essere contenuto nel tipo di destinazione, il risultato sarà zero o infinito.  
  
- Quando si esegue una conversione da `float` o `double` a `decimal`, il valore di origine viene convertito nella rappresentazione `decimal` e arrotondato al numero più vicino successivo alla ventottesima posizione decimale, se necessario. A seconda dell'entità del valore di origine, è possibile che si verifichi uno dei risultati seguenti:  

  - Se il valore di origine è troppo piccolo per essere rappresentato come `decimal`, il risultato diventa zero.  

  - Se il valore di origine è NaN (non un numero), infinito o troppo grande per essere rappresentato come `decimal`, viene generata un'eccezione <xref:System.OverflowException>.  
  
- Quando si esegue una conversione da `decimal` a `float` o `double`, il valore `decimal` viene arrotondato al valore `double` o `float` più vicino.  
  
 Per altre informazioni sulle conversioni esplicite, vedere la sezione [conversioni esplicite](~/_csharplang/spec/conversions.md#explicit-conversions) della [specifica del linguaggio C#](../language-specification/index.md).
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Cast e conversioni di tipi](../../programming-guide/types/casting-and-type-conversions.md)
- [Operatore ()](../operators/invocation-operator.md)
- [Tabella dei tipi integrali](integral-types-table.md)
- [Tabella dei tipi a virgola mobile](floating-point-types-table.md)
- [Tabella dei tipi incorporati](built-in-types-table.md)
- [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md)
