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
ms.openlocfilehash: c2d3d7d360ccb240bafbe0e19e9f396adfba7f7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590264"
---
# <a name="double-data-type-visual-basic"></a>Tipo di dati Double (Visual Basic)
Contiene con segno IEEE a 64 bit (8 byte) e con precisione doppia numeri a virgola mobile in un intervallo compreso tra - 1.79769313486231570 e + 308 e - 4, 94065645841246544E-324 per i valori negativi e tra 4, 94065645841246544E-324 e 1.79769313486231570 e + 308 per valori positivi. Numeri a precisione doppia archiviano un'approssimazione di un numero reale.  
  
## <a name="remarks"></a>Note  
 Il `Double` tipo di dati fornisce la grandezza e più di un numero.  
  
 Il valore predefinito di `Double` è 0.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Precisione.** Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre contengono una precisa rappresentazione in memoria. Ciò potrebbe provocare risultati imprevisti da alcune operazioni, ad esempio il confronto di valori e `Mod` operatore. Per ulteriori informazioni, vedere [risoluzione dei problemi dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Zeri finali.** I tipi di dati a virgola mobile non dispone di alcuna rappresentazione interna degli zeri finali. Ad esempio, non distingue tra 4,2000 e 4.2. Di conseguenza, gli zeri finali non vengono visualizzati quando si visualizza o stampanti valori a virgola mobile.  
  
-   **Caratteri tipo.** Aggiungendo il carattere di tipo letterale `R` a un valore letterale, se ne determina la conversione nel tipo di dati `Double`. Ad esempio, se un valore intero è seguito da `R`, il valore viene modificato in un `Double`.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     Aggiungendo il carattere identificatore di tipo `#` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Double`. Nell'esempio seguente, la variabile `num` è tipizzato come un `Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Double?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Double?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Tipo di dati Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Tipo di dati Single](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Caratteri tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
