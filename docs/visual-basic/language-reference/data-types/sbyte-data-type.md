---
title: Tipo di dati SByte (Visual Basic)
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
ms.openlocfilehash: 1b10379e626c8e53b2e1e6eddaa964f13f9e4b62
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50037334"
---
# <a name="sbyte-data-type-visual-basic"></a>Tipo di dati SByte (Visual Basic)

Contiene valori integer a 8 bit (a 1 byte) in un intervallo compreso tra -128 e 127.  
  
## <a name="remarks"></a>Note

Usare la `SByte` tipo di dati per contenere i valori interi che non richiedono l'intera ampiezza dei dati `Integer` o anche la larghezza della metà dei dati di `Short`. In alcuni casi, common language runtime potrebbe essere possibile riunire i `SByte` variabili e ridurre il consumo di memoria.

Il valore predefinito di `SByte` è 0.

## <a name="literal-assignments"></a>Assegnazioni di valori letterali
  
È possibile dichiarare e inizializzare un `SByte` variabile da assegnarle un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.

Nell'esempio seguente, i valori interi uguali a 102 rappresentati come decimali, esadecimali o valori letterali binari vengono assegnati a `SByte` valori. In questo esempio richiede la compilazione con il `/removeintchecks` opzione del compilatore.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> Il prefisso viene usato `&h` oppure `&H` per indicare un valore letterale esadecimale, il prefisso `&b` oppure `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente viene illustrato.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

A partire da Visual Basic 15.5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottale. Ad esempio:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Se il valore letterale integer è esterno all'intervallo di `SByte`, vale a dire se è minore di <xref:System.SByte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.SByte.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione. Quando un valore letterale integer non ha alcun suffisso, un [Integer](integer-data-type.md) viene dedotto. Se il valore letterale integer è compreso nell'intervallo del `Integer` tipo, una [lungo](long-data-type.md) viene dedotto. Ciò significa che, negli esempi precedenti, i valori letterali numerici `0x9A` e `0b10011010` vengono interpretati come interi con segno a 32 bit con un valore corrispondente a 156, che supera <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Per la corretta compilazione codice simile al seguente che assegna un intero decimale non a un `SByte`, è possibile effettuare una delle operazioni seguenti:

- Disabilitare il controllo dei limiti di integer eseguendo la compilazione con il `/removeintchecks` opzione del compilatore.

- Usare un [carattere di tipo](../../programming-guide\language-features\data-types/type-characters.md) definire in modo esplicito il valore letterale che si desidera assegnare al `SByte`. L'esempio seguente assegna un valore letterale negativo `Short` valore per un `SByte`. Si noti che, per i numeri negativi, è necessario impostare il bit più significativo della parola più significativa del valore letterale numerico. Nel caso di questo esempio, si tratta del valore letterale 15 `Short` valore.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Suggerimenti sulla programmazione
  
-   **Conformità a CLS.** Il `SByte` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), in modo che il codice conforme a CLS non è possibile utilizzare un componente che lo usa.

-   **Ampliamento.** Il `SByte` può ampliarsi nel tipo di dati `Short`, `Integer`, `Long`, `Decimal`, `Single`, e `Double`. Ciò significa che è possibile convertire `SByte` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.
  
-   **Caratteri tipo.** `SByte` non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.SByte?displayProperty=nameWithType>.
  
## <a name="see-also"></a>Vedere anche

 <xref:System.SByte?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [Tipo di dati Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
