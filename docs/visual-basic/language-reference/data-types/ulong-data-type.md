---
title: Tipo di dati ULong
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
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400701"
---
# <a name="ulong-data-type-visual-basic"></a>Tipo di dati ULong (Visual Basic)

Contiene interi senza segno a 64 bit (8 byte) che vanno da 0 a 18.446.744.073.709,551.615 (più di 1,84 x 10 x 19).

## <a name="remarks"></a>Osservazioni

Utilizzare `ULong` il tipo di dati per `UInteger`contenere dati binari troppo grandi per o per i valori integer senza segno più grandi possibili.

Il valore predefinito di `ULong` è 0.

## <a name="literal-assignments"></a>Assegnazioni letterali

È possibile dichiarare `ULong` e inizializzare una variabile assegnandole un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `ULong`, vale a dire se è minore di <xref:System.UInt64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 7.934.076.125 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `ULong`.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> Utilizzare il `&h` `&H` prefisso o per indicare un valore `&b` `&B` letterale esadecimale, il prefisso o per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è `_`anche possibile utilizzare il carattere di sottolineatura, , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partire da Visual Basic 15.5, è`_`inoltre possibile utilizzare il carattere di sottolineatura ( ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

I valori letterali `UL` numerici possono includere anche il `ul` [carattere](../../programming-guide/language-features/data-types/type-characters.md) di tipo o per indicare il `ULong` tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Numeri negativi.** Poiché `ULong` è un tipo senza segno, non può rappresentare un numero negativo. Se si utilizza l'operatore meno unario (`-` `ULong`) su un'espressione `Decimal` che restituisce type , Visual Basic converte l'espressione in prima.

- **Conformità a CLS.** Il `ULong` tipo di dati non fa parte di [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.

- **Considerazioni sull'interoperabilità.** Se si interagisce con componenti non scritti per .NET Framework, ad esempio oggetti `ulong` COM o di automazione, tenere presente che tipi quali possono avere una larghezza di dati diversa (32 bit) in altri ambienti. Se si passa un argomento a 32 bit a `UInteger` un `ULong` componente di questo tipo, dichiararlo come anziché nel codice Visual Basic gestito.

  Inoltre, l'automazione non supporta numeri interi a 64 bit in Windows 95, Windows 98, Windows ME o Windows 2000. Non è possibile `ULong` passare un argomento di Visual Basic a un componente di automazione su queste piattaforme.

- **Ampliamento.** Il `ULong` tipo di `Decimal`dati `Single`si `Double`allarga a , , e . Ciò significa `ULong` che è possibile eseguire la <xref:System.OverflowException?displayProperty=nameWithType> conversione in uno qualsiasi di questi tipi senza che si verifichi un errore.

- **Digitare caratteri.** L'aggiunta dei `UL` caratteri di tipo letterale a un valore letterale lo forza al tipo di `ULong` dati. `ULong`non ha alcun carattere di tipo identificatore.

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt64?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.UInt64>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Utilizzo efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
