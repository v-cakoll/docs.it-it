---
title: Impossibile utilizzare i parametri di tipo come qualificatori
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 563010efc4f3049d330ee2b38b7f59e23292e630
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Impossibile utilizzare i parametri di tipo come qualificatori
Un elemento di programmazione è qualificato con la stringa di qualificazione che include un parametro di tipo.  
  
 Un parametro di tipo rappresenta un requisito per un tipo che deve essere fornito quando il tipo generico viene costruito. Non rappresenta un tipo specifico definito. La stringa di qualificazione deve includere solo gli elementi definiti in fase di compilazione.  
  
 Le istruzioni seguenti possono generare questo errore.  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **ID errore:** BC32098  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Rimuovere il parametro di tipo stringa di qualificazione o sostituirlo con un tipo definito.  
  
2.  Se è necessario utilizzare un tipo costruito per individuare l'elemento di programmazione qualificato, è necessario utilizzare la logica di programma aggiuntiva.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)
