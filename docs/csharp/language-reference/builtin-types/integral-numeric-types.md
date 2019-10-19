---
title: Tipi numerici integrali - Riferimenti per C#
description: Informazioni sull'intervallo, le dimensioni di archiviazione e gli usi dei singoli tipi numerici integrali.
ms.date: 10/18/2019
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
ms.openlocfilehash: 3d4f3164d67a000123417619f3be6be455d5ab87
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579188"
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

- Se il valore letterale non ha alcun suffisso, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `int`, `uint`, `long` `ulong`.
- Se il valore letterale è suffisso per `U` o `u`, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `uint`, `ulong`.
- Se il valore letterale è suffisso per `L` o `l`, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `long`, `ulong`.

  > [!NOTE]
  > È possibile usare la lettera minuscola `l` come suffisso. Viene tuttavia generato un avviso del compilatore perché la lettera `l` può essere confusa con la cifra `1`. Per maggiore chiarezza, utilizzare `L`.

- Se il valore letterale è suffisso in `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` o `lu`, il tipo è `ulong`.

Se il valore rappresentato da un valore letterale Integer supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione [CS1021](../../misc/cs1021.md).

Il valore rappresentato da un valore letterale integer può essere convertito in modo implicito in un tipo con un intervallo inferiore al tipo determinato del valore letterale. Questo è possibile quando il valore è compreso nell'intervallo del tipo di destinazione:

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

Viene eseguita una conversione implicita (detta *conversione verso un tipo di dati più grande*) tra due tipi integrali in cui il tipo di destinazione può archiviare tutti i valori del tipo di origine. Ad esempio, è presente una conversione implicita da `int` a `long` perché l'intervallo di valori `int` è un subset corretto di `long`. Sono presenti conversioni implicite da un tipo integrale senza segno più piccolo a un tipo integrale con segno più grande. È presente una conversione implicita anche da qualsiasi tipo integrale a qualsiasi tipo a virgola mobile.  Non vi è conversione implicita da qualsiasi tipo integrale con segno a qualsiasi tipo integrale senza segno.

È necessario usare un cast esplicito per convertire un tipo integrale in un altro tipo integrale quando non è definita una conversione implicita dal tipo di origine al tipo di destinazione. Questa operazione è definita *conversione verso un tipo di dati più piccolo*. Il caso esplicito è necessario perché la conversione può comportare una perdita di dati.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Tipi integrali](~/_csharplang/spec/types.md#integral-types)
- [Valori letterali integer](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Tipi a virgola mobile](floating-point-numeric-types.md)
- [Tabella dei valori predefiniti](../keywords/default-values-table.md)
- [Tabella di formattazione dei risultati numerici](../keywords/formatting-numeric-results-table.md)
- [Tabella dei tipi incorporati](../keywords/built-in-types-table.md)
- [Dati numerici in .NET](../../../standard/numerics.md)
