---
title: '&#39;&lt;EventName&gt; &#39; è un evento e non può essere chiamato direttamente'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3efd8c18497ce288e16659db4ca4693d5a3e6acc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581996"
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39;&lt;EventName&gt; &#39; è un evento e non può essere chiamato direttamente
' <`eventname`>' è un evento e non può essere chiamato direttamente. Usare un `RaiseEvent` istruzione per generare un evento.  
  
 Una chiamata di routine specifica un evento per il nome della routine. Un gestore di è una procedura, ma l'evento stesso è un dispositivo di segnalazione, che deve essere generato e gestito.  
  
 **ID errore:** BC32022  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Usare un `RaiseEvent` istruzione per segnalare un evento e richiamare la routine o una routine che gestiscono.  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
