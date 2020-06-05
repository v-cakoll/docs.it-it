---
title: L'istruzione 'Class' deve terminare con un 'End Class' corrispondente
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 01c231f577d21028e9ef92f37c7ac5f7f1fe2aa3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415388"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a>L'istruzione 'Class' deve terminare con un 'End Class' corrispondente
`Class`viene usato per avviare un `Class` blocco, quindi può essere visualizzato solo all'inizio del blocco, con un'istruzione corrispondente che `End Class` termina il blocco. È presente un'istruzione ridondante `Class` oppure il blocco non è stato terminato `Class` con `End Class` .  
  
 **ID errore:** BC30481  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Individuare e rimuovere l'istruzione `Class` non necessaria.  
  
- Terminare il `Class` blocco con un oggetto corrispondente `End Class` .  
  
## <a name="see-also"></a>Vedere anche

- [\<keyword>Istruzione End](../statements/end-keyword-statement.md)
- [Istruzione Class](../statements/class-statement.md)
