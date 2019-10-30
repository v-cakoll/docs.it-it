---
title: Valori letterali
description: Informazioni sui tipi letterali nel linguaggio F# di programmazione.
ms.date: 06/28/2019
ms.openlocfilehash: 9792a24ac28eb402e35e78574cd6a2bf9526734d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041037"
---
# <a name="literals"></a>Valori letterali

> [!NOTE]
> I collegamenti di riferimento all'API in questo articolo ti porteranno a MSDN (per il momento).

In questo argomento viene fornita una tabella in cui viene illustrato come specificare il tipo di F#un valore letterale in.

## <a name="literal-types"></a>Tipi di valori letterali

Nella tabella seguente vengono illustrati i tipi F#di valore letterale in. I caratteri che rappresentano le cifre nella notazione esadecimale non fanno distinzione tra maiuscole e minuscole. i caratteri che identificano il tipo fanno distinzione tra maiuscole e minuscole.

|Digitare|Descrizione|Suffisso o prefisso|Esempi|
|----|-----------|----------------|--------|
|sbyte|Signed Integer a 8 bit|s|`86y`<br /><br />`0b00000101y`|
|byte|numero naturale senza segno a 8 bit|uy|`86uy`<br /><br />`0b00000101uy`|
|int16|Signed Integer a 16 bit|s|`86s`|
|uint16|numero naturale senza segno a 16 bit|us|`86us`|
|int<br /><br />int32|Signed Integer a 32 bit|l o None|`86`<br /><br />`86l`|
|uint<br /><br />uint32|numero naturale senza segno a 32 bit|u o UL|`86u`<br /><br />`86ul`|
|nativeint|puntatore nativo a un numero naturale con segno|n|`123n`|
|unativeint|puntatore nativo come numero naturale senza segno|non|`0x00002D3Fun`|
|int64|Signed Integer a 64 bit|L|`86L`|
|uint64|numero naturale senza segno a 64 bit|UL|`86UL`|
|singolo, float32|numero a virgola mobile a 32 bit|F o f|`4.14F` o `4.14f`|
|||Se|`0x00000000lf`|
|float doppio|numero a virgola mobile a 64 bit|none|`4.14` o `2.3E+32` o `2.3e+32`|
|||Se|`0x0000000000000000LF`|
|bigint|Integer non limitato alla rappresentazione a 64 bit|I|`9999999999999999999999999999I`|
|decimal|numero frazionario rappresentato come punto fisso o numero razionale|M o m|`0.7833M` o `0.7833m`|
|Char|Carattere Unicode|none|`'a'` o `'\u0061'`|
|Stringa|Stringa Unicode|none|`"text\n"`<br /><br />Oppure<br /><br />`@"c:\filename"`<br /><br />Oppure<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />Oppure<br /><br />`"string1" + "string2"`<br /><br />Vedere anche [stringhe](Strings.md).|
|byte|Carattere ASCII|B|`'a'B`|
|byte[]|Stringa ASCII|B|`"text"B`|
|String o byte []|stringa Verbatim|@ prefix|`@"\\server\share"` (Unicode)<br /><br />`@"\\server\share"B` (ASCII)|

## <a name="named-literals"></a>Valori letterali denominati

I valori destinati a essere costanti possono essere contrassegnati con l'attributo [letterale](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) . Questo attributo ha l'effetto di causare la compilazione di un valore come costante.

Nelle espressioni di criteri di ricerca, gli identificatori che iniziano con caratteri minuscoli vengono sempre considerati come variabili da associare, anziché come valori letterali, pertanto è consigliabile utilizzare in genere maiuscole iniziali quando si definiscono i valori letterali.

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a>Note

Le stringhe Unicode possono contenere codifiche esplicite che è possibile specificare usando `\u` seguito da un codice esadecimale a 16 bit (0000-FFFF) o da codifiche UTF-32 che è possibile specificare usando `\U` seguito da un codice esadecimale a 32 bit che rappresenta qualsiasi Unicode punto di codice (00000000-0010FFFF).

L'utilizzo di altri operatori bit per bit diversi da `|||` non è consentito.

## <a name="integers-in-other-bases"></a>Numeri interi in altre basi

Gli interi con segno a 32 bit possono essere specificati anche in formato esadecimale, ottale o binario usando rispettivamente un prefisso `0x`, `0o` o `0b`.

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>Caratteri di sottolineatura nei valori letterali numerici

È possibile separare le cifre con il carattere di sottolineatura (`_`).

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a>Vedere anche

- [Classe Core. LiteralAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
