---
title: Le classi derivate non possono generare eventi di classe base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: c59212a28ba27123a7db9163ff7437c159a3d310
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409699"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Le classi derivate non possono generare eventi di classe base
Un evento può essere generato solo dallo spazio di dichiarazione in cui è dichiarato. Pertanto, una classe non può generare eventi da qualsiasi altra classe, anche uno da cui è derivato.  
  
 **ID errore:** BC30029  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Spostare l' `Event` istruzione o l' `RaiseEvent` istruzione in modo che si trovino nella stessa classe.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Event](../statements/event-statement.md)
- [Istruzione RaiseEvent](../statements/raiseevent-statement.md)
