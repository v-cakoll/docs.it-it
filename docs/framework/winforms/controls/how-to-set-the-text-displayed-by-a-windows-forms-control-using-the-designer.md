---
title: 'Procedura: impostare il testo visualizzato da un controllo Windows Form utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: e41ce3e91e6c2a3c91dd0dc39723df1185721096
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a>Procedura: impostare il testo visualizzato da un controllo Windows Form utilizzando la finestra di progettazione
Controlli Windows Form in genere visualizzano il testo che è correlato alla funzione principale del controllo. Ad esempio, un <xref:System.Windows.Forms.Button> controllo Visualizza in genere una didascalia indicante l'azione da eseguire quando si fa clic sul pulsante. Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>. È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>.  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a>Per impostare il testo e il tipo di carattere con la finestra di progettazione  
  
1.  Nella finestra Proprietà impostare la <xref:System.Windows.Forms.Control.Text%2A> proprietà del controllo su una stringa appropriata.  
  
     Per creare un tasto di scelta rapida sottolineato, includere una e commerciale (&) prima della lettera che sarà il tasto di scelta rapida.  
  
2.  Nella finestra Proprietà fare clic sul pulsante con puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.Control.Font%2A> proprietà.  
  
     Selezionare il tipo di carattere, lo stile del carattere, dimensioni, effetti (ad esempio barrato o sottolineato) e script che si desidera, nella finestra di dialogo tipo di carattere standard.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Impostare il testo visualizzato da un controllo Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
