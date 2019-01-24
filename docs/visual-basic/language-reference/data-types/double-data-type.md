---
title: Tipo di dati Double (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 456383dd2f38e96a8ff18472ff44c65ba7b4a341
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626485"
---
# <a name="double-data-type-visual-basic"></a>Tipo di dati Double (Visual Basic)
Contiene segno IEEE a 64 bit (8 byte) e con precisione doppia numeri a virgola mobile che intervallo compreso tra - 1, 79769313486231570E + 308 a - fino a 4.94065645841246544-324 per i valori negativi e tra fino a 4.94065645841246544-324 e 1.79769313486231570 e + 308 per valori positivi. Numeri a precisione doppia contengono un'approssimazione di un numero reale.  
  
## <a name="remarks"></a>Note  
 Il `Double` tipo di dati fornisce la grandezza più grande e più piccolo possibile per un numero.  
  
 Il valore predefinito di `Double` è 0.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Precisione.** Quando si lavora con numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione esatta in memoria. Ciò potrebbe provocare risultati imprevisti da determinate operazioni, ad esempio il confronto dei valori e `Mod` operatore. Per altre informazioni, vedere [tipi di dati di risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Zeri finali.** I tipi di dati a virgola mobile non è qualsiasi rappresentazione interna di zeri finali. Ad esempio, essi non viene fatta distinzione tra 4,2000 e 4.2. Di conseguenza, gli zeri finali non vengono visualizzati quando si visualizza o stampa valori a virgola mobile.  
  
-   **Caratteri tipo.** Aggiungendo il carattere di tipo letterale `R` a un valore letterale, se ne determina la conversione nel tipo di dati `Double`. Ad esempio, se un valore intero è seguito da `R`, il valore viene modificato in un `Double`.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     Aggiungendo il carattere identificatore di tipo `#` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Double`. Nell'esempio seguente, la variabile `num` tipizzata come una `Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Double?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Double?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Tipo di dati Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Tipo di dati Single](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Caratteri tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
