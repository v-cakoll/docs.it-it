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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343941"
---
# <a name="sbyte-data-type-visual-basic"></a>Tipo di dati SByte (Visual Basic)

Include interi con segno a 8 bit (1 byte) compresi tra-128 e 127.

## <a name="remarks"></a>Note

Utilizzare il tipo di dati `SByte` per contenere valori integer che non richiedono la larghezza dei dati completa di `Integer` o anche la lunghezza della metà dei dati di `Short`. In alcuni casi, il Common Language Runtime potrebbe essere in grado di comprimere le variabili di `SByte` e risparmiare sull'utilizzo della memoria.

Il valore predefinito di `SByte` è 0.

## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare una variabile di `SByte` assegnando un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario.

Nell'esempio seguente, i numeri interi uguali a-102 rappresentati come valori letterali decimali, esadecimali e binari vengono assegnati ai valori `SByte`. Questo esempio richiede la compilazione con l'opzione del compilatore `/removeintchecks`.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Se il valore letterale integer è esterno all'intervallo di `SByte`, vale a dire se è minore di <xref:System.SByte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.SByte.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione. Quando un valore letterale integer non ha alcun suffisso, viene dedotto un [valore integer](integer-data-type.md) . Se il valore letterale integer non è compreso nell'intervallo del tipo di `Integer`, viene dedotto un valore [Long](long-data-type.md) . Ciò significa che, negli esempi precedenti, i valori letterali numerici `0x9A` e `0b10011010` sono interpretati come interi con segno a 32 bit con un valore di 156, che supera <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Per compilare correttamente codice simile a questo che assegna un Integer non decimale a una `SByte`, è possibile eseguire una delle operazioni seguenti:

- Disabilitare i controlli dei limiti Integer compilando con l'opzione del compilatore `/removeintchecks`.

- Usare un [carattere tipo](../../programming-guide/language-features/data-types/type-characters.md) per definire in modo esplicito il valore letterale che si vuole assegnare al `SByte`. Nell'esempio seguente viene assegnato un valore letterale negativo `Short` a un `SByte`. Si noti che, per i numeri negativi, è necessario impostare il bit più significativo della parola più ordinata del valore letterale numerico. Nel caso dell'esempio, si tratta del bit 15 del valore letterale `Short`.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Conformità a CLS.** Il tipo di dati `SByte` non fa parte della [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.

- **Conversioni.** Il tipo di dati `SByte` viene ampliato in `Short`, `Integer`, `Long`, `Decimal`, `Single`e `Double`. Ciò significa che è possibile convertire `SByte` in uno di questi tipi senza riscontrare un errore <xref:System.OverflowException?displayProperty=nameWithType>.

- **Digitare i caratteri.** `SByte` non ha un carattere di tipo letterale o un carattere di tipo identificatore.

- **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.SByte?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.SByte?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Tipo di dati Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
