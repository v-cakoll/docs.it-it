---
title: Tipi numerici integrali - Riferimenti per C#
description: Informazioni sull'intervallo, le dimensioni di archiviazione e gli usi dei singoli tipi numerici integrali.
ms.date: 06/25/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: bde0b7cea52951cd72bde6cfd7d8f1c7dbcb8f46
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425596"
---
# <a name="integral-numeric-types--c-reference"></a>Tipi numerici integrali (Riferimenti per C#)

I **tipi numerici integrali** sono un subset dei **tipi semplici** e possono essere inizializzati con [*valori letterali*](#integral-literals). Tutti i tipi integrali sono anche tipi valore.

Tutti i tipi numerici integrali supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), [logici bit per bit](../operators/bitwise-and-shift-operators.md), [di confronto e di uguaglianza](../operators/equality-operators.md).

## <a name="sizes-and-ranges"></a>Dimensioni e intervalli

La tabella seguente elenca le dimensioni e gli intervalli dei tipi integrali:

|Tipo|Intervallo|Dimensione|  
|----------|-----------|----------|  
|`sbyte`|Da -128 a 127|Valore intero con segno a 8 bit|  
|`byte`|Da 0 a 255|Intero senza segno a 8 bit|  
|`short`|Da –32,768 a 32,767|Valore intero a 16 bit con segno|  
|`ushort`|Da 0 a 65.535|Intero senza segno a 16 bit|  
|`int`|da -2.147.483.648 a 2.147.483.647|Valore intero a 32 bit con segno|  
|`uint`|Da 0 a 4.294.967.295|Intero senza segno a 32 bit|  
|`long`|Da -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807|Numero intero con segno a 64 bit|  
|`ulong`|Da 0 a 18.446.744.073.709.551.615|Intero senza segno a 64 bit|  

Il valore predefinito di tutti i tipi integrali è `0`. Ogni tipo integrale ha costanti denominate `MinValue` e `MaxValue` per il valore minimo e massimo del tipo.

Usare la struttura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> per rappresentare un intero con segno senza limiti inferiori o superiori.

## <a name="integral-literals"></a>Valori letterali integrali

I valori letterali integrali possono essere specificati come *valori letterali decimali*, *valori letterali esadecimali* o *valori letterali binari*. Di seguito è illustrato un esempio di ognuno:

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

I valori letterali decimali non richiedono alcun prefisso. Il prefisso `x` o `X` indica un *valore letterale esadecimale*. Il prefisso `b` o `B` indica un *valore letterale binario*. La dichiarazione di `binaryLiteral` dimostra l'uso di `_` come *separatore di cifra*. Il separatore di cifra può essere usato con tutti i valori letterali numerici. I valori letterali binari e il separatore di cifra `_` sono supportati a partire da C# 7.0.

## <a name="literal-suffixes"></a>Suffissi letterali 

Il suffisso `l` o `L` specifica che il valore letterale integrale deve essere del tipo `long`. Il suffisso `ul` o `UL` specifica il tipo `ulong`. Se il suffisso `L` viene usato su un valore letterale maggiore di 9.223.372.036.854.775.807 (il valore massimo di `long`), il valore viene convertito nel tipo `ulong`. Se il valore rappresentato da un valore letterale Integer supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione [CS1021](../../misc/cs1021.md). 

> [!NOTE]
> È possibile usare la lettera minuscola "l" come suffisso. In questo caso, viene tuttavia generato un avviso del compilatore perché la lettera "l" viene facilmente confusa con la cifra "1". Per maggiore chiarezza, usare la lettera "L".

## <a name="type-of-an-integral-literal"></a>Tipo di un valore letterale integrale

Se un valore letterale integrale non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:

1. `int`
1. `uint`
1. `long`
1. `ulong`

È possibile convertire un valore letterale integrale in un tipo con un intervallo più piccolo rispetto a quello predefinito eseguendo un'assegnazione o un cast:

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

È possibile convertire un valore letterale integrale in un tipo con un intervallo più grande rispetto a quello predefinito eseguendo un'assegnazione, un cast o inserendo un suffisso nel valore letterale:

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a>Conversioni

Viene eseguita una conversione implicita (detta *conversione verso un tipo di dati più grande*) tra due tipi integrali in cui il tipo di destinazione può archiviare tutti i valori del tipo di origine. Ad esempio, è presente una conversione implicita da `int` a `long` perché l'intervallo di valori `int` è un subset corretto di `long`. Sono presenti conversioni implicite da un tipo integrale senza segno più piccolo a un tipo integrale con segno più grande. È presente una conversione implicita anche da qualsiasi tipo integrale a qualsiasi tipo a virgola mobile.  Non vi è conversione implicita da qualsiasi tipo integrale con segno a qualsiasi tipo integrale senza segno.

È necessario usare un cast esplicito per convertire un tipo integrale in un altro tipo integrale quando non è definita una conversione implicita dal tipo di origine al tipo di destinazione. Questa operazione è definita *conversione verso un tipo di dati più piccolo*. Il caso esplicito è necessario perché la conversione può comportare una perdita di dati.

## <a name="see-also"></a>Vedere anche

- [Specifiche del linguaggio C# - Tipi integrali](~/_csharplang/spec/types.md#integral-types)
- [Riferimenti per C#](../index.md)
- [Tabella dei tipi a virgola mobile](../keywords/floating-point-types-table.md)
- [Tabella dei valori predefiniti](../keywords/default-values-table.md)
- [Tabella di formattazione dei risultati numerici](../keywords/formatting-numeric-results-table.md)
- [Tabella dei tipi incorporati](../keywords/built-in-types-table.md)
- [Dati numerici in .NET](../../../standard/numerics.md)
