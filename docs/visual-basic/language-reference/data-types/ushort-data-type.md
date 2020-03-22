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
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400694"
---
# <a name="ushort-data-type-visual-basic"></a>Tipo di dati UShort (Visual Basic)

Contiene interi senza segno a 16 bit (2 byte) compresi in un valore compreso tra 0 e 65.535.  
  
## <a name="remarks"></a>Osservazioni

 Utilizzare `UShort` il tipo di dati per `Byte`contenere dati binari troppo grandi per .  
  
 Il valore predefinito di `UShort` è 0.  

## <a name="literal-assignments"></a>Assegnazioni letterali

È possibile dichiarare `UShort` e inizializzare una variabile assegnandole un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `UShort`, vale a dire se è minore di <xref:System.UInt16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i numeri interi uguali a 65.034 rappresentati come valori letterali decimali, esadecimali e binari vengono assegnati ai `UShort` valori.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Utilizzare il `&h` `&H` prefisso o per indicare un valore `&b` `&B` letterale esadecimale, il prefisso o per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è `_`anche possibile utilizzare il carattere di sottolineatura, , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

A partire da Visual Basic 15.5, è`_`inoltre possibile utilizzare il carattere di sottolineatura ( ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

I valori letterali `US` numerici possono includere anche il `us` [carattere](../../programming-guide/language-features/data-types/type-characters.md) di tipo o per indicare il `UShort` tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione
  
- **Numeri negativi.** Poiché `UShort` è un tipo senza segno, non può rappresentare un numero negativo. Se si utilizza l'operatore meno unario (`-` `UShort`) su un'espressione `Integer` che restituisce type , Visual Basic converte l'espressione in prima.  
  
- **Conformità a CLS.** Il `UShort` tipo di dati non fa parte di [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.
  
- **Ampliamento.** Il `UShort` tipo di `Integer`dati `UInteger` `Long`si `ULong` `Decimal`allarga a , , , , , `Single`e `Double`. Ciò significa `UShort` che è possibile eseguire la <xref:System.OverflowException?displayProperty=nameWithType> conversione in uno qualsiasi di questi tipi senza che si verifichi un errore.  
  
- **Digitare caratteri.** L'aggiunta dei `US` caratteri di tipo letterale a un valore letterale lo forza al tipo di `UShort` dati. `UShort`non ha alcun carattere di tipo identificatore.  
  
- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.UInt16>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Utilizzo efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
