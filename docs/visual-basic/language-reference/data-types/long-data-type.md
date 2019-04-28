---
title: Tipo di dati Long (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: ca0f95342783d22559761294ccea6056cd3e4fa7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918450"
---
# <a name="long-data-type-visual-basic"></a>Tipo di dati Long (Visual Basic)

Contiene valori integer a 64 bit (8 byte) nell'intervallo compreso tra -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807 (9.2... E + 18).  
  
## <a name="remarks"></a>Note

 Usare la `Long` contenga numeri interi che sono troppo grandi per rientrare tipo di dati di `Integer` tipo di dati.  
  
 Il valore predefinito di `Long` è 0.

## <a name="literal-assignments"></a>Assegnazioni di valori letterali 

È possibile dichiarare e inizializzare un `Long` variabile da assegnarle un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `Long`, vale a dire se è minore di <xref:System.Int64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 4.294.967.296 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `Long`.
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> Il prefisso viene usato `&h` oppure `&H` per indicare un valore letterale esadecimale, il prefisso `&b` oppure `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente viene illustrato.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partire da Visual Basic 15.5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottale. Ad esempio:

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Valori letterali numerici possono includere anche il `L` [Digita carattere](../../programming-guide/language-features/data-types/type-characters.md) per indicare il `Long` tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>Suggerimenti sulla programmazione

- **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che `Long` ha una larghezza diversa dei dati (32 bit) in altri ambienti. Se si passa un argomento a 32 bit a tale componente, dichiararlo come `Integer` invece di `Long` nel nuovo codice Visual Basic.  
  
- **Widening.** Il `Long` può ampliarsi nel tipo di dati `Decimal`, `Single`, o `Double`. È pertanto possibile convertire `Long` in uno di questi tipi senza generare un errore <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Caratteri tipo.** Aggiungendo il carattere di tipo letterale `L` a un valore letterale, se ne determina la conversione nel tipo di dati `Long`. Aggiungendo il carattere identificatore di tipo `&` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Long`.  
  
- **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Int64?displayProperty=nameWithType>.  

## <a name="see-also"></a>Vedere anche

- <xref:System.Int64>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Tipo di dati Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
