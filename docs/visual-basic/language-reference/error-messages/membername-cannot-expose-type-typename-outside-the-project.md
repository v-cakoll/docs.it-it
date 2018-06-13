---
title: "&#39;&lt;MemberName&gt; &#39; non può esporre il tipo &#39; &lt;typename&gt; &#39; all'esterno del progetto tramite &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 36add48ebee2d1804921eeeec0b59cdd4cbafecc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588093"
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a>&#39;&lt;MemberName&gt; &#39; non può esporre il tipo &#39; &lt;typename&gt; &#39; all'esterno del progetto tramite &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;
Una variabile, parametro di routine o restituito dalla funzione viene esposto all'esterno del relativo contenitore, ma è dichiarato come un tipo che non deve essere esposti di fuori del contenitore.  
  
 La struttura del codice seguente viene illustrata una situazione che genera l'errore.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Un tipo dichiarato `Protected`, `Friend`, `Protected Friend`, o `Private` deve avere accesso all'esterno del contesto di dichiarazione limitato. Utilizzarlo come dati di tipo di una variabile con accesso limitato meno vanificherebbe lo scopo. Nel codice precedente, `exposedVar` è `Public` ed espone `privateClass` al codice che non deve avere accesso a esso.  
  
 **ID errore:** BC30909  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Modifica il livello di accesso della variabile, parametro di routine o funzione restituito per essere restrittivi almeno quanto il livello di accesso di tipo di dati.  
  
## <a name="see-also"></a>Vedere anche  
 [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
