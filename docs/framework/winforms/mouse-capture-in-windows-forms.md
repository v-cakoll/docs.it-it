---
title: Mouse Capture
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741028"
---
# <a name="mouse-capture-in-windows-forms"></a>Mouse capture in Windows Form
Il *mouse capture* fa riferimento a quando un controllo accetta il comando di tutti gli input del mouse. Quando un controllo ha acquisito il mouse, riceve l'input del mouse indipendentemente dal fatto che il puntatore si trovi all'interno dei bordi.  
  
## <a name="setting-mouse-capture"></a>Impostazione dell'acquisizione del mouse  
 In Windows Forms il mouse viene acquisito dal controllo quando l'utente preme un pulsante del mouse su un controllo e il mouse viene rilasciato dal controllo quando l'utente rilascia il pulsante del mouse.  
  
 La proprietà <xref:System.Windows.Forms.Control.Capture%2A> della classe <xref:System.Windows.Forms.Control> specifica se un controllo ha acquisito il mouse. Per determinare quando un controllo perde il mouse capture, gestire l'evento <xref:System.Windows.Forms.Control.MouseCaptureChanged>.  
  
 Solo la finestra in primo piano può acquisire il mouse. Quando una finestra di sfondo tenta di acquisire il mouse, la finestra riceve i messaggi solo per gli eventi del mouse che si verificano quando il puntatore del mouse si trova all'interno della parte visibile della finestra. Inoltre, anche se la finestra in primo piano ha acquisito il mouse, l'utente può comunque fare clic su un'altra finestra, portandola in primo piano. Quando il mouse viene acquisito, i tasti di scelta rapida non funzionano.  
  
## <a name="see-also"></a>Vedere anche

- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
