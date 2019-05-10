---
title: 'Procedura: Agganciare i controlli in Windows Forms'
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
ms.openlocfilehash: b48761bda2baad4f7d1e6db9b41d73d6d54bc081
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211265"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Procedura: Agganciare i controlli in Windows Forms

Se si sta progettando un form che l'utente può ridimensionare in fase di esecuzione, i controlli sul form devono ridimensionare e riposizionare correttamente. Per ridimensionare i controlli in modo dinamico con il modulo, è possibile usare il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà dei controlli Windows Form. Il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà definisce una posizione di ancoraggio del controllo. Quando un controllo è agganciato a un modulo e il form viene ridimensionato, il controllo gestisce la distanza tra il controllo e la posizione di ancoraggio. Ad esempio, se si dispone di un <xref:System.Windows.Forms.TextBox> controllo è agganciato ai bordi inferiore del form e sinistro, destro, quando il form viene ridimensionato, la <xref:System.Windows.Forms.TextBox> controllo deve essere ridimensionato orizzontalmente in modo che mantiene la stessa distanza dai lati destro e sinistro del form. Inoltre, il controllo si posizionerà verticalmente in modo che il percorso è sempre la stessa distanza dal bordo inferiore del form. Se un controllo è agganciato non e il form viene ridimensionato, viene modificata la posizione del controllo in relazione i bordi del form.

Il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà interagisce con il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà. Per altre informazioni, vedere [Cenni preliminari sulle proprietà AutoSize](autosize-property-overview.md).

## <a name="anchor-a-control-on-a-form"></a>Ancoraggio di un controllo in un form

1. In Visual Studio, selezionare il controllo che si desidera ancorare.

    > [!NOTE]
    > È possibile ancorare più controlli contemporaneamente tenendo premuto CTRL, facendo clic su ogni controllo per selezionarla e quindi seguendo il resto di questa procedura.

2. Nel **delle proprietà** finestra, fare clic sulla freccia a destra del <xref:System.Windows.Forms.Control.Anchor%2A> proprietà.

     Viene visualizzato un editor che mostra una croce.

3. Per impostare un punto di ancoraggio, fare clic su alto, a sinistra, destra, ovvero nella sezione inferiore della finestra di tra.

     I controlli ancorati nella parte superiore e sinistra per impostazione predefinita.

4. Per cancellare un lato del controllo che è stato ancorato, fare clic su tale parte della croce.

5. Per chiudere la <xref:System.Windows.Forms.Control.Anchor%2A> editor di proprietà, fare clic su di <xref:System.Windows.Forms.Control.Anchor%2A> nuovo nome della proprietà.

Quando il form viene visualizzato in fase di esecuzione, il controllo viene ridimensionato per rimanere posizionato alla stessa distanza dal bordo del form. La distanza dal bordo ancorato rimane sempre lo stesso come distanza definito quando viene posizionato il controllo in Progettazione Windows Form.

> [!NOTE]
> Alcuni controlli, ad esempio il <xref:System.Windows.Forms.ComboBox> , dispongono di un limite all'altezza. Il controllo nella parte inferiore del form o contenitore di ancoraggio non è possibile forzare il controllo di superare il limite di altezza.

I controlli ereditati devono essere `Protected` per poter essere ancorata. Per modificare il livello di accesso di un controllo, impostare il relativo `Modifiers` proprietà nel **proprietà** finestra.

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Disposizione di controlli in Windows Form](arranging-controls-on-windows-forms.md)
- [Panoramica sulla proprietà AutoSize](autosize-property-overview.md)
- [Procedura: Ancorare i controlli in Windows Form](how-to-dock-controls-on-windows-forms.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Definire il layout dei Windows Form usando spaziatura, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md)
