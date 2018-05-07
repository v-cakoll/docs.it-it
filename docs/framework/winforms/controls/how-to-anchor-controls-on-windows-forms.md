---
title: 'Procedura: agganciare i controlli in Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: 3d0885ac3acde6732a5c059063f992913a98b9c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Procedura: agganciare i controlli in Windows Form
Se si progetta un form che l'utente può ridimensionare in fase di esecuzione, i controlli sul form devono ridimensionare e riposizionare correttamente. Per ridimensionare i controlli in modo dinamico con il modulo, è possibile utilizzare il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà dei controlli Windows Form. Il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà definisce una posizione di ancoraggio per il controllo. Quando un controllo viene ancorato a un modulo e il form viene ridimensionato, il controllo mantiene la distanza tra il controllo e la posizione di ancoraggio. Ad esempio, se dispone di un <xref:System.Windows.Forms.TextBox> controllo è ancorato il sinistro, destro e inferiore del form, come il form viene ridimensionato, il <xref:System.Windows.Forms.TextBox> controllo viene ridimensionato orizzontalmente in modo che mantiene la stessa distanza i lati destro e sinistro del form. Inoltre, il controllo si posizionerà verticalmente in modo che il percorso è sempre la stessa distanza dal bordo inferiore del form. Se un controllo non è ancorato e viene ridimensionato il form, la posizione del controllo in relazione i bordi del form viene modificata.  
  
 Il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà interagisce con il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà. Per ulteriori informazioni, vedere [Cenni preliminari sulla proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-anchor-a-control-on-a-form"></a>Per ancorare un controllo in un form  
  
1.  Selezionare il controllo che si desidera ancorare.  
  
    > [!NOTE]
    >  È possibile ancorare più controlli contemporaneamente tenendo premuto CTRL, fare clic su ogni controllo per selezionarlo e quindi seguendo il resto di questa procedura.  
  
2.  Nel **proprietà** finestra, fare clic sulla freccia a destra della <xref:System.Windows.Forms.Control.Anchor%2A> proprietà.  
  
     Viene visualizzato un editor con una croce.  
  
3.  Per impostare un punto di ancoraggio, fare clic su sezione inferiore della croce, alto, a sinistra o destra.  
  
     I controlli ancorati nella parte superiore e sinistra per impostazione predefinita.  
  
4.  Per cancellare un lato del controllo che è stato ancorato, fare clic su tale parte della croce.  
  
5.  Per chiudere il <xref:System.Windows.Forms.Control.Anchor%2A> editor proprietà scegliere il <xref:System.Windows.Forms.Control.Anchor%2A> nuovo nome della proprietà.  
  
 Quando il form viene visualizzato in fase di esecuzione, il controllo viene ridimensionato per rimanere posizionato alla stessa distanza dal bordo del form. La distanza dal bordo agganciato resta sempre la stessa alla distanza definita quando il controllo viene posizionato in Progettazione Windows Form.  
  
> [!NOTE]
>  Alcuni controlli, ad esempio il <xref:System.Windows.Forms.ComboBox> , presentano un limite di altezza. Il controllo nella parte inferiore del form o contenitore di ancoraggio non è possibile forzare il controllo di superare il limite di altezza.  
  
 I controlli ereditati devono essere `Protected` per poter essere ancorato. Per modificare il livello di accesso di un controllo, impostare il relativo `Modifiers` proprietà il **proprietà** finestra.  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)  
 [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Panoramica sulla proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Procedura: Ancorare i controlli in Windows Form](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Procedura dettagliata: disposizione di controlli Windows Form usando spaziatura, margini e la proprietà AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
