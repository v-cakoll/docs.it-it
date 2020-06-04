---
title: Le espressioni lambda non sono valide nella prima espressione di un'istruzione 'Select Case'
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 08f7cd9dd95a10cad0df6539ba43122495347bae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397363"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a>Le espressioni lambda non sono valide nella prima espressione di un'istruzione 'Select Case'
Non è possibile usare un'espressione lambda per l'espressione di test in un' `Select Case` istruzione. Le definizioni delle espressioni lambda restituiscono funzioni e l'espressione di test di un' `Select Case` istruzione deve essere un tipo di dati elementare.  
  
 Il codice seguente causa questo errore:  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **ID errore:** BC36635  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Esaminare il codice per determinare se funziona una costruzione condizionale diversa, ad esempio un'istruzione `If...Then...Else` .  
  
- È possibile che si abbia intenzione di chiamare la funzione, come illustrato nel codice seguente:  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Istruzione If...Then...Else](../statements/if-then-else-statement.md)
- [Istruzione Select...Case](../statements/select-case-statement.md)
