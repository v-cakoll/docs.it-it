---
title: Tipo di dati SByte (Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.sbyte
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
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bcd00665ec5b8651089811a61212bfa302fe95d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sbyte-data-type-visual-basic"></a>Tipo di dati SByte (Visual Basic)

Contiene valori integer a 8 bit (1-byte) in un intervallo compreso tra -128 e 127.  
  
## <a name="remarks"></a>Note

Utilizzare il `SByte` il tipo di dati per contenere i valori integer che non richiedono l'ampiezza dei dati completo `Integer` o anche l'ampiezza dei dati metà `Short`. In alcuni casi, potrebbe essere in grado di pack common language runtime il `SByte` variabili e ridurre il consumo di memoria.

Il valore predefinito di `SByte` è 0.

## <a name="literal-assignments"></a>Assegnazioni di valori letterali
  
È possibile dichiarare e inizializzare un `SByte` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.

Nell'esempio seguente, i numeri interi uguale a-102 rappresentati come decimali, esadecimali, e valori letterali binari vengono assegnati a `SByte` valori. In questo esempio richiede la compilazione con il `/removeintchecks` opzione del compilatore.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

Se il valore letterale integer è esterno all'intervallo di `SByte`, vale a dire se è minore di <xref:System.SByte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.SByte.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione. Quando un valore letterale integer non ha alcun suffisso, un [intero](integer-data-type.md) è dedotto. Se il valore letterale integer è compreso nell'intervallo del `Integer` tipo, un [lungo](long-data-type.md) è dedotto. Ciò significa che, negli esempi precedenti, i valori letterali numerici `0x9A` e `0b10011010` vengono interpretati come interi con segno a 32 bit con un valore di 156, che supera <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Per la corretta compilazione di codice simile al seguente che assegna un intero decimale non a un `SByte`, è possibile effettuare una delle operazioni seguenti:

- Disabilitare i controlli dei limiti integer per la compilazione con il `/removeintchecks` opzione del compilatore.

- Utilizzare un [carattere tipo](../../programming-guide\language-features\data-types/type-characters.md) definire in modo esplicito il valore letterale che si desidera assegnare il `SByte`. Nell'esempio seguente viene assegnato un valore negativo letterale `Short` valore un `SByte`. Si noti che, per i numeri negativi, è necessario impostare il bit più significativo della parola significativa del valore letterale numerico. Nel caso di questo esempio, questo è di tipo bit 15 del valore letterale `Short` valore.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Suggerimenti sulla programmazione
  
-   **Conformità a CLS.** Il `SByte` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto codice conforme a CLS non può utilizzare un componente che utilizza tale.

-   **Ampliamento.** Il `SByte` può ampliarsi nel tipo di dati `Short`, `Integer`, `Long`, `Decimal`, `Single`, e `Double`. È pertanto possibile convertire `SByte` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.
  
-   **Caratteri tipo.** `SByte`non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.SByte?displayProperty=nameWithType>.
  
## <a name="see-also"></a>Vedere anche

 <xref:System.SByte?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [Tipo di dati Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
