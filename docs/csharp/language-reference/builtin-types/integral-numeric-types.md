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
ms.openlocfilehash: 2fb4d7185ac85b29f2cc2d2e7a29e192f91a0868
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980145"
---
# <a name="integral-numeric-types--c-reference"></a>Tipi numerici integrali (Riferimenti per C#)

I **tipi numerici integrali** sono un subset dei **tipi semplici** e possono essere inizializzati con [*valori letterali*](#integer-literals). Tutti i tipi integrali sono anche tipi valore. Tutti i tipi numerici integrali supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), [logici bit per bit](../operators/bitwise-and-shift-operators.md), di [confronto](../operators/comparison-operators.md)e di [uguaglianza](../operators/equality-operators.md) .

## <a name="characteristics-of-the-integral-types"></a>Caratteristiche dei tipi integrali

C# supporta i tipi integrali predefiniti seguenti:

|Tipo/parola chiave C#|Intervallo|Dimensioni|Tipo .NET|
|----------|-----------|----------|-------------|
|`sbyte`|Da -128 a 127|Valore intero con segno a 8 bit|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|Da 0 a 255|Intero senza segno a 8 bit|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|Da –32,768 a 32,767|Valore intero a 16 bit con segno|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|Da 0 a 65.535|Intero senza segno a 16 bit|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|da -2.147.483.648 a 2.147.483.647|Valore intero a 32 bit con segno|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|Da 0 a 4.294.967.295|Intero senza segno a 32 bit|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|Da -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807|Numero intero con segno a 64 bit|<xref:System.Int64?displayProperty=nameWithType>|
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

- *Decimal*: senza prefisso
- *esadecimale*: con il prefisso `0x` o `0X`
- *Binary*: con il prefisso `0b` o `0B` (disponibile in C# 7,0 e versioni successive)

Il codice seguente illustra un esempio di ogni:

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

Nell'esempio precedente viene inoltre illustrato l'utilizzo di `_` come *separatore di cifre*, supportato a partire C# da 7,0. È possibile usare il separatore di cifre con tutti i tipi di valori letterali numerici.

Il tipo di un valore letterale integer è determinato dal suffisso, come indicato di seguito:

- Se il valore letterale non ha alcun suffisso, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `int`, `uint`, `long``ulong`.
- Se il valore letterale è suffisso per `U` o `u`, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `uint`, `ulong`.
- Se il valore letterale è suffisso per `L` o `l`, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `long`, `ulong`.

  > [!NOTE]
  > È possibile usare la lettera minuscola `l` come suffisso. Viene tuttavia generato un avviso del compilatore perché la lettera `l` può essere confusa con la cifra `1`. Per maggiore chiarezza, utilizzare `L`.

- Se il valore letterale è suffisso in `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`o `lu`, il tipo è `ulong`.

Se il valore rappresentato da un valore letterale Integer supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione [CS1021](../../misc/cs1021.md).

Se il tipo determinato di un valore letterale integer è `int` e il valore rappresentato dal valore letterale è compreso nell'intervallo del tipo di destinazione, il valore può essere convertito in modo implicito in `sbyte`, `byte`, `short`, `ushort`, `uint`o `ulong`:

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

Come illustrato nell'esempio precedente, se il valore del valore letterale non è compreso nell'intervallo del tipo di destinazione, si verifica un errore del compilatore [CS0031](../../misc/cs0031.md) .

È anche possibile usare un cast per convertire il valore rappresentato da un valore letterale integer nel tipo diverso dal tipo determinato del valore letterale:

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a>Conversioni

È possibile convertire qualsiasi tipo numerico integrale in qualsiasi altro tipo numerico integrale. Se il tipo di destinazione può archiviare tutti i valori del tipo di origine, la conversione è implicita. In caso contrario, è necessario usare l' [operatore cast `()`](../operators/type-testing-and-cast.md#cast-operator-) per richiamare una conversione esplicita. Per altre informazioni, vedere [conversioni numeriche predefinite](numeric-conversions.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Tipi integrali](~/_csharplang/spec/types.md#integral-types)
- [Valori letterali integer](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Tabella dei tipi incorporati](../keywords/built-in-types-table.md)
- [Tipi a virgola mobile](floating-point-numeric-types.md)
- [Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md)
- [Dati numerici in .NET](../../../standard/numerics.md)
