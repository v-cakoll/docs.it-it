---
title: "'<eventname>' è un evento e non può essere chiamato direttamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: eb0b40a80d37788bcab32791d7ed701a77505371
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831444"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a>'\<NomeEvento >' è un evento e non può essere chiamato direttamente
' <`eventname`>' è un evento e non può essere chiamato direttamente. Usare un `RaiseEvent` istruzione per generare un evento.  
  
 Una chiamata di routine specifica un evento per il nome della routine. Un gestore di è una procedura, ma l'evento stesso è un dispositivo di segnalazione, che deve essere generato e gestito.  
  
 **ID errore:** BC32022  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Usare un `RaiseEvent` istruzione per segnalare un evento e richiamare la routine o una routine che gestiscono.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
