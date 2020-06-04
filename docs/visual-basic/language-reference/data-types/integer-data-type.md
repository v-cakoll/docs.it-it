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
ms.openlocfilehash: aa7b64162308d6af2763b29034c5a7276c973876
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415609"
---
# <a name="integer-data-type-visual-basic"></a>Tipo di dati Integer (Visual Basic)

Contiene valori integer con segno a 32 bit (4 byte) in un intervallo compreso tra -2.147.483.648 e 2.147.483.647.  
  
## <a name="remarks"></a>Commenti

 Il tipo di dati `Integer` consente di ottenere prestazioni ottimali su processori a 32 bit. Gli altri tipi integrali vengono caricati e memorizzati più lentamente.  
  
 Il valore predefinito di `Integer` è 0.  

## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare una `Integer` variabile assegnandogli un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `Integer`, vale a dire se è minore di <xref:System.Int32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 90.946 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `Integer`.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_` , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura ( `_` ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

I valori letterali numerici possono includere anche il `I` [carattere tipo](../../programming-guide/language-features/data-types/type-characters.md) per indicare il `Integer` tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Considerazioni sull'interoperabilità.** Se si interagisce con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che `Integer` in altri ambienti è presente una larghezza dei dati diversa (16 bit). Se si passa un argomento a 16 bit a un componente di questo tipo, nel nuovo codice Visual Basic è necessario eseguirne la dichiarazione come `Short` anziché come `Integer`.  
  
- **Conversioni.** Il tipo di dati `Integer` può ampliarsi nel tipo `Long`, `Decimal`, `Single` o `Double`. È pertanto possibile convertire `Integer` in uno di questi tipi senza generare un errore <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Digitare i caratteri.** Aggiungendo il carattere di tipo letterale `I` a un valore letterale, se ne determina la conversione nel tipo di dati `Integer`. Aggiungendo il carattere identificatore di tipo `%` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Integer`.  
  
- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Int32?displayProperty=nameWithType>.  
  
## <a name="range"></a>Range

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
- [Tipi di dati](index.md)
- [Tipo di dati Long](long-data-type.md)
- [Tipo di dati Short](short-data-type.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
