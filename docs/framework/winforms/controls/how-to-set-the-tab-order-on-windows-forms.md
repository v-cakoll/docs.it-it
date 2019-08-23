---
title: "Procedura: Impostare l'ordine di tabulazione in Windows Forms"
ms.date: 03/30/2017
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
ms.openlocfilehash: 0a6cd8b16148d28049549b241b568966239b9b01
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923608"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Procedura: Impostare l'ordine di tabulazione in Windows Forms
L'ordine di tabulazione è l'ordine in cui un utente sposta lo stato attivo da un controllo a un altro premendo il tasto TAB. Ogni form ha un proprio ordine di tabulazione. Per impostazione predefinita, l'ordine di tabulazione corrisponde all'ordine in cui sono stati creati i controlli. La numerazione dell'ordine di tabulazione inizia con zero.

## <a name="to-set-the-tab-order-of-a-control"></a>Per impostare l'ordine di tabulazione di un controllo

1. Scegliere **ordine**di tabulazione dal menu **Visualizza** .

     In questo modo viene attivata la modalità di selezione dell'ordine di tabulazione nel form. Un numero (che rappresenta <xref:System.Windows.Forms.Control.TabIndex%2A> la proprietà) viene visualizzato nell'angolo superiore sinistro di ogni controllo.

2. Fare clic sui controlli in sequenza per stabilire l'ordine di tabulazione desiderato.

    > [!NOTE]
    > La posizione di un controllo all'interno dell'ordine di tabulazione può essere impostata su qualsiasi valore maggiore o uguale a 0. Quando si verificano duplicati, l'ordine z dei due controlli viene valutato e il controllo nella parte superiore viene a schede per primo. (L'ordine z è il livello visivo dei controlli in un form lungo l'asse z del form [Depth]. L'ordine z determina i controlli che si trovano davanti ad altri controlli. Per ulteriori informazioni sull'ordine z, vedere la pagina relativa ai [livelli di oggetti su Windows Forms](how-to-layer-objects-on-windows-forms.md).

3. Al termine, fare di nuovo clic su tabulazione dal menu **Visualizza** per lasciare la modalità ordine di tabulazione.

    > [!NOTE]
    > I controlli che non possono ottenere lo stato attivo, nonché i controlli disabilitati e invisibili, <xref:System.Windows.Forms.Control.TabIndex%2A> non hanno una proprietà e non sono inclusi nell'ordine di tabulazione. Quando un utente preme il tasto TAB, questi controlli vengono ignorati.

 In alternativa, è possibile impostare l'ordine di tabulazione nell'finestra proprietà <xref:System.Windows.Forms.Control.TabIndex%2A> utilizzando la proprietà. La <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà di un controllo determina la posizione in cui è posizionata nell'ordine di tabulazione. Per impostazione predefinita, il primo controllo disegnato ha <xref:System.Windows.Forms.Control.TabIndex%2A> un valore pari a 0, il secondo <xref:System.Windows.Forms.Control.TabIndex%2A> ha un valore pari a 1 e così via.

 Inoltre, per impostazione predefinita, <xref:System.Windows.Forms.GroupBox> un controllo ha un <xref:System.Windows.Forms.Control.TabIndex%2A> proprio valore, ovvero un numero intero. Un <xref:System.Windows.Forms.GroupBox> controllo non può avere lo stato attivo in fase di esecuzione. Pertanto, ogni controllo all'interno <xref:System.Windows.Forms.GroupBox> di un oggetto ha <xref:System.Windows.Forms.Control.TabIndex%2A> un proprio valore decimale, a partire da. 0. Naturalmente, quando l' <xref:System.Windows.Forms.Control.TabIndex%2A> oggetto di <xref:System.Windows.Forms.GroupBox> un controllo viene incrementato, i controlli in esso contenuti verranno incrementati di conseguenza. Se è stato modificato <xref:System.Windows.Forms.Control.TabIndex%2A> un valore compreso tra 5 e 6 <xref:System.Windows.Forms.Control.TabIndex%2A> , il valore del primo controllo del gruppo viene automaticamente modificato in 6,0 e così via.

 Infine, qualsiasi controllo dei molti sul form può essere ignorato nell'ordine di tabulazione. In genere, la pressione di TAB in successione in fase di esecuzione seleziona ogni controllo nell'ordine di tabulazione. Disattivando la <xref:System.Windows.Forms.Control.TabStop%2A> proprietà, è possibile passare un controllo nell'ordine di tabulazione del form.

## <a name="to-remove-a-control-from-the-tab-order"></a>Per rimuovere un controllo dall'ordine di tabulazione

1. Impostare la <xref:System.Windows.Forms.Control.TabStop%2A> proprietà del controllo su `false` nel finestra Proprietà.

     Un controllo la <xref:System.Windows.Forms.Control.TabStop%2A> cui proprietà è stata impostata `false` su mantiene ancora la posizione nell'ordine di tabulazione, anche se il controllo viene ignorato quando si scorre il controllo con il tasto TAB.

    > [!NOTE]
    > Un gruppo di pulsanti di opzione ha una singola tabulazione in fase di esecuzione. Il pulsante selezionato (ovvero il pulsante con <xref:System.Windows.Forms.RadioButton.Checked%2A> la relativa proprietà impostata su `true`) dispone <xref:System.Windows.Forms.Control.TabStop%2A> automaticamente della proprietà impostata <xref:System.Windows.Forms.Control.TabStop%2A> su `true`, mentre gli altri pulsanti hanno la proprietà impostata su `false`. Per ulteriori informazioni sul raggruppamento <xref:System.Windows.Forms.RadioButton> di controlli, vedere [raggruppamento Windows Forms controlli RadioButton per funzionare come un set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Disposizione di controlli in Windows Form](arranging-controls-on-windows-forms.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
