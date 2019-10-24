---
title: parola chiave char C# -riferimento
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771792"
---
# <a name="char-c-reference"></a>char (C# riferimento)

La parola chiave `char` Type è un alias per il tipo di struttura <xref:System.Char?displayProperty=nameWithType> .NET che rappresenta un carattere Unicode UTF-16:

|Digitare|Intervallo|Dimensioni|Tipo .NET|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 a U+FFFF|16 bit|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>Valori letterali

Le costanti di tipo `char` possono essere scritte come valori letterali carattere, sequenze di escape esadecimali o rappresentazioni Unicode. È anche possibile eseguire il cast di un codice carattere integrale nel valore `char` corrispondente. Nell'esempio seguente i quattro elementi di una matrice di `char` vengono inizializzati con lo stesso carattere `X`:

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>Conversioni

Il tipo di `char` è convertibile in modo implicito nei tipi [integrali](../builtin-types/integral-numeric-types.md) seguenti: `ushort`, `int`, `uint`, `long` e `ulong`. È anche convertibile in modo implicito nei tipi numerici a [virgola mobile](../builtin-types/floating-point-numeric-types.md) predefiniti: `float`, `double` e `decimal`. È convertibile in modo esplicito in `sbyte`, `byte` e `short` i tipi integrali.

Non esistono conversioni implicite da altri tipi al tipo di `char`. Tuttavia, qualsiasi tipo numerico [integrale](../builtin-types/integral-numeric-types.md) o a [virgola mobile](../builtin-types/floating-point-numeric-types.md) è convertibile in modo esplicito in `char`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere la sezione [tipi integrali](~/_csharplang/spec/types.md#integral-types) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Parole chiave C#](./index.md)
- [Tabella dei tipi incorporati](./built-in-types-table.md)
- [Stringhe](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
