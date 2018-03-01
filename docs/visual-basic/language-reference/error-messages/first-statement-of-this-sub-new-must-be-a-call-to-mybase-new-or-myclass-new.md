---
title: La prima istruzione di questo &#39; Sub nuovo &#39; deve essere una chiamata a &#39; MyBase. New &#39; o &#39; MyClass. New &#39; (Nessun costruttore accessibile senza parametri)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1065643e1f6c868092fbad839af0dbbd33afaf01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>La prima istruzione di questo &#39; Sub nuovo &#39; deve essere una chiamata a &#39; MyBase. New &#39; o &#39; MyClass. New &#39; (Nessun costruttore accessibile senza parametri)
La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase. New' o 'MyClass. New' perché classe di base\<basename >' di '\<derivedname >' non dispone di un 'Sub New' accessibile che può essere chiamato senza argomenti.  
  
 In una classe derivata, ogni costruttore deve chiamare un costruttore di classe di base (`MyBase.New`). Se la classe di base ha un costruttore senza parametri accessibile alle classi derivate, `MyBase.New` può essere chiamato automaticamente. In caso contrario, un costruttore di classe di base deve essere chiamato con parametri e questa operazione non può essere eseguita automaticamente. In questo caso, la prima istruzione di ogni costruttore di classe derivata deve chiamare un costruttore con parametri nella classe base o chiamare un altro costruttore nella classe derivata che esegue un costruttore della classe base chiamare.  
  
 **ID errore:** BC30148  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Chiamare `MyBase.New` specificando i parametri obbligatori o chiamare un costruttore peer che effettua una chiamata di questo tipo.  
  
     Ad esempio, se la classe di base ha un costruttore che è dichiarato come `Public Sub New(ByVal index as Integer)`la prima istruzione della classe derivata, il costruttore di classe potrebbe essere `MyBase.New(100)`.  
  
## <a name="see-also"></a>Vedere anche  
 [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
