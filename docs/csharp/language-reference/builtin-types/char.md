---
title: Tipo di char - Riferimenti per C
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: a07cae6e607bb6cda965240c669c655207632298
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739059"
---
# <a name="char-c-reference"></a>char (riferimenti per C

La `char` parola chiave type è <xref:System.Char?displayProperty=nameWithType> un alias per il tipo di struttura .NET che rappresenta un carattere Unicode UTF-16.

|Type|Range|Dimensione|Tipo .NET|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 a U+FFFF|16 bit|<xref:System.Char?displayProperty=nameWithType>|

Il valore predefinito `char` del `\0`tipo è , ovvero U.

Il tipo [string](reference-types.md#the-string-type) rappresenta il `char` testo come una sequenza di valori.

## <a name="literals"></a>Valori letterali

È possibile `char` specificare un valore con:You can specify a value with:

- un valore letterale carattere.
- una sequenza di `\u` escape Unicode, seguita dalla rappresentazione esadecimale a quattro simboli di un codice di carattere.
- una sequenza di escape esadecimale, `\x` seguita dalla rappresentazione esadecimale di un codice di carattere.

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

Come illustrato nell'esempio precedente, è anche possibile eseguire il `char` cast del valore di un codice carattere nel valore corrispondente.

> [!NOTE]
> Nel caso di una sequenza di escape Unicode, è necessario specificare tutte e quattro le cifre esadecimali. Ovvero, `\u006A` è una sequenza `\u06A` di `\u6A` escape valida, mentre e non sono validi.
>
> Nel caso di una sequenza di escape esadecimale, è possibile omettere gli zeri iniziali. Ovvero, le `\x006A` `\x06A`sequenze `\x6A` , e escape sono valide e corrispondono allo stesso carattere.

## <a name="conversions"></a>Conversioni

Il `char` tipo è convertibile in modo implicito `uint` `long`nei `ulong`seguenti tipi [integrali:](integral-numeric-types.md) `ushort`, `int`, , , e . È inoltre convertibile in modo implicito nei tipi numerici `double`a `decimal` [virgola mobile](floating-point-numeric-types.md) incorporati: `float`, , e . È convertibile in `sbyte`modo `byte`esplicito in tipi , e `short` integrali.

Non esistono conversioni implicite da `char` altri tipi al tipo. Tuttavia, qualsiasi tipo numerico [integrale](integral-numeric-types.md) o `char`a virgola [mobile](floating-point-numeric-types.md) è convertibile in modo esplicito in .

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere la sezione [relativa ai tipi integrali](~/_csharplang/spec/types.md#integral-types) della specifica del [linguaggio C.](~/_csharplang/spec/introduction.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Tipi valore](value-types.md)
- [Stringhe](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [Codifica dei caratteri in .NET](../../../standard/base-types/character-encoding-introduction.md)
