---
title: Tipo di dati Short
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 176d27c86127dac1d9c9c0231790f7a5c2a2fefc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415557"
---
# <a name="short-data-type-visual-basic"></a>Tipo di dati short (Visual Basic)

Include interi con segno a 16 bit (2 byte) compresi tra-32.768 e 32.767.  
  
## <a name="remarks"></a>Commenti  

 Utilizzare il `Short` tipo di dati per contenere valori integer per i quali non è necessaria la larghezza dei dati completa di `Integer` . In alcuni casi, il Common Language Runtime è in grado di comprimere le variabili in modo `Short` stretto e di risparmiare sull'utilizzo della memoria.  
  
 Il valore predefinito di `Short` è 0.  
  
## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare una variabile assegnandogli un valore letterale `Short` decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `Short`, vale a dire se è minore di <xref:System.Int16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i numeri interi uguali a 1.034 rappresentati come valori letterali decimali, esadecimali e binari vengono convertiti in modo implicito da [Integer](integer-data-type.md) a `Short` valori.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_` , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura ( `_` ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

I valori letterali numerici possono includere anche il `S` [carattere tipo](../../programming-guide/language-features/data-types/type-characters.md) per indicare il `Short` tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Conversioni.** Il `Short` tipo di dati viene ampliato in `Integer` , `Long` , `Decimal` , `Single` o `Double` . È pertanto possibile convertire `Short` in uno di questi tipi senza generare un errore <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Digitare i caratteri.** Aggiungendo il carattere di tipo letterale `S` a un valore letterale, se ne determina la conversione nel tipo di dati `Short`. `Short`non ha un carattere di tipo identificatore.  
  
- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Int16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Int16?displayProperty=nameWithType>
- [Tipi di dati](index.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Tipo di dati Integer](integer-data-type.md)
- [Tipo di dati Long](long-data-type.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
