---
title: Tipo di dati ULong (Visual Basic)
ms.date: 01/31/2018
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
ms.openlocfilehash: 82a2badc1bb22a55f753c9075562db3a5ee0d234
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522960"
---
# <a name="ulong-data-type-visual-basic"></a>Tipo di dati ULong (Visual Basic)

Contiene valori integer senza segno a 64 bit (8 byte) nell'intervallo compreso tra 0 e 18.446.744.073.709.551.615 (1,84 volte più di 10 ^ 19).  
  
## <a name="remarks"></a>Note

Usare la `ULong` tipo di dati per contenere dati binari troppo grandi per `UInteger`, o il più grande possibile valori unsigned integer.  
  
Il valore predefinito di `ULong` è 0.

## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare un `ULong` variabile da assegnarle un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `ULong`, vale a dire se è minore di <xref:System.UInt64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 7.934.076.125 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `ULong`.
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> Il prefisso viene usato `&h` oppure `&H` per indicare un valore letterale esadecimale, il prefisso `&b` oppure `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente viene illustrato.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partire da Visual Basic 15.5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottale. Ad esempio:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Valori letterali numerici possono includere anche il `UL` o `ul` [Digita carattere](../../programming-guide/language-features/data-types/type-characters.md) per indicare il `ULong` tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Suggerimenti sulla programmazione
  
-   **Numeri negativi.** Poiché `ULong` è un tipo unsigned, non può rappresentare un numero negativo. Se si usa l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce il tipo `ULong`, Visual Basic consente di convertire l'espressione da `Decimal` prima.  
  
-   **Conformità a CLS.** Il `ULong` tipo di dati non è in parte il [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), in modo che il codice conforme a CLS non è possibile utilizzare un componente che lo usa.  
  
-   **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi, ad esempio `ulong` può avere una larghezza diversa dei dati (32 bit) in altri ambienti. Se si passa un argomento a 32 bit a tale componente, dichiararlo come `UInteger` invece di `ULong` nel codice gestito di Visual Basic.  
  
     Inoltre, automazione non supporta valori interi a 64 bit in Windows 95, Windows 98, Windows ME o Windows 2000. Non è possibile passare un oggetto visivo di base `ULong` argomento a un componente di automazione in queste piattaforme.  
  
-   **Widening.** Il `ULong` può ampliarsi nel tipo di dati `Decimal`, `Single`, e `Double`. Ciò significa che è possibile convertire `ULong` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
-   **Caratteri tipo.** Aggiungendo i caratteri di tipo di valore letterale `UL` a un valore letterale, se ne determina la `ULong` tipo di dati. `ULong` possiede alcun carattere di tipo identificatore.
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt64?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.UInt64>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
