---
title: L'evento '<eventname1>' non può implementare l'evento '<eventname2>' nell'interfaccia '<interface>' poiché i tipi delegati '<delegate1>' e '<delegate2>' non corrispondono
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 32d6733580de8798a66c30d486b8439befd2af19
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409608"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a>L'evento '\<eventname1>' non può implementare l'evento '\<eventname2>' nell'interfaccia '\<interface>' poiché i tipi delegati '\<delegate1>' e '\<delegate2>' non corrispondono
Visual Basic non è in grado di implementare un evento perché il tipo delegato dell'evento non corrisponde al tipo delegato dell'evento nell'interfaccia. Questo errore può insorgere quando si definiscono più eventi in un'interfaccia e si prova a implementarli assieme con lo stesso evento. Un evento può implementare due o più eventi solo se tutti gli eventi implementati vengono dichiarati usando la sintassi `As` e se tutti specificano lo stesso tipo delegato.  
  
 **ID errore:** BC31423  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Implementare gli eventi separatamente.  
  
     -oppure-  
  
- Definire gli eventi nell'interfaccia usando la `As` sintassi e specificare lo stesso tipo delegato.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Event](../statements/event-statement.md)
- [Istruzione Delegate](../statements/delegate-statement.md)
- [Events](../../programming-guide/language-features/events/index.md)
