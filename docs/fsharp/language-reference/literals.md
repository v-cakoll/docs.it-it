---
title: Valori letterali (F#)
description: 'Informazioni sui tipi di valore letterale in F # linguaggio di programmazione.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 961d6a10122c5d5c691d394efa8d2b7b31a80453
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="literals"></a>Valori letterali

> [!NOTE]
I collegamenti di riferimento API in questo articolo si passerà a MSDN (per ora).

In questo argomento fornisce una tabella in cui viene illustrato come specificare il tipo di un valore letterale in F #.

## <a name="literal-types"></a>Tipi di valori letterali
La tabella seguente illustra i tipi di valore letterale in F #. Caratteri che rappresentano cifre in notazione esadecimale non fanno distinzione; caratteri che identificano il tipo di maiuscole e minuscole.

|Tipo|Descrizione|Prefisso o suffisso|Esempi|
|----|-----------|----------------|--------|
|sbyte|Intero con segno a 8 bit|y|`86y`<br /><br />`0b00000101y`|
|byte|Numero naturale senza segno a 8 bit|UY|`86uy`<br /><br />`0b00000101uy`|
|int16|Intero con segno a 16 bit|s|`86s`|
|uint16|numero di naturale senza segno a 16 bit|us|`86us`|
|int<br /><br />int32|Intero con segno a 32 bit|l o nessuno|`86`<br /><br />`86l`|
|uint<br /><br />uint32|Numero naturale senza segno a 32 bit|u o ul|`86u`<br /><br />`86ul`|
|unativeint|puntatore nativo come un numero naturale senza segno|Annulla|`0x00002D3Fun`|
|int64|Intero con segno a 64 bit|L|`86L`|
|uint64|numero di naturale senza segno a 64 bit|UL|`86UL`|
|float32 singolo,|numero a virgola mobile a 32 bit|F o f|`4.14F` o `4.14f`|
|||LF|`0x00000000lf`|
|float; Double|numero a virgola mobile a 64 bit|none|`4.14` o `2.3E+32` o `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|bigint|numero intero non è limitato a una rappresentazione a 64 bit|I|`9999999999999999999999999999I`|
|decimal|numero frazionario rappresentato come un punto fisso o un numero razionale|M o m|`0.7833M` o `0.7833m`|
|Char|Carattere Unicode|none|`'a'`|
|Stringa|Stringa Unicode|none|`"text\n"`<br /><br />oppure<br /><br />`@"c:\filename"`<br /><br />oppure<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />oppure<br /><br />`"string1" + "string2"`<br /><br />Vedere anche [stringhe](Strings.md).|
|byte|Carattere ASCII|B|`'a'B`|
|byte[]|Stringa ASCII|B|`"text"B`|
|String o byte]|stringa verbatim|prefisso @|`@"\\server\share"` (Unicode)<br /><br />`@"\\server\share"B` (ASCII)|

## <a name="remarks"></a>Note
Le stringhe Unicode possono contenere codifiche esplicite che è possibile specificare utilizzando `\u` seguito da un codice esadecimale a 16 bit o codifiche UTF-32 che è possibile specificare utilizzando `\U` seguito da un codice esadecimale a 32 bit che rappresenta un Unicode coppia di surrogati.

A partire da F # 3.1, è possibile utilizzare il `+` accedere per combinare i valori letterali stringa. È inoltre possibile utilizzare il bit per bit o (`|||`) (operatore) per combinare i flag di enumerazione. Ad esempio, il codice seguente è valido in F # 3.1:

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

Non è consentito l'uso di altri operatori bit per bit.


## <a name="named-literals"></a>Valori letterali denominati
I valori che devono essere costanti possono essere contrassegnati con il [letterale](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attributo. Questo attributo ha l'effetto della causa di un valore essere compilata come una costante.

Nelle espressioni dei criteri, gli identificatori che iniziano con caratteri minuscoli vengono sempre considerati come variabili di essere vincolato, anziché come valori letterali, pertanto è in genere consigliabile utilizzare le lettere maiuscole iniziali quando si definiscono i valori letterali.

## <a name="integers-in-other-bases"></a>Numeri interi In altra base

È inoltre possibile specificare interi con segno a 32 bit binaria, ottale o esadecimale con un `0x`, `0o` o `0b` prefisso rispettivamente.

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>Caratteri di sottolineatura nei valori letterali numerici

A partire da F # 4.1, è possibile separare cifre con il carattere di sottolineatura (`_`).

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a>Vedere anche

[Classe Core. LiteralAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
