---
title: Le espressioni lambda non sono valide nella prima espressione di un'istruzione 'Select Case'
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: e9bf248da980705f070be878208c55b0cc6dae01
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64589728"
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
  
- Esaminare il codice per determinare se funziona una costruzione condizionale diversa, ad esempio un'istruzione `If...Then...Else` .  
  
- Se si intende chiamare la funzione, come illustrato nel codice seguente:  
  
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
