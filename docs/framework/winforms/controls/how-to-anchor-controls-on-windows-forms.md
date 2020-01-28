---
title: Ancorare i controlli (Anchor)
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7c307d8c5b3bc32e15e6de048c434854ef1bbc65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747189"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Procedura: ancorare i controlli in Windows Forms

Se si progetta un modulo che l'utente può ridimensionare in fase di esecuzione, i controlli sul form devono essere ridimensionati e riposizionati correttamente. Per ridimensionare i controlli in modo dinamico con il modulo, è possibile usare la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> dei controlli Windows Forms. La proprietà <xref:System.Windows.Forms.Control.Anchor%2A> definisce una posizione di ancoraggio per il controllo. Quando un controllo è ancorato a un form e il form viene ridimensionato, il controllo mantiene la distanza tra il controllo e le posizioni di ancoraggio. Se, ad esempio, si dispone di un controllo <xref:System.Windows.Forms.TextBox> ancorato ai bordi sinistro, destro e inferiore del form, quando il form viene ridimensionato, il controllo <xref:System.Windows.Forms.TextBox> viene ridimensionato orizzontalmente in modo da mantenere la stessa distanza dai lati destro e sinistro del form. Inoltre, il controllo si posiziona verticalmente in modo che la posizione sia sempre la stessa a distanza dal bordo inferiore del form. Se un controllo non è ancorato e il form viene ridimensionato, la posizione del controllo rispetto ai bordi del form viene modificata.

La proprietà <xref:System.Windows.Forms.Control.Anchor%2A> interagisce con la proprietà <xref:System.Windows.Forms.Control.AutoSize%2A>. Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](autosize-property-overview.md).

## <a name="anchor-a-control-on-a-form"></a>Ancoraggio di un controllo in un form

1. In Visual Studio selezionare il controllo che si vuole ancorare.

    > [!NOTE]
    > È possibile ancorare più controlli simultaneamente premendo il tasto CTRL, facendo clic su ogni controllo per selezionarlo e quindi attenendosi al resto della procedura.

2. Nella finestra **Proprietà** fare clic sulla freccia a destra della proprietà <xref:System.Windows.Forms.Control.Anchor%2A>.

     Viene visualizzato un editor che mostra una croce.

3. Per impostare un ancoraggio, fare clic sulla sezione superiore, a sinistra, a destra o in basso della Croce.

     Per impostazione predefinita, i controlli sono ancorati nella parte superiore e sinistra.

4. Per cancellare un lato del controllo che è stato ancorato, fare clic su tale ARM della Croce.

5. Per chiudere l'editor proprietà <xref:System.Windows.Forms.Control.Anchor%2A>, fare di nuovo clic sul nome della proprietà <xref:System.Windows.Forms.Control.Anchor%2A>.

Quando il form viene visualizzato in fase di esecuzione, il controllo viene ridimensionato in modo che rimanga posizionato alla stessa distanza dal bordo del form. La distanza dal bordo ancorato rimane sempre uguale alla distanza definita quando il controllo è posizionato nell'Progettazione Windows Form.

> [!NOTE]
> Alcuni controlli, ad esempio il controllo <xref:System.Windows.Forms.ComboBox>, hanno un limite per l'altezza. L'ancoraggio del controllo nella parte inferiore del form o del contenitore non può forzare il superamento del limite di altezza del controllo.

I controlli ereditati devono essere `Protected` per poter essere ancorati. Per modificare il livello di accesso di un controllo, impostarne la proprietà `Modifiers` nella finestra **Proprietà** .

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Panoramica sulla proprietà AutoSize](autosize-property-overview.md)
- [Procedura: Ancorare i controlli in Windows Form](how-to-dock-controls-on-windows-forms.md)
- [Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione di controlli Windows Form con spaziatura, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md)
