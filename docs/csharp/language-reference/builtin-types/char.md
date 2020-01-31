---
title: tipo char- C# riferimento
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 3952e9e30706a8cd362ef248955918de5dacf4a3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787812"
---
# <a name="char-c-reference"></a>char (C# riferimento)

La parola chiave `char` Type è un alias per il tipo di struttura <xref:System.Char?displayProperty=nameWithType> .NET che rappresenta un carattere Unicode UTF-16.

|Tipo di|Intervallo|Dimensioni|Tipo .NET|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 a U+FFFF|16 bit|<xref:System.Char?displayProperty=nameWithType>|

Il valore predefinito del tipo di `char` è `\0`, ovvero U + 0000.

Il tipo [stringa](reference-types.md#the-string-type) rappresenta il testo come sequenza di valori `char`.

## <a name="literals"></a>Valori letterali

È possibile specificare un valore `char` con:

- valore letterale carattere.
- sequenza di escape Unicode, che è `\u` seguita dalla rappresentazione esadecimale a quattro simboli di un codice carattere.
- sequenza di escape esadecimale, `\x` seguita dalla rappresentazione esadecimale di un codice carattere.

[!code-csharp-interactive[char literals](~/samples/csharp/language-reference/builtin-types/CharType.cs#Literals)]

Come illustrato nell'esempio precedente, è anche possibile eseguire il cast del valore di un codice carattere nel valore `char` corrispondente.

> [!NOTE]
> Nel caso di una sequenza di escape Unicode, è necessario specificare tutte e quattro le cifre esadecimali. Ovvero, `\u006A` è una sequenza di escape valida, mentre `\u06A` e `\u6A` non sono validi.
>
> Nel caso di una sequenza di escape esadecimale, è possibile omettere gli zeri iniziali. Ovvero le sequenze di escape `\x006A`, `\x06A`e `\x6A` sono valide e corrispondono allo stesso carattere.

## <a name="conversions"></a>Conversioni

Il tipo di `char` è convertibile in modo implicito nei tipi [integrali](integral-numeric-types.md) seguenti: `ushort`, `int`, `uint`, `long`e `ulong`. È anche convertibile in modo implicito nei tipi numerici a [virgola mobile](floating-point-numeric-types.md) predefiniti: `float`, `double`e `decimal`. È convertibile in modo esplicito in `sbyte`, `byte`e `short` i tipi integrali.

Non esistono conversioni implicite da altri tipi al tipo di `char`. Tuttavia, qualsiasi tipo numerico [integrale](integral-numeric-types.md) o a [virgola mobile](floating-point-numeric-types.md) è convertibile in modo esplicito in `char`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere la sezione [tipi integrali](~/_csharplang/spec/types.md#integral-types) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Tabella dei tipi incorporati](../keywords/built-in-types-table.md)
- [Stringhe](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
