---
title: Tipo di &#39; &lt;variablename&gt; &#39; non può essere dedotto perché i limiti del ciclo e la variabile di passaggio si amplia nello stesso tipo
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: d6fdd9445b5336773d150c643c7bf1ca58a0c87a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597152"
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Tipo di &#39; &lt;variablename&gt; &#39; non può essere dedotto perché i limiti del ciclo e la variabile di passaggio si amplia nello stesso tipo
È stato scritto un `For...Next` ciclo in cui il compilatore non è possibile dedurre un tipo di dati per la variabile di controllo perché vengono soddisfatte le condizioni seguenti:  
  
-   Il tipo di dati della variabile di controllo del ciclo non è specificato con una clausola `As` .  
  
-   I limiti del ciclo e la clausola step contengono almeno due tipi di dati.  
  
-   Non esiste alcuna conversione standard tra i tipi di dati.  
  
 Pertanto, il compilatore non è possibile dedurre il tipo di dati della variabile di controllo di un ciclo.  
  
 Nell'esempio seguente, la variabile di passaggio è un carattere e i limiti del ciclo sono entrambe numeri interi. Poiché non esiste alcuna conversione standard tra i caratteri e numeri interi, viene restituito questo errore.  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 **ID errore:** BC30982  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Modificare i tipi di limiti del ciclo e passaggio in base alle esigenze in modo che almeno uno di essi è un tipo che gli altri vengono ampliati ai. Nell'esempio precedente, modificare il tipo di `stepVar` a `Integer`.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     -oppure-  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   Utilizzare le funzioni di conversione esplicita per convertire i limiti del ciclo e passaggio per i tipi appropriati. Nell'esempio precedente, applicare il `Val` funzione `stepVar`.  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Istruzione Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
