---
title: Mouse capture in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 30432c6978f60cc9ad47d5df5dafc7aa45229f3b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151645"
---
# <a name="mouse-capture-in-windows-forms"></a>Mouse capture in Windows Form
*Passare il mouse capture* fa riferimento a quando un controllo accetta comandi del tutto l'input del mouse. Quando un controllo ha acquisito il mouse, riceve l'input del mouse se il puntatore si trova all'interno dei bordi.  
  
## <a name="setting-mouse-capture"></a>Impostazione stato Mouse Capture  
 In Windows Form viene acquisito il mouse dal controllo quando l'utente preme un pulsante del mouse su un controllo e il puntatore del mouse viene rilasciato dal controllo quando l'utente rilascia il pulsante del mouse.  
  
 Il <xref:System.Windows.Forms.Control.Capture%2A> proprietà del <xref:System.Windows.Forms.Control> classe specifica se un controllo ha acquisito il mouse. Per determinare quando un controllo perde il mouse capture, gestire il <xref:System.Windows.Forms.Control.MouseCaptureChanged> evento.  
  
 Solo la finestra di primo piano può acquisire il mouse. Quando una finestra di sfondo tenta di acquisire il mouse, la finestra riceve i messaggi solo per gli eventi del mouse che si verificano quando il puntatore del mouse è all'interno della parte visibile della finestra. Inoltre, anche se la finestra di primo piano ha acquisito il mouse, l'utente può comunque fare clic su un'altra finestra del portata in primo piano. Quando il puntatore del mouse viene acquisito, tasti di scelta rapida non funziona.  
  
## <a name="see-also"></a>Vedere anche

- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
