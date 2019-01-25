---
title: La prima istruzione di questo oggetto &#39;Sub New&#39; deve essere una chiamata a &#39;MyBase. New&#39; o &#39;MyClass. New&#39; (nessun costruttore accessibile senza parametri)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 75832ae88908094c1cb74ce04ad84c0d2ae91e68
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728895"
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>La prima istruzione di questo oggetto &#39;Sub New&#39; deve essere una chiamata a &#39;MyBase. New&#39; o &#39;MyClass. New&#39; (nessun costruttore accessibile senza parametri)
La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase. New' o 'MyClass. New' perché classe di base\<basename >' di '\<derivedname >' è privo di un 'Sub New' accessibile che può essere chiamato senza argomenti.  
  
 In una classe derivata, ogni costruttore deve chiamare un costruttore di classe di base (`MyBase.New`). Se la classe di base ha un costruttore senza parametri accessibile alle classi derivate, `MyBase.New` può essere chiamato automaticamente. In caso contrario, un costruttore di classe di base deve essere chiamato con parametri e questa operazione non può essere eseguita automaticamente. In questo caso, la prima istruzione di ogni costruttore della classe derivata deve chiamare un costruttore con parametri nella classe base o chiamare un altro costruttore nella classe derivata che consente di chiamare un costruttore di classe di base.  
  
 **ID errore:** BC30148  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Chiamare `MyBase.New` specificando i parametri obbligatori o chiamare un costruttore di peer che effettua una chiamata di questo tipo.  
  
     Ad esempio, se la classe di base ha un costruttore che viene dichiarato come `Public Sub New(ByVal index as Integer)`, la prima istruzione in derivato costruttore della classe potrebbe essere `MyBase.New(100)`.  
  
## <a name="see-also"></a>Vedere anche
- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
