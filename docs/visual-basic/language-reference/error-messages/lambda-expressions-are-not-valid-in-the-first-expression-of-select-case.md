---
title: Espressioni lambda non sono valide nella prima espressione di un &#39; Selezionare i Case &#39; istruzione
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords: BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e91401d6891d4e38014bb716a337560885cf73a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a>Espressioni lambda non sono valide nella prima espressione di un &#39; Selezionare i Case &#39; istruzione
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
