---
title: Tipo di dati ULong (Visual Basic)
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 606e0ef87b209bb2e75e28223f27d081713c1b7e
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="ulong-data-type-visual-basic"></a>Tipo di dati ULong (Visual Basic)

Contiene interi senza segno a 64 bit (8 byte) compresi nell'intervallo da 0 a 18.446.744.073.709.551.615 (oltre 1,84 volte 10 ^ 19).  
  
## <a name="remarks"></a>Note

Utilizzare il `ULong` il tipo di dati per contenere dati binari troppo grandi per `UInteger`, o il massimo valori unsigned integer.  
  
Il valore predefinito di `ULong` è 0.

## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare un `ULong` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `ULong`, vale a dire se è minore di <xref:System.UInt64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 7.934.076.125 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `ULong`.
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partire da Visual Basic 15,5, è inoltre possibile utilizzare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre binarie, ottale o esadecimale. Ad esempio:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Valori letterali numerici possono includere anche il `UL` o `ul` [carattere tipo](../../programming-guide\language-features\data-types/type-characters.md) per indicare il `ULong` il tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Suggerimenti sulla programmazione
  
-   **Numeri negativi.** Poiché `ULong` è un tipo unsigned, non può rappresentare un numero negativo. Se si utilizza l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce al tipo `ULong`, Visual Basic converte l'espressione `Decimal` prima.  
  
-   **Conformità a CLS.** Il `ULong` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto codice conforme a CLS non può utilizzare un componente che utilizza tale.  
  
-   **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi, ad esempio `ulong` può avere un'ampiezza dei dati diversa (32 bit) in altri ambienti. Se si passa un argomento a 32 bit a tale componente, dichiararla come `UInteger` anziché `ULong` nel codice gestito di Visual Basic.  
  
     Inoltre, automazione non supporta valori integer a 64 bit in Windows 95, Windows 98, Windows ME o Windows 2000. Non è possibile passare un Visual Basic `ULong` argomento a un componente di automazione su queste piattaforme.  
  
-   **Ampliamento.** Il `ULong` può ampliarsi nel tipo di dati `Decimal`, `Single`, e `Double`. È pertanto possibile convertire `ULong` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
-   **Caratteri tipo.** Aggiungendo i caratteri di tipo letterale `UL` a un valore letterale indica al sistema di `ULong` tipo di dati. `ULong`non include alcun carattere di tipo identificatore.
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt64?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

 <xref:System.UInt64>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
