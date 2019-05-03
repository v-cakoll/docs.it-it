---
title: 'Procedura: Impostare il testo visualizzato da un controllo di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: a0f567befb1e0c323dd16fffedec279ff836cbf8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013218"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a>Procedura: Impostare il testo visualizzato da un controllo di Windows Forms usando la finestra di progettazione
Controlli Windows Form in genere visualizzano il testo è correlato alla funzione principale del controllo. Ad esempio, un <xref:System.Windows.Forms.Button> controllo Visualizza in genere una didascalia indicante l'azione che verrà eseguita quando si fa clic sul pulsante. Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>. È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>.  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a>Per impostare il testo e il tipo di carattere con la finestra di progettazione  
  
1. Nella finestra Proprietà impostare il <xref:System.Windows.Forms.Control.Text%2A> proprietà del controllo da una stringa appropriata.  
  
     Per creare un tasto di scelta rapida sottolineato, includere una e commerciale (&) alla lettera che sarà il tasto di scelta rapida.  
  
2. Nella finestra Proprietà, fare clic sul pulsante con puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.Control.Font%2A> proprietà.  
  
     Nella finestra di dialogo tipo di carattere standard, selezionare il tipo di carattere, lo stile del carattere, dimensioni, effetti (ad esempio barrato o carattere di sottolineatura) e script che si desidera.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Impostare il testo visualizzato dal controllo di un Windows Form](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Uso di tipi di carattere e testo](../advanced/using-fonts-and-text.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
