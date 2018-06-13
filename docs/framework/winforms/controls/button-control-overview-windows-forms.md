---
title: Cenni preliminari sul controllo Button (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 88255882d3255eff112b9048a906182b64d75084
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526022"
---
# <a name="button-control-overview-windows-forms"></a>Cenni preliminari sul controllo Button (Windows Form)
Il controllo <xref:System.Windows.Forms.Button> Windows Form consente all'utente di eseguire le operazioni desiderate facendo clic su di esso. Una volta scelto, il pulsante viene visualizzato come se fosse stato effettivamente premuto e poi rilasciato. Ogni volta che l'utente fa clic su un pulsante, il <xref:System.Windows.Forms.Control.Click> viene richiamato il gestore di evento. Inserire il codice nel <xref:System.Windows.Forms.Control.Click> gestore eventi per eseguire qualsiasi operazione.  
  
 Cui è contenuto il testo visualizzato sul pulsante di <xref:System.Windows.Forms.Control.Text%2A> proprietà. Se il testo supera la larghezza del pulsante, eseguirà il wrapping alla riga successiva. Tuttavia, verrà troncato se il controllo non supporta l'altezza complessiva. Per ulteriori informazioni, vedere [procedura: impostare il testo visualizzato da un controllo Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md). Il <xref:System.Windows.Forms.Control.Text%2A> proprietà può contenere una chiave di accesso, che consente agli utenti di "fare clic su" controllo premendo il tasto ALT con la chiave di accesso. Per informazioni dettagliate, vedere [procedura: creazione di chiavi per i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md). L'aspetto del testo viene controllato mediante il <xref:System.Windows.Forms.Control.Font%2A> proprietà e <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> proprietà.  
  
 Il <xref:System.Windows.Forms.Button> controllo può anche visualizzare immagini utilizzando la <xref:System.Windows.Forms.ButtonBase.Image%2A> e <xref:System.Windows.Forms.ButtonBase.ImageList%2A> proprietà. Per ulteriori informazioni, vedere [procedura: impostare l'immagine visualizzata da un controllo Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Button>  
 [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Modalità di selezione di un controllo Button di Windows Form](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Procedura: Designare un pulsante Windows Form come pulsante di conferma usando la finestra di progettazione](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [Procedura: Designare un pulsante Windows Form come pulsante Annulla usando la finestra di progettazione](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [Controllo Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
