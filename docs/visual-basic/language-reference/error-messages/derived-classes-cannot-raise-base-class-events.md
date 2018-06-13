---
title: Le classi derivate non possono generare eventi di classe base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 365ce6ece1d964d3fac2a44f7ed4c1e16f44c95d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586399"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Le classi derivate non possono generare eventi di classe base
Un evento può essere generato solo dallo spazio di dichiarazione in cui viene dichiarato. Pertanto, una classe non può generare eventi da qualsiasi altra classe, uno da cui deriva.  
  
 **ID errore:** BC30029  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Spostare il `Event` istruzione o `RaiseEvent` istruzione in modo che siano della stessa classe.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
