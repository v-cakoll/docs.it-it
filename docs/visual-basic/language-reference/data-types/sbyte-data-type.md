---
title: Tipo di dati SByte
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400792"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte data type (Visual Basic)

Contiene interi con segno a 8 bit (1 byte) compresi in un valore compreso tra -128 e 127.

## <a name="remarks"></a>Osservazioni

Utilizzare `SByte` il tipo di dati per contenere valori `Integer` integer che non richiedono `Short`l'intera larghezza dei dati o anche la metà della larghezza dei dati di . In alcuni casi, Common Language Runtime potrebbe `SByte` essere in grado di comprimere le variabili strettamente insieme e risparmiare il consumo di memoria.

Il valore predefinito di `SByte` è 0.

## <a name="literal-assignments"></a>Assegnazioni letterali

È possibile dichiarare `SByte` e inizializzare una variabile assegnandole un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario.

Nell'esempio seguente, i numeri interi uguali a -102 rappresentati come valori letterali decimali, esadecimali e binari vengono assegnati ai `SByte` valori. Questo esempio richiede la `/removeintchecks` compilazione con l'opzione del compilatore.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Utilizzare il `&h` `&H` prefisso o per indicare un valore `&b` `&B` letterale esadecimale, il prefisso o per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è `_`anche possibile utilizzare il carattere di sottolineatura, , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

A partire da Visual Basic 15.5, è`_`inoltre possibile utilizzare il carattere di sottolineatura ( ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Se il valore letterale integer è esterno all'intervallo di `SByte`, vale a dire se è minore di <xref:System.SByte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.SByte.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione. Quando un valore letterale integer non ha alcun suffisso, viene dedotto un [Integer.When](integer-data-type.md) an integer literal has no suffix, an Integer is inferred. Se il valore letterale integer `Integer` non è compreso nell'intervallo del tipo, viene dedotto [un valore Long.](long-data-type.md) Ciò significa che, negli esempi precedenti, `0b10011010` i valori letterali numerici e vengono interpretati <xref:System.SByte.MaxValue?displayProperty=nameWithType> `0x9A` come interi con segno a 32 bit con un valore di 156, che supera . Per compilare correttamente codice come questo che `SByte`assegna un numero intero non decimale a un oggetto , è possibile effettuare una delle seguenti operazioni:

- Disabilitare i controlli dei limiti `/removeintchecks` integer eseguendo la compilazione con l'opzione del compilatore.

- Utilizzare un [carattere tipo](../../programming-guide/language-features/data-types/type-characters.md) per definire in modo `SByte`esplicito il valore letterale che si desidera assegnare all'oggetto . Nell'esempio seguente viene `Short` assegnato un `SByte`valore letterale negativo a un oggetto . Si noti che, per i numeri negativi, è necessario impostare il bit più in ordine della parola più in ordine superiore del valore letterale numerico. Nel caso del nostro esempio, questo è `Short` il bit 15 del valore letterale.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Conformità a CLS.** Il `SByte` tipo di dati non fa parte di [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.

- **Ampliamento.** Il `SByte` tipo di `Short`dati `Integer` `Long`si `Decimal` `Single`allarga `Double`a , , , , e . Ciò significa `SByte` che è possibile eseguire la <xref:System.OverflowException?displayProperty=nameWithType> conversione in uno qualsiasi di questi tipi senza che si verifichi un errore.

- **Digitare caratteri.** `SByte`non dispone di alcun carattere di tipo letterale o tipo di identificatore.

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.SByte?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.SByte?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Tipo di dati IntegerInteger Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Utilizzo efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
