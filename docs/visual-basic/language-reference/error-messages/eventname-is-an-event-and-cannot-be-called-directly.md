---
title: "'<eventname>' è un evento e non può essere chiamato direttamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: bf900566bdb4ecf8d8961a12b5dd67ba426caf27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803313"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a>'\<NomeEvento >' è un evento e non può essere chiamato direttamente
' <`eventname`>' è un evento e non può essere chiamato direttamente. Usare un `RaiseEvent` istruzione per generare un evento.  
  
 Una chiamata di routine specifica un evento per il nome della routine. Un gestore di è una procedura, ma l'evento stesso è un dispositivo di segnalazione, che deve essere generato e gestito.  
  
 **ID errore:** BC32022  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Usare un `RaiseEvent` istruzione per segnalare un evento e richiamare la routine o una routine che gestiscono.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
