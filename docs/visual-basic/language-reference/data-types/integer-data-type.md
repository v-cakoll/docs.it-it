---
title: Tipo di dati Integer
ms.date: 01/31/2018
f1_keywords:
- vb.Integer
- Integer
helpviewer_keywords:
- numbers [Visual Basic], whole
- enumerated values [Visual Basic]
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- literal type characters [Visual Basic], I
- integers [Visual Basic], types
- data types [Visual Basic], integral
- '% identifier type character'
- data types [Visual Basic], assigning
- identifier type characters [Visual Basic], %
- I literal type character [Visual Basic]
- Integer data type
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
ms.openlocfilehash: c5b1041b8ef0ca9898a846fea03888537bb4abbf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343992"
---
# <a name="integer-data-type-visual-basic"></a>Integer data type (Visual Basic)

Contiene valori integer con segno a 32 bit (4 byte) in un intervallo compreso tra -2.147.483.648 e 2.147.483.647.  
  
## <a name="remarks"></a>Note

 Il tipo di dati `Integer` consente di ottenere prestazioni ottimali su processori a 32 bit. Gli altri tipi integrali vengono caricati e memorizzati più lentamente.  
  
 Il valore predefinito di `Integer` è 0.  

## <a name="literal-assignments"></a>Literal assignments

You can declare and initialize an `Integer` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal. Se il valore letterale integer è esterno all'intervallo di `Integer`, vale a dire se è minore di <xref:System.Int32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 90.946 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `Integer`.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal. I valori letterali decimali non hanno prefissi.

Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits. Esempio:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numeric literals can also include the `I` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Integer` data type, as the following example shows.

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Interop Considerations.** If you are interfacing with components not written for the .NET Framework, such as Automation or COM objects, remember that `Integer` has a different data width (16 bits) in other environments. Se si passa un argomento a 16 bit a un componente di questo tipo, nel nuovo codice Visual Basic è necessario eseguirne la dichiarazione come `Short` anziché come `Integer`.  
  
- **Widening.** Il tipo di dati `Integer` può ampliarsi nel tipo `Long`, `Decimal`, `Single` o `Double`. È pertanto possibile convertire `Integer` in uno di questi tipi senza generare un errore <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Type Characters.** Aggiungendo il carattere di tipo letterale `I` a un valore letterale, se ne determina la conversione nel tipo di dati `Integer`. Aggiungendo il carattere identificatore di tipo `%` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Integer`.  
  
- **Framework Type.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Int32?displayProperty=nameWithType>.  
  
## <a name="range"></a>Intervallo

Se si tenta di impostare una variabile di un tipo integrale su un numero esterno all'intervallo valido per tale tipo, verrà generato un errore. Se si tenta di impostarlo in una frazione, il numero viene arrotondato all'intero pari più vicino. Se il numero è egualmente vicino a due valori interi, il valore viene arrotondato all'intero pari più vicino. Questo comportamento riduce al minimo gli errori di arrotondamento risultanti dall'arrotondamento coerente di un valore del punto centrale in una singola direzione. Nel codice riportato di seguito vengono illustrati esempi di arrotondamento.  

```vb  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Int32?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
