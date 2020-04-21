---
title: Tipi numerici integrali - Riferimenti per C#
description: Informazioni sull'intervallo, le dimensioni di archiviazione e gli usi dei singoli tipi numerici integrali.
ms.date: 10/22/2019
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
ms.openlocfilehash: 51ea64065ea8422e5885022105545780bc916f06
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739014"
---
# <a name="integral-numeric-types--c-reference"></a>Tipi numerici integrali (Riferimenti per C#)

I *tipi numerici integrali* rappresentano numeri interi. Tutti i tipi numerici integrali sono [tipi di valore](value-types.md). Sono anche [tipi semplici](value-types.md#built-in-value-types) e possono essere inizializzati con valori [letterali](#integer-literals). Tutti i tipi numerici integrali supportano gli operatori [aritmetici,](../operators/arithmetic-operators.md) [logici bit per bit](../operators/bitwise-and-shift-operators.md), [di confronto](../operators/comparison-operators.md)e [di uguaglianza.](../operators/equality-operators.md)

## <a name="characteristics-of-the-integral-types"></a>Caratteristiche dei tipi integrali

C# supporta i tipi integrali predefiniti seguenti:

|Tipo/parola chiave C#|Range|Dimensione|Tipo .NET|
|----------|-----------|----------|-------------|
|`sbyte`|Da -128 a 127|Valore intero con segno a 8 bit|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|da 0 a 255|Intero senza segno a 8 bit|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|Da -32.768 a 32.767|Valore intero a 16 bit con segno|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|Da 0 a 65.535|Intero senza segno a 16 bit|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|Da -2.147.483.648 a 2.147.483.647|Valore intero a 32 bit con segno|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|Da 0 a 4.294.967.295|Intero senza segno a 32 bit|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|Da -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807|Valore intero a 64 bit con segno|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|Da 0 a 18.446.744.073.709.551.615|Intero senza segno a 64 bit|<xref:System.UInt64?displayProperty=nameWithType>|

Nella tabella precedente ogni tipo/parola chiave C# nella colonna più a sinistra è un alias per il tipo .NET corrispondente. Sono intercambiabili. Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:

```csharp
int a = 123;
System.Int32 b = 123;
```

Il valore predefinito di ogni tipo integrale è zero `0`. Ogni tipo integrale ha costanti `MinValue` e `MaxValue` che specificano il valore minimo e massimo del tipo.

Usare la struttura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> per rappresentare un intero con segno senza limiti inferiori o superiori.

## <a name="integer-literals"></a>Valori letterali Integer

I valori letterali integer possono essere

- *decimal*: senza prefisso
- *esadecimale*: con `0x` il `0X` prefisso o
- *binary*: `0b` con `0B` il prefisso o (disponibile in C , 7.0 e versioni successive)

Il codice seguente illustra un esempio di ogni codice:The following code demonstrates an example of each:

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

Nell'esempio precedente viene illustrato `_` anche l'utilizzo di come separatore di *cifre*, che è supportato a partire da C . È possibile utilizzare il separatore di cifre con tutti i tipi di valori letterali numerici.

Il tipo di un valore letterale integer è determinato dal relativo suffisso come segue:

- Se il valore letterale non ha alcun suffisso, il tipo è `int` `uint`il `long` `ulong`primo dei seguenti tipi in cui il relativo valore può essere rappresentato: , , , .
- Se il valore `U` letterale `u`è suffisso da o , il tipo è `uint`il `ulong`primo dei seguenti tipi in cui il relativo valore può essere rappresentato: , .
- Se il valore `L` letterale `l`è suffisso da o , il tipo è `long`il `ulong`primo dei seguenti tipi in cui il relativo valore può essere rappresentato: , .

  > [!NOTE]
  > È possibile utilizzare la `l` lettera minuscola come suffisso. Tuttavia, questo genera un `l` avviso del compilatore `1`perché la lettera può essere confusa con la cifra . Utilizzare `L` per chiarezza.

- Se il valore letterale `uL`è `ul` `LU`suffisso `lU`da `lu` `UL`, `Ul`, `ulong`, , , `Lu`, o , il tipo è .

Se il valore rappresentato da un valore letterale Integer supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione [CS1021](../../misc/cs1021.md).

Se il tipo determinato di `int` un valore letterale integer è e il valore rappresentato dal valore `sbyte` `byte`letterale è compreso nell'intervallo del tipo di destinazione, il valore può essere convertito in modo implicito `short`in , , `ushort`, , `uint`o `ulong`:

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

Come illustrato nell'esempio precedente, se il valore letterale non è compreso nell'intervallo del tipo di destinazione, si verifica un errore del compilatore [CS0031.](../../misc/cs0031.md)

È inoltre possibile utilizzare un cast per convertire il valore rappresentato da un valore letterale integer nel tipo diverso dal tipo determinato del valore letterale:

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a>Conversioni

È possibile convertire qualsiasi tipo numerico integrale in qualsiasi altro tipo numerico integrale. Se il tipo di destinazione può archiviare tutti i valori del tipo di origine, la conversione è implicita. In caso contrario, è necessario utilizzare [un'espressione cast](../operators/type-testing-and-cast.md#cast-expression) per eseguire una conversione esplicita. Per ulteriori informazioni, consultate [Conversioni numeriche predefinite.](numeric-conversions.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Tipi integrali](~/_csharplang/spec/types.md#integral-types)
- [Valori letterali Integer](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Tipi valore](value-types.md)
- [Tipi a virgola mobile](floating-point-numeric-types.md)
- [Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md)
- [Valori numerici in .NET](../../../standard/numerics.md)
