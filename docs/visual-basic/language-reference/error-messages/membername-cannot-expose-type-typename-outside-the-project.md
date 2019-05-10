---
title: "'<membername>' non può esporre il tipo '<typename>' all'esterno del progetto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: cb5191442ed8d3ee47c5116b10740e277ffa5bac
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661923"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>'\<nomeMembro >' non può esporre il tipo '\<nomeTipo >' all'esterno del progetto mediante \<containertype > '\<containertypename >'
Una variabile, parametro di routine o restituito dalla funzione viene esposto all'esterno del relativo contenitore, ma viene dichiarato come un tipo che non deve essere esposto all'esterno del contenitore.  
  
 Lo scheletro di codice seguente viene illustrata una situazione che genera l'errore.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Un tipo dichiarato `Protected`, `Friend`, `Protected Friend`, o `Private` deve avere accesso all'esterno del contesto di dichiarazione limitato. Per utilizzarlo come i dati di tipo di una variabile con meno restrizioni accesso vanificherebbe lo scopo. Nel codice precedente, `exposedVar` viene `Public` e consente di esporre `privateClass` al codice che non dovrebbe avere accesso a esso.  
  
 **ID errore:** BC30909  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Modifica il livello di accesso della variabile, parametro di routine o funzione, tornare a essere restrittivi almeno quanto il livello di accesso del relativo tipo di dati.  
  
## <a name="see-also"></a>Vedere anche

- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
