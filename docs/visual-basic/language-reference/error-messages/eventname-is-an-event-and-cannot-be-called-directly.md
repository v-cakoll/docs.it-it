---
title: '&#39;&lt;EventName&gt; &#39; è un evento e non può essere chiamato direttamente'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 4d8a7d716d2b7c52d1d027a1e7959d981bb0857e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39;&lt;EventName&gt; &#39; è un evento e non può essere chiamato direttamente
' <`eventname`>' è un evento e non può essere chiamato direttamente. Utilizzare un `RaiseEvent` istruzione per generare un evento.  
  
 Una chiamata di procedura specifica un evento per il nome della stored procedure. Un gestore eventi è una procedura, ma l'evento è un dispositivo di segnalazione, che deve essere generato e gestito.  
  
 **ID errore:** BC32022  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Utilizzare un `RaiseEvent` istruzione per segnalare un evento e richiamare la routine o una routine che gestiscono.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
