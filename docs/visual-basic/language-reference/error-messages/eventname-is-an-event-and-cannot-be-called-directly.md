---
title: "'<eventname>' è un evento e non può essere chiamato direttamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 510fff5370e63a31ee271421c0ab6f154518899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409595"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a>'\<eventname>' è un evento e non può essere chiamato direttamente
' <`eventname`>' è un evento e non può essere chiamato direttamente. Utilizzare un' `RaiseEvent` istruzione per generare un evento.  
  
 Una chiamata di routine specifica un evento per il nome della stored procedure. Un gestore eventi è una routine, ma l'evento stesso è un dispositivo di segnalazione, che deve essere generato e gestito.  
  
 **ID errore:** BC32022  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Utilizzare un' `RaiseEvent` istruzione per segnalare un evento e richiamare la procedura o le procedure che la gestiscono.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione RaiseEvent](../statements/raiseevent-statement.md)
