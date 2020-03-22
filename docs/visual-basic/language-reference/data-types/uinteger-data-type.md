---
title: Tipo di dati UInteger
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400785"
---
# <a name="uinteger-data-type"></a>UInteger (tipo di dati)

Contiene interi senza segno a 32 bit (4 byte) compresi in un valore compreso tra 0 e 4.294.967.295.

## <a name="remarks"></a>Osservazioni

Il `UInteger` tipo di dati fornisce il valore senza segno più grande nella larghezza dei dati più efficiente.

Il valore predefinito di `UInteger` è 0.

## <a name="literal-assignments"></a>Assegnazioni letterali

È possibile dichiarare `UInteger` e inizializzare una variabile assegnandole un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `UInteger`, vale a dire se è minore di <xref:System.UInt32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 3.000.000.000 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `UInteger`.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> Utilizzare il `&h` `&H` prefisso o per indicare un valore `&b` `&B` letterale esadecimale, il prefisso o per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è `_`anche possibile utilizzare il carattere di sottolineatura, , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

A partire da Visual Basic 15.5, è`_`inoltre possibile utilizzare il carattere di sottolineatura ( ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

I valori letterali `UI` numerici possono includere anche il `ui` [carattere](../../programming-guide/language-features/data-types/type-characters.md) di tipo o per indicare il `UInteger` tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione

I `UInteger` `Integer` tipi di dati e offrono prestazioni ottimali su un`UShort`processore `Short` `Byte`a `SByte`32 bit, poiché i tipi Integer più piccoli ( , , e ), anche se utilizzano meno bit, richiedono più tempo per il caricamento, l'archiviazione e il recupero.

- **Numeri negativi.** Poiché `UInteger` è un tipo senza segno, non può rappresentare un numero negativo. Se si utilizza l'operatore meno unario (`-` `UInteger`) su un'espressione `Long` che restituisce type , Visual Basic converte l'espressione in prima.

- **Conformità a CLS.** Il `UInteger` tipo di dati non fa parte di [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.

- **Considerazioni sull'interoperabilità.** Se si interagisce con componenti non scritti per .NET Framework, ad esempio oggetti `uint` COM o di automazione, tenere presente che tipi quali possono avere una larghezza di dati diversa (16 bit) in altri ambienti. Se si passa un argomento a 16 bit a `UShort` un `UInteger` componente di questo tipo, dichiararlo come anziché nel codice Visual Basic gestito.

- **Ampliamento.** Il `UInteger` tipo di `Long`dati `ULong` `Decimal`si `Single`allarga a , , , , e `Double`. Ciò significa `UInteger` che è possibile eseguire la <xref:System.OverflowException?displayProperty=nameWithType> conversione in uno qualsiasi di questi tipi senza che si verifichi un errore.

- **Digitare caratteri.** L'aggiunta dei `UI` caratteri di tipo letterale a un valore letterale lo forza al tipo di `UInteger` dati. `UInteger`non ha alcun carattere di tipo identificatore.

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt32?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.UInt32>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Utilizzo efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
