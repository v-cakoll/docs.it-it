---
title: Funzione annidata non dispone di una firma compatibile con il delegato &#39; &lt;NomeDelegato&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 94c53d30ad9aea9386fbb1be3e65fa31719f7a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a>Funzione annidata non dispone di una firma compatibile con il delegato &#39; &lt;NomeDelegato&gt;&#39;
Un'espressione lambda è stata assegnata a un delegato che ha una firma compatibile. Nel codice seguente, ad esempio, è consigliabile delegare `Del` presenta due parametri di tipo integer.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Se un'espressione lambda con un argomento è dichiarata come tipo, viene generato l'errore `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **ID errore:** BC36532  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Modificare la definizione del delegato o l'espressione lambda assegnata in modo che le firme compatibili.  
  
## <a name="see-also"></a>Vedere anche  
 [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
