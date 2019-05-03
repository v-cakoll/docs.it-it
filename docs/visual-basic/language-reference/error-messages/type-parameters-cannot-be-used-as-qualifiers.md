---
title: Impossibile utilizzare i parametri di tipo come qualificatori
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: ba7348ae50965ffcf2719b20934451916c8fa95a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923721"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Impossibile utilizzare i parametri di tipo come qualificatori
Un elemento di programmazione è qualificato con una stringa di qualificazione che includa un parametro di tipo.  
  
 Un parametro di tipo rappresenta un requisito per un tipo che deve essere specificato quando viene costruito il tipo generico. Non rappresenta un tipo specifico definito. La stringa di qualificazione deve includere solo gli elementi definiti in fase di compilazione.  
  
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
  
1. Rimuovere il parametro di tipo dalla stringa di qualificazione o sostituirlo con un tipo definito.  
  
2. Se è necessario utilizzare un tipo costruito per individuare l'elemento di programmazione completo in corso, è necessario usare la logica del programma aggiuntivi.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)
