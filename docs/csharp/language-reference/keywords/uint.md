---
title: Parola chiave uint - Riferimenti per C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.openlocfilehash: 9a60460f67f9b6cf0b57d40ebf2789536e870d75
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633152"
---
# <a name="uint-c-reference"></a>uint (Riferimenti per C#)

La parola chiave `uint` rappresenta un tipo integrale che archivia valori in base alla dimensione e all'intervallo mostrato nella tabella seguente.

|Tipo|Intervallo|Dimensione|Tipo .NET|
|----------|-----------|----------|-------------------------|
|`uint`|Da 0 a 4.294.967.295|Intero senza segno a 32 bit|<xref:System.UInt32?displayProperty=nameWithType>|

**Nota** Il tipo `uint` non è conforme a CLS. Usare `int`, laddove possibile.

## <a name="literals"></a>Valori letterali

È possibile dichiarare e inizializzare una variabile `uint` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `uint`, vale a dire se è minore di <xref:System.UInt32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 3.000.000.000 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `uint`.

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]

> [!NOTE]
> Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario. I valori letterali decimali non hanno prefissi.

A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità:

- C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.
- C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale. In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.

Di seguito sono riportati alcuni esempi.

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]

Valori letterali integer possono anche includere un suffisso che denota il tipo. Il suffisso `U` o 'u' denota un valore `uint` o `ulong`, a seconda del valore numerico del valore letterale. L'esempio seguente usa il suffisso `u` per indicare un intero senza segno di entrambi i tipi. Si noti che il primo valore letterale è `uint` perché il relativo valore è minore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, mentre il secondo è `ulong` perché il relativo valore è maggiore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.

[!code-csharp[usuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]

Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:

1. [int](int.md)
2. `uint`
3. [long](long.md)
4. [ulong](ulong.md)

## <a name="conversions"></a>Conversioni

Si verifica una conversione implicita predefinita da `uint` a [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) o [decimal](decimal.md). Ad esempio:

```csharp
float myFloat = 4294967290;   // OK: implicit conversion to float
```

Viene eseguita una conversione implicita predefinita da [byte](byte.md), [ushort](ushort.md) o [char](char.md) a `uint`. In tutti gli altri casi è necessario ricorrere a un cast. Nella seguente istruzione di assegnazione, ad esempio, verrà generato un errore di compilazione senza un cast:

```csharp
long aLong = 22;
// Error -- no implicit conversion from long:
uint uInt1 = aLong;
// OK -- explicit conversion:
uint uInt2 = (uint)aLong;
```

Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `uint`. Ad esempio, l'istruzione seguente genera un errore di compilazione, a meno che non venga usato un cast esplicito:

```csharp
// Error -- no implicit conversion from double:
uint x = 3.0;
// OK -- explicit conversion:
uint y = (uint)3.0;
```

Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](float.md) e [double](double.md).

Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- <xref:System.UInt32>
- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tabella dei tipi integrali](integral-types-table.md)
- [Tabella dei tipi incorporati](built-in-types-table.md)
- [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md)
- [Tabella delle conversioni numeriche esplicite](explicit-numeric-conversions-table.md)
