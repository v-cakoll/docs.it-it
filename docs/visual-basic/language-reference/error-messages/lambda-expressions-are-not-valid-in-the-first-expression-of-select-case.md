---
title: Espressioni lambda non sono valide nella prima espressione di un &#39;Select Case&#39; istruzione
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: c492615850ec089fe35c1ae4eaba90a741e30f42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588921"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a>Espressioni lambda non sono valide nella prima espressione di un &#39;Select Case&#39; istruzione
Non è possibile utilizzare un'espressione lambda dell'espressione di test in un `Select Case` istruzione. Le definizioni delle espressioni lambda restituiscono funzioni e l'espressione di test di un `Select Case` istruzione deve essere un tipo di dati elementare.  
  
 Il codice seguente causa questo errore:  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **ID errore:** BC36635  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Esaminare il codice per determinare se funziona una costruzione condizionale diversa, ad esempio un'istruzione `If...Then...Else` .  
  
-   Se si intende chiamare la funzione, come illustrato nel codice seguente:  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Istruzione Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)
