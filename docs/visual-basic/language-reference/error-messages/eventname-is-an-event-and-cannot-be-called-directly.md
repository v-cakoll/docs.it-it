---
title: "&#39; &lt;eventname&gt;&#39; è un evento e non può essere chiamato direttamente"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords: BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb987c957a28aa37c40ad975b945c20da4690f6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39; &lt;eventname&gt;&#39; è un evento e non può essere chiamato direttamente
' <`eventname`>' è un evento e non può essere chiamato direttamente. Utilizzare un `RaiseEvent` istruzione per generare un evento.  
  
 Una chiamata di procedura specifica un evento per il nome della stored procedure. Un gestore eventi è una procedura, ma l'evento è un dispositivo di segnalazione, che deve essere generato e gestito.  
  
 **ID errore:** BC32022  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Utilizzare un `RaiseEvent` istruzione per segnalare un evento e richiamare la routine o una routine che gestiscono.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
