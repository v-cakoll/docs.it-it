---
title: Tipo di dati Long
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
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400813"
---
# <a name="long-data-type-visual-basic"></a>Tipo di dati Long (Visual Basic)

Contiene interi con segno a 64 bit (8 byte) compresi in -9.223.372.036.854.775.808 fino a 9.223.372.036.854.775.807 (9.2...E.18).

## <a name="remarks"></a>Osservazioni

Utilizzare `Long` il tipo di dati per contenere numeri `Integer` interi troppo grandi per essere inseriti nel tipo di dati.

Il valore predefinito di `Long` è 0.

## <a name="literal-assignments"></a>Assegnazioni letterali

È possibile dichiarare `Long` e inizializzare una variabile assegnandole un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `Long`, vale a dire se è minore di <xref:System.Int64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 4.294.967.296 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `Long`.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> Utilizzare il `&h` `&H` prefisso o per indicare un valore `&b` `&B` letterale esadecimale, il prefisso o per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è `_`anche possibile utilizzare il carattere di sottolineatura, , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partire da Visual Basic 15.5, è`_`inoltre possibile utilizzare il carattere di sottolineatura ( ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

I valori letterali `L` numerici possono includere `Long` anche il [carattere](../../programming-guide/language-features/data-types/type-characters.md) di tipo per indicare il tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Considerazioni sull'interoperabilità.** Se si interagisce con componenti non scritti per .NET Framework, ad `Long` esempio oggetti COM o di automazione, tenere presente che ha una larghezza di dati diversa (32 bit) in altri ambienti. Se si passa un argomento a 32 bit a `Integer` un `Long` componente di questo tipo, dichiararlo come anziché nel nuovo codice Visual Basic.

- **Ampliamento.** Il `Long` tipo di `Decimal`dati `Single`si `Double`allarga a , , o . È pertanto possibile convertire `Long` in uno di questi tipi senza generare un errore <xref:System.OverflowException?displayProperty=nameWithType>.

- **Digitare caratteri.** Aggiungendo il carattere di tipo letterale `L` a un valore letterale, se ne determina la conversione nel tipo di dati `Long`. Aggiungendo il carattere identificatore di tipo `&` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Long`.

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Int64?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Int64>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Tipo di dati IntegerInteger Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Utilizzo efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
