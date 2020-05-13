---
title: tipo char-riferimenti per C#
ms.date: 05/11/2020
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: f771626e9777deab30e798559d847615d6124e6d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205785"
---
# <a name="char-c-reference"></a>char (riferimenti per C#)

La `char` parola chiave Type è un alias per il <xref:System.Char?displayProperty=nameWithType> tipo di struttura .NET che rappresenta un carattere Unicode UTF-16.

|Type|Range|Dimensione|Tipo .NET|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 a U+FFFF|16 bit|<xref:System.Char?displayProperty=nameWithType>|

Il valore predefinito del `char` tipo è `\0` , ovvero U + 0000.

Il `char` tipo supporta operatori di [confronto](../operators/comparison-operators.md), [uguaglianza](../operators/equality-operators.md), [incremento](../operators/arithmetic-operators.md#increment-operator-)e [decremento](../operators/arithmetic-operators.md#decrement-operator---) . Inoltre, per gli `char` operandi, gli operatori [logici](../operators/bitwise-and-shift-operators.md) [aritmetici](../operators/arithmetic-operators.md) e bit per bit eseguono un'operazione sui codici carattere corrispondenti e producono il risultato del `int` tipo.

Il tipo [stringa](reference-types.md#the-string-type) rappresenta il testo come una sequenza di `char` valori.

## <a name="literals"></a>Valori letterali

È possibile specificare un `char` valore con:

- valore letterale carattere.
- sequenza di escape Unicode, `\u` seguita dalla rappresentazione esadecimale a quattro simboli di un codice carattere.
- sequenza di escape esadecimale, `\x` seguita dalla rappresentazione esadecimale di un codice carattere.

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

Come illustrato nell'esempio precedente, è anche possibile eseguire il cast del valore di un codice carattere nel `char` valore corrispondente.

> [!NOTE]
> Nel caso di una sequenza di escape Unicode, è necessario specificare tutte e quattro le cifre esadecimali. Ovvero, `\u006A` è una sequenza di escape valida, mentre `\u06A` e `\u6A` non sono validi.
>
> Nel caso di una sequenza di escape esadecimale, è possibile omettere gli zeri iniziali. Ovvero le `\x006A` `\x06A` `\x6A` sequenze di escape, e sono valide e corrispondono allo stesso carattere.

## <a name="conversions"></a>Conversioni

Il `char` tipo è convertibile in modo implicito nei tipi [integrali](integral-numeric-types.md) seguenti: `ushort` ,, `int` `uint` , `long` e `ulong` . È anche convertibile in modo implicito nei tipi numerici a [virgola mobile](floating-point-numeric-types.md) predefiniti: `float` , `double` e `decimal` . È convertibile in modo esplicito in `sbyte` `byte` `short` tipi integrali, e.

Non esistono conversioni implicite da altri tipi al `char` tipo. Tuttavia, qualsiasi tipo numerico [integrale](integral-numeric-types.md) o a [virgola mobile](floating-point-numeric-types.md) è convertibile in modo esplicito in `char` .

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere la sezione [tipi integrali](~/_csharplang/spec/types.md#integral-types) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Tipi valore](value-types.md)
- [Stringhe](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [Codifica dei caratteri in .NET](../../../standard/base-types/character-encoding-introduction.md)
