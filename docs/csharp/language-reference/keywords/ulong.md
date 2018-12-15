---
title: Parola chiave ulong - Riferimenti per C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: 97db22612e900658746f40cd117ff941135027a1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235020"
---
# <a name="ulong-c-reference"></a>ulong (Riferimenti per C#)

La parola chiave `ulong` denota un tipo integrale che archivia valori in base alla dimensione e all'intervallo mostrato nella tabella seguente.

|Tipo|Intervallo|Dimensione|Tipo .NET|
|----------|-----------|----------|-------------------------|
|`ulong`|Da 0 a 18.446.744.073.709.551.615|Intero senza segno a 64 bit|<xref:System.UInt64?displayProperty=nameWithType>|

## <a name="literals"></a>Valori letterali

È possibile dichiarare e inizializzare una variabile `ulong` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.  Se il valore letterale integer è esterno all'intervallo di `ulong`, vale a dire se è minore di <xref:System.UInt64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 7.934.076.125 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `ulong`.

[!code-csharp[ulong](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]

> [!NOTE]
> Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario. I valori letterali decimali non hanno prefissi.

A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità:

- C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.
- C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale. In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.

Di seguito sono riportati alcuni esempi.

[!code-csharp[long](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

Valori letterali integer possono anche includere un suffisso che denota il tipo. Il suffisso `UL` o `ul` identifica in modo inequivocabile un valore letterale numerico come valore `ulong`. Il suffisso `L` indica `ulong` se il valore letterale supera <xref:System.Int64.MaxValue?displayProperty=nameWithType>. Il suffisso `U` o `u` indica `ulong` se il valore letterale supera <xref:System.UInt32.MaxValue?displayProperty=nameWithType>. L'esempio seguente usa il suffisso `ul` per indicare un valore long integer:

[!code-csharp[ulsuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:

1. [int](int.md)
2. [uint](uint.md)
3. [long](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a>Risoluzione dell'overload del compilatore

Il suffisso viene comunemente usato per la chiamata di metodi di overload. Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `ulong` e [int](int.md):

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ulong l) {}
```

L'uso del suffisso con il parametro `ulong` garantisce che verrà chiamato il tipo corretto, ad esempio:

```csharp
SampleMethod(5);    // Calling the method with the int parameter
SampleMethod(5UL);  // Calling the method with the ulong parameter
```

## <a name="conversions"></a>Conversioni

Si verifica una conversione implicita predefinita da `ulong` a [float](float.md), [double](double.md) o [decimal](decimal.md).

Non viene eseguita alcuna conversione implicita da `ulong` a qualsiasi tipo integrale. L'istruzione seguente, ad esempio, genera un errore di compilazione se non viene usato un cast esplicito:

```csharp
long long1 = 8UL;   // Error: no implicit conversion from ulong
```

Viene eseguita una conversione implicita predefinita da [byte](byte.md), [ushort](ushort.md), [uint](uint.md) o [char](char.md) a `ulong`.

Non viene eseguita alcuna conversione implicita dai tipi a virgola mobile a `ulong`. Ad esempio, l'istruzione seguente genera un errore di compilazione, a meno che non venga usato un cast esplicito:

```csharp
// Error -- no implicit conversion from double:
ulong x = 3.0;
// OK -- explicit conversion:
ulong y = (ulong)3.0;
```

Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](float.md) e [double](double.md).

Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- <xref:System.UInt64>
- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tabella dei tipi integrali](integral-types-table.md)
- [Tabella dei tipi incorporati](built-in-types-table.md)
- [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md)
- [Tabella delle conversioni numeriche esplicite](explicit-numeric-conversions-table.md)
