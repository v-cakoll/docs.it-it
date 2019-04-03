---
title: Le classi derivate non possono generare eventi di classe base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0e9acf4b3e71295655c15ae9b1c80852c9aca8df
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835141"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Le classi derivate non possono generare eventi di classe base
Un evento può essere generato solo dallo spazio di dichiarazione in cui è dichiarata. Di conseguenza, una classe non può generare eventi da qualsiasi altra classe, anche uno solo da cui è derivato.  
  
 **ID errore:** BC30029  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Spostare il `Event` istruzione o il `RaiseEvent` istruzione in modo che siano nella stessa classe.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
