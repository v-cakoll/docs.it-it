---
title: Mouse capture in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: dfe983b9e407eddb9bed3bcc1a767cdeff38f2ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538408"
---
# <a name="mouse-capture-in-windows-forms"></a>Mouse capture in Windows Form
*Passa il mouse capture* fa riferimento a in presenza di un controllo dell'input del mouse tutti i comandi. Quando un controllo ha acquisito il mouse, riceve l'input del mouse o meno il puntatore si trova all'interno dei bordi.  
  
## <a name="setting-mouse-capture"></a>Impostazione di Mouse Capture  
 In Windows Form viene acquisito il mouse dal controllo quando l'utente preme un pulsante del mouse su un controllo, mentre il puntatore del mouse viene rilasciato dal controllo quando l'utente rilascia il pulsante del mouse.  
  
 Il <xref:System.Windows.Forms.Control.Capture%2A> proprietà la <xref:System.Windows.Forms.Control> classe specifica se un controllo ha acquisito il mouse. Per determinare quando un controllo perde il mouse capture, gestire il <xref:System.Windows.Forms.Control.MouseCaptureChanged> evento.  
  
 Solo la finestra di primo piano è possibile acquisire il mouse. Quando una finestra di sfondo tenta di acquisire il mouse, la finestra riceve i messaggi solo per gli eventi del mouse che si verificano quando il puntatore del mouse è all'interno della parte visibile della finestra. Inoltre, anche se la finestra di primo piano ha acquisito il mouse, l'utente può comunque fare clic su un'altra finestra portarla in primo piano. Quando viene acquisito il mouse, tasti di scelta rapida non funzionano.  
  
## <a name="see-also"></a>Vedere anche  
 [Input del mouse in un'applicazione Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
