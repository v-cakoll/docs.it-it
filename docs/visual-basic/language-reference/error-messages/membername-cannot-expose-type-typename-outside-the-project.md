---
title: "&#39;&lt;nomeMembro&gt; &#39; non può esporre il tipo &#39; &lt;nomeTipo&gt; &#39; all'esterno del progetto mediante &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 39d316aca5ec306de4b1e43e2eb2d1495f5525d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672344"
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a>&#39;&lt;nomeMembro&gt; &#39; non può esporre il tipo &#39; &lt;nomeTipo&gt; &#39; all'esterno del progetto mediante &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;
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
  
-   Modifica il livello di accesso della variabile, parametro di routine o funzione, tornare a essere restrittivi almeno quanto il livello di accesso del relativo tipo di dati.  
  
## <a name="see-also"></a>Vedere anche
- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
