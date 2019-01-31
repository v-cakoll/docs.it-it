---
title: Le espressioni lambda non sono valide nella prima espressione di un'istruzione 'Select Case'
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: d56515093020a4c987d132491957ce6db9e21683
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287794"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a>Le espressioni lambda non sono valide nella prima espressione di un'istruzione 'Select Case'
È possibile usare un'espressione lambda per l'espressione di test in un `Select Case` istruzione. Le definizioni delle espressioni lambda restituiscono le funzioni e l'espressione di test di un `Select Case` istruzione deve essere un tipo di dati elementare.  
  
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
- [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Istruzione Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)
