---
title: Parola chiave ushort - Riferimenti per C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
ms.openlocfilehash: 934e25576a8a24c176a54ec6af984459b513fe5a
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614459"
---
# <a name="ushort-c-reference"></a>ushort (Riferimenti per C#)

La parola chiave `ushort` indica un tipo di dati integrale che archivia valori in base alla dimensione e all'intervallo mostrato nella tabella seguente.

|Tipo|Intervallo|Dimensione|Tipo .NET|
|----------|-----------|----------|-------------------------|
|`ushort`|Da 0 a 65.535|Intero senza segno a 16 bit|<xref:System.UInt16?displayProperty=nameWithType>|

## <a name="literals"></a>Valori letterali

È possibile dichiarare e inizializzare una variabile `ushort` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `ushort`, vale a dire se è minore di <xref:System.UInt16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 65,034 rappresentati come valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](int.md) a valori `ushort`.

[!code-csharp[UShort](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]

> [!NOTE]
> Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario. I valori letterali decimali non hanno prefissi.

A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità:

- C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.
- C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale. In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.

Di seguito sono riportati alcuni esempi.

[!code-csharp[UShort](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]

## <a name="compiler-overload-resolution"></a>Risoluzione dell'overload del compilatore

Quando si chiamano metodi di overload, è necessario usare un cast. Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `ushort` e [int](int.md):

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ushort s) {}
```

L'uso del cast `ushort` garantisce che venga chiamato il tipo corretto, ad esempio:

```csharp
// Calls the method with the int parameter:
SampleMethod(5);
// Calls the method with the ushort parameter:
SampleMethod((ushort)5);
```

## <a name="conversions"></a>Conversioni

Viene eseguita una conversione implicita da `ushort` in [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) o [decimal](decimal.md).

Viene eseguita una conversione implicita predefinita da [byte](byte.md) o [char](char.md) in `ushort`. In caso contrario è necessario usare un cast per eseguire una conversione esplicita. Considerare, ad esempio, le due variabili `ushort` seguenti, `x` e `y`:

```csharp
ushort x = 5, y = 12;
```

L'istruzione di assegnazione seguente genererà un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce `int` per impostazione predefinita.

```csharp
ushort z = x + y;   // Error: conversion from int to ushort
```

Per risolvere il problema, usare un cast:

```csharp
ushort z = (ushort)(x + y);   // OK: explicit conversion
```

È possibile tuttavia usare le istruzioni seguenti dove la variabile di destinazione ha la stessa dimensione di archiviazione o una dimensione maggiore:

```csharp
int m = x + y;
long n = x + y;
```

Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `ushort`. Ad esempio, l'istruzione seguente genera un errore di compilazione, a meno che non venga usato un cast esplicito:

```csharp
// Error -- no implicit conversion from double:
ushort x = 3.0;
// OK -- explicit conversion:
ushort y = (ushort)3.0;
```

Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](float.md) e [double](double.md).

Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- <xref:System.UInt16>
- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tabella dei tipi integrali](integral-types-table.md)
- [Tabella dei tipi incorporati](built-in-types-table.md)
- [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md)
- [Tabella delle conversioni numeriche esplicite](explicit-numeric-conversions-table.md)
