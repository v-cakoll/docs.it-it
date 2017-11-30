---
title: Tipo di dati Short (Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
f1_keywords: vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: fef948debed69cf9fb7b0e6bb65eb0ddbe497a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="short-data-type-visual-basic"></a>Tipo di dati short (Visual Basic)
Contiene valori integer a 16 bit (2 byte) in un intervallo compreso tra -32.768 e 32.767.  
  
## <a name="remarks"></a>Note  
 Utilizzare il `Short` il tipo di dati per contenere i valori integer che non richiedono l'ampiezza dei dati completo `Integer`. In alcuni casi, è possibile comprimere common language runtime il `Short` variabili e ridurre il consumo di memoria.  
  
 Il valore predefinito di `Short` è 0.  
  
## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare un `Short` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `Short`, vale a dire se è minore di <xref:System.Int16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i numeri interi uguale a 1,034 rappresentati come decimali, esadecimali, e valori letterali binari vengono convertiti implicitamente dal [intero](integer-data-type.md) a `Short` valori.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Valori letterali numerici possono includere anche il `S` [carattere tipo](../../programming-guide\language-features\data-types/type-characters.md) per indicare il `Short` il tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H0326S
```

## <a name="programming-tips"></a>Suggerimenti sulla programmazione

-   **Ampliamento.** Il `Short` può ampliarsi nel tipo di dati `Integer`, `Long`, `Decimal`, `Single`, o `Double`. È pertanto possibile convertire `Short` in uno di questi tipi senza generare un errore <xref:System.OverflowException?displayProperty=nameWithType>.  
  
-   **Caratteri tipo.** Aggiungendo il carattere di tipo letterale `S` a un valore letterale, se ne determina la conversione nel tipo di dati `Short`. `Short`non include alcun carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Int16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

 <xref:System.Int16?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Tipo di dati Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
