---
title: Tipo di dati UShort
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: ee31156e00059699125fd72a7f091afbb21beab0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415479"
---
# <a name="ushort-data-type-visual-basic"></a>Tipo di dati UShort (Visual Basic)

Include interi senza segno a 16 bit (a 2 byte) compresi tra 0 e 65.535.  
  
## <a name="remarks"></a>Commenti

 Utilizzare il `UShort` tipo di dati per contenere dati binari troppo grandi per `Byte` .  
  
 Il valore predefinito di `UShort` è 0.  

## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare una variabile assegnandogli un valore letterale `UShort` decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `UShort`, vale a dire se è minore di <xref:System.UInt16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i numeri interi uguali a 65.034 rappresentati come valori letterali decimali, esadecimali e binari vengono assegnati ai `UShort` valori.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_` , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura ( `_` ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

I valori letterali numerici possono includere anche il `US` `us` [carattere di tipo](../../programming-guide/language-features/data-types/type-characters.md) o per indicare il `UShort` tipo di dati, come illustrato nell'esempio riportato di seguito.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione
  
- **Numeri negativi.** Poiché `UShort` è un tipo senza segno, non può rappresentare un numero negativo. Se si usa l'operatore unario meno ( `-` ) su un'espressione che restituisce il tipo `UShort` , Visual Basic converte prima l'espressione in `Integer` .  
  
- **Conformità a CLS.** Il `UShort` tipo di dati non fa parte del [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.
  
- **Conversioni.** Il `UShort` tipo di dati viene ampliato in `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` e `Double` . Ciò significa che è possibile `UShort` eseguire la conversione in uno di questi tipi senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
- **Digitare i caratteri.** L'aggiunta di caratteri di tipo letterale `US` a un valore letterale impone il `UShort` tipo di dati. `UShort`non ha un carattere di tipo identificatore.  
  
- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.UInt16>
- [Tipi di dati](index.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
