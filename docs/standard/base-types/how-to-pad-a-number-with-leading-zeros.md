---
title: 'Procedura: Aggiungere zeri iniziali a un numero'
description: Impara a riempire un numero con zeri iniziali. Aggiungere zeri iniziali a numeri interi o valori numerici a una lunghezza totale specifica o a un numero specifico di zeri iniziali.
ms.date: 02/25/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
ms.openlocfilehash: 6ef0ddb37f1bc73254aa639d7c018ec6a01abd9b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447186"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a>Procedura: Aggiungere zeri iniziali a un numero

È possibile aggiungere degli zeri iniziali a un numero intero usando la [stringa di formato numerico standard](standard-numeric-format-strings.md) "D" con un identificatore di precisione. È possibile aggiungere zeri iniziali sia ai numeri interi che ai numeri a virgola mobile usando una [stringa di formato numerico personalizzata](custom-numeric-format-strings.md). Questo argomento illustra come usare entrambi i metodi per aggiungere gli zeri iniziali a un numero.

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a>Per aggiungere un intero con gli zeri iniziali a una lunghezza specifica

1. Determinare il numero minimo di cifre da visualizzare nel valore di tipo Integer. Includere eventuali cifre iniziali nel numero.

1. Determinare se si vuole visualizzare il valore di tipo Integer come valore decimale o esadecimale.

    - Per visualizzare il valore di tipo Integer come valore decimale, chiamare il metodo `ToString(String)` e passare la stringa "D*n*" come valore del parametro `format`, dove *n* rappresenta la lunghezza minima della stringa.

    - Per visualizzare il numero intero come valore esadecimale, chiamare il metodo `ToString(String)` e passare la stringa "X*n*" come valore del parametro format, dove *n* rappresenta la lunghezza minima della stringa.

È anche possibile formattare la stringa come stringa interpolata in [C#](../../csharp/language-reference/tokens/interpolated.md) e in [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) oppure chiamare un metodo, come <xref:System.String.Format%2A?displayProperty=nameWithType> o <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, che usa la [formattazione composita](composite-formatting.md).

Il seguente esempio formatta diversi valori di tipo Integer con gli zeri iniziali in modo che la lunghezza totale del numero formattato sia almeno di otto caratteri.

[!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
[!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a>Per aggiungere un intero con un determinato numero di zeri iniziali

1. Determinare il numero di zeri iniziali da visualizzare nel valore di tipo Integer.

1. Determinare se si vuole visualizzare il valore di tipo Integer come valore decimale o esadecimale.

    - Per applicare la formattazione come valore decimale, è necessario usare l'identificatore di formato standard "D".

    - Per applicare la formattazione come valore esadecimale, è necessario usare l'identificatore di formato standard "X".

1. Determine la lunghezza della stringa numerica non aggiunta chiamando il metodo `ToString("D").Length` o `ToString("X").Length` del valore di tipo Integer.

1. Aggiungere il numero di zeri iniziali da includere nella stringa formattata nella lunghezza della stringa numerica non aggiunta. L'aggiunta del numero di zeri iniziali definisce la lunghezza della stringa formattata.

1. Chiamare il metodo `ToString(String)` del valore integer e passare la stringa "D*n*" per le stringhe decimali e la stringa "X*n*" per quelle esadecimali, dove *n* rappresenta la lunghezza totale della stringa aggiunta. È anche possibile usare la stringa di formato "D*n*" o "X*n*" in un metodo che supporta la formattazione composta.

Il seguente esempio aggiunge un valore di tipo Integer con cinque zeri iniziali.

[!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
[!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a>Per aggiungere un valore numerico con gli zeri iniziali a una lunghezza specifica

1. Determinare il numero di cifre alla sinistra del decimale che deve avere la rappresentazione della stringa del numero. Includere gli eventuali zeri iniziali nel numero totale di cifre.

1. Definire una stringa in formato numerico personalizzato in cui si usa un segnaposto zero "0" per rappresentare il numero minimo di zeri.

1. Chiamare il metodo `ToString(String)` del numero e passarlo alla stringa di formato personalizzata. È anche possibile usare la stringa in formato personalizzato con un metodo che supporta la formattazione composita.

L'esempio seguente formatta diversi valori numerici con gli zeri iniziali. Di conseguenza, la lunghezza totale del numero formattato è di almeno otto cifre a sinistra del decimale.

[!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
[!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a>Per aggiungere un valore numerico con un determinato numero di zeri iniziali

1. Determinare il numero di zeri iniziali che deve avere il valore numerico.

1. Determinare il numero di cifre a sinistra del decimale nella stringa numerica senza aggiunta di zeri iniziali:

    1. Determinare se la rappresentazione della stringa di un numero include un simbolo di separatore decimale.

    1. In questo caso, determinare il numero di caratteri alla sinistra del separatore decimale.

         -oppure-

         In caso contrario, determinare la lunghezza della stringa.

1. Creare una stringa in formato personalizzato in cui si usa:

    - Il segnaposto zero "0" per ogni zero iniziale da visualizzare nella stringa.

    - Il segnaposto zero o il segnaposto di cifra "#" per rappresentare ogni cifra nella stringa predefinita.

1. Fornire la stringa di formato personalizzata come parametro nel metodo `ToString(String)` del numero o in un metodo che supporta la formattazione composta.

Il seguente esempio aggiunge due valori <xref:System.Double> con cinque zeri iniziali.

[!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
[!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]

## <a name="see-also"></a>Vedere anche

- [Stringhe di formato numerico personalizzato](custom-numeric-format-strings.md)
- [Stringhe di formato numerico standard](standard-numeric-format-strings.md)
- [Formattazione composita](composite-formatting.md)
