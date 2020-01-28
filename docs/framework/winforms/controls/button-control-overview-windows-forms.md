---
title: Panoramica del controllo Button
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 4ba7b333e5414efb4814d64ce50c55e08b27f859
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747083"
---
# <a name="button-control-overview-windows-forms"></a>Panoramica del controllo Button (Windows Form)
Il controllo <xref:System.Windows.Forms.Button> Windows Form consente all'utente di eseguire le operazioni desiderate facendo clic su di esso. Una volta scelto, il pulsante viene visualizzato come se fosse stato effettivamente premuto e poi rilasciato. Ogni volta che l'utente fa clic su un pulsante, viene richiamato il gestore dell'evento <xref:System.Windows.Forms.Control.Click>. Inserire il codice nel gestore eventi <xref:System.Windows.Forms.Control.Click> per eseguire qualsiasi azione scelta.  
  
 Il testo visualizzato sul pulsante è contenuto nella proprietà <xref:System.Windows.Forms.Control.Text%2A>. Se il testo supera la larghezza del pulsante, verrà eseguito il wrapping alla riga successiva. Tuttavia, verrà ritagliata se il controllo non può contenere l'altezza complessiva. Per altre informazioni, vedere [procedura: impostare il testo visualizzato da un controllo Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md). La proprietà <xref:System.Windows.Forms.Control.Text%2A> può contenere una chiave di accesso, che consente a un utente di fare clic sul controllo premendo il tasto ALT con il tasto di accesso. Per informazioni dettagliate, vedere [procedura: creare chiavi di accesso per controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md). L'aspetto del testo è controllato dalla proprietà <xref:System.Windows.Forms.Control.Font%2A> e dalla proprietà <xref:System.Windows.Forms.ButtonBase.TextAlign%2A>.  
  
 Il controllo <xref:System.Windows.Forms.Button> può anche visualizzare immagini usando le proprietà <xref:System.Windows.Forms.ButtonBase.Image%2A> e <xref:System.Windows.Forms.ButtonBase.ImageList%2A>. Per altre informazioni, vedere [procedura: impostare l'immagine visualizzata da un controllo Windows Forms](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Button>
- [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Modalità di selezione di un controllo Button di Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Designare un pulsante Windows Form come pulsante di conferma usando la finestra di progettazione](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Procedura: Designare un pulsante Windows Form come pulsante Annulla usando la finestra di progettazione](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Controllo Button](button-control-windows-forms.md)
