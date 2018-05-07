---
title: La prima istruzione di questo &#39;Sub New&#39; deve essere una chiamata a &#39;MyBase. New&#39; o &#39;MyClass. New&#39; (nessun costruttore accessibile senza parametri)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 3b24385932700a4843ae295bc82ef9529cc86b9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>La prima istruzione di questo &#39;Sub New&#39; deve essere una chiamata a &#39;MyBase. New&#39; o &#39;MyClass. New&#39; (nessun costruttore accessibile senza parametri)
La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase. New' o 'MyClass. New' perché classe di base\<basename >' di '\<derivedname >' non dispone di un 'Sub New' accessibile che può essere chiamato senza argomenti.  
  
 In una classe derivata, ogni costruttore deve chiamare un costruttore di classe di base (`MyBase.New`). Se la classe di base ha un costruttore senza parametri accessibile alle classi derivate, `MyBase.New` può essere chiamato automaticamente. In caso contrario, un costruttore di classe di base deve essere chiamato con parametri e questa operazione non può essere eseguita automaticamente. In questo caso, la prima istruzione di ogni costruttore di classe derivata deve chiamare un costruttore con parametri nella classe base o chiamare un altro costruttore nella classe derivata che esegue un costruttore della classe base chiamare.  
  
 **ID errore:** BC30148  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Chiamare `MyBase.New` specificando i parametri obbligatori o chiamare un costruttore peer che effettua una chiamata di questo tipo.  
  
     Ad esempio, se la classe di base ha un costruttore che è dichiarato come `Public Sub New(ByVal index as Integer)`la prima istruzione della classe derivata, il costruttore di classe potrebbe essere `MyBase.New(100)`.  
  
## <a name="see-also"></a>Vedere anche  
 [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
