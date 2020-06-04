---
title: "'<membername>' non può esporre il tipo '<typename>' all'esterno del progetto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 729a9f385d94412469d318cb804d216827eeb0fd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397285"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>'\<membername>' non può esporre il tipo '\<typename>' all'esterno del progetto mediante \<containertype> '\<containertypename>'
Una variabile, un parametro di routine o un valore restituito dalla funzione viene esposto all'esterno del relativo contenitore, ma viene dichiarato come un tipo che non deve essere esposto all'esterno del contenitore.  
  
 Il codice di scheletro seguente mostra una situazione che genera questo errore.  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Un tipo dichiarato,, `Protected` `Friend` `Protected Friend` o `Private` è progettato per avere accesso limitato al di fuori del contesto di dichiarazione. Il suo utilizzo come tipo di dati di una variabile con accesso meno limitato comporterebbe la sconfitta di questo scopo. Nel codice di scheletro precedente, `exposedVar` è `Public` ed esporrebbe `privateClass` a codice che non dovrebbe avere accesso a tale codice.  
  
 **ID errore:** BC30909  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Modificare il livello di accesso della variabile, il parametro di routine o la funzione Return in modo che sia almeno restrittivo come livello di accesso del tipo di dati.  
  
## <a name="see-also"></a>Vedere anche

- [Livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
