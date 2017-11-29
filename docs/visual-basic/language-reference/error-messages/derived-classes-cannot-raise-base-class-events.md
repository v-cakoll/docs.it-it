---
title: Le classi derivate non possono generare eventi di classe base
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords: BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70dde8b96980adfd618e38b9ce142cdec56a6b13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Le classi derivate non possono generare eventi di classe base
Un evento può essere generato solo dallo spazio di dichiarazione in cui viene dichiarato. Pertanto, una classe non può generare eventi da qualsiasi altra classe, uno da cui deriva.  
  
 **ID errore:** BC30029  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Spostare il `Event` istruzione o `RaiseEvent` istruzione in modo che siano della stessa classe.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
