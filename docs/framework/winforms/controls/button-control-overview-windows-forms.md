---
title: Cenni preliminari sul controllo Button (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 042ff7cb868b62778691348cb6c1ba464b794993
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656440"
---
# <a name="button-control-overview-windows-forms"></a>Cenni preliminari sul controllo Button (Windows Form)
Il controllo <xref:System.Windows.Forms.Button> Windows Form consente all'utente di eseguire le operazioni desiderate facendo clic su di esso. Una volta scelto, il pulsante viene visualizzato come se fosse stato effettivamente premuto e poi rilasciato. Ogni volta che l'utente fa clic su un pulsante, il <xref:System.Windows.Forms.Control.Click> viene richiamato il gestore di evento. Inserendo il codice nel <xref:System.Windows.Forms.Control.Click> gestore eventi per eseguire qualsiasi azione scelta.  
  
 Il testo visualizzato sul pulsante è contenuto nel <xref:System.Windows.Forms.Control.Text%2A> proprietà. Se il testo supera la larghezza del pulsante, eseguirà il wrapping alla riga successiva. Tuttavia, verrà troncato se il controllo non è possibile gestire l'altezza complessiva. Per altre informazioni, vedere [Procedura: Impostare il testo visualizzato dal controllo di un Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md). Il <xref:System.Windows.Forms.Control.Text%2A> proprietà può contenere una chiave di accesso, che consente agli utenti di "fare clic su" controllo premendo il tasto ALT con la chiave di accesso. Per informazioni dettagliate, vedere [come: Creare le chiavi di accesso per i controlli di Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md). L'aspetto del testo viene controllato mediante il <xref:System.Windows.Forms.Control.Font%2A> proprietà e il <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> proprietà.  
  
 Il <xref:System.Windows.Forms.Button> controllo può anche visualizzare immagini usando il <xref:System.Windows.Forms.ButtonBase.Image%2A> e <xref:System.Windows.Forms.ButtonBase.ImageList%2A> proprietà. Per altre informazioni, vedere [Procedura: Impostare l'immagine visualizzata da controllo di un Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.Button>
- [Procedura: Rispondere alle selezioni dei pulsanti di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [Modalità di selezione di un controllo Button di Windows Form](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Designare un pulsante di Windows Form come pulsante di conferma usando la finestra di progettazione](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Procedura: Designare un pulsante di Windows Form come pulsante Annulla usando la finestra di progettazione](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Controllo Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
