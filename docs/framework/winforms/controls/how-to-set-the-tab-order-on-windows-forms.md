---
title: Imposta ordine di tabulazione dei controlli
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5d53e411bda0279271e4f73e1842c52fd6d9b3a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746838"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Procedura: impostare l'ordine di tabulazione in Windows Forms

L'ordine di tabulazione è l'ordine in cui un utente sposta lo stato attivo da un controllo a un altro premendo il tasto TAB. Ogni form ha un proprio ordine di tabulazione. Per impostazione predefinita, l'ordine di tabulazione corrisponde all'ordine in cui sono stati creati i controlli. La numerazione dell'ordine di tabulazione inizia con zero.

## <a name="to-set-the-tab-order-of-a-control"></a>Per impostare l'ordine di tabulazione di un controllo

1. In Visual Studio scegliere **ordine di tabulazione**dal menu **Visualizza** .

   In questo modo viene attivata la modalità di selezione dell'ordine di tabulazione nel form. Nell'angolo superiore sinistro di ogni controllo viene visualizzato un numero che rappresenta la proprietà <xref:System.Windows.Forms.Control.TabIndex%2A>.

2. Fare clic sui controlli in sequenza per stabilire l'ordine di tabulazione desiderato.

   > [!NOTE]
   > La posizione di un controllo all'interno dell'ordine di tabulazione può essere impostata su qualsiasi valore maggiore o uguale a 0. Quando si verificano duplicati, l'ordine z dei due controlli viene valutato e il controllo nella parte superiore viene a schede per primo. (L'ordine z è il livello visivo dei controlli in un form lungo l'asse z del form [Depth]. L'ordine z determina i controlli che si trovano davanti ad altri controlli. Per ulteriori informazioni sull'ordine z, vedere la pagina relativa ai [livelli di oggetti su Windows Forms](how-to-layer-objects-on-windows-forms.md).

3. Al termine, selezionare di nuovo **ordine di tabulazione** dal menu **Visualizza** per lasciare la modalità ordine di tabulazione.

   > [!NOTE]
   > I controlli che non possono ottenere lo stato attivo, nonché i controlli disabilitati e invisibili, non hanno una proprietà <xref:System.Windows.Forms.Control.TabIndex%2A> e non sono inclusi nell'ordine di tabulazione. Quando un utente preme il tasto TAB, questi controlli vengono ignorati.

In alternativa, è possibile impostare l'ordine di tabulazione nella Finestra Proprietà usando la proprietà <xref:System.Windows.Forms.Control.TabIndex%2A>. La proprietà <xref:System.Windows.Forms.Control.TabIndex%2A> di un controllo determina la posizione in cui è posizionata nell'ordine di tabulazione. Per impostazione predefinita, il primo controllo disegnato ha un valore <xref:System.Windows.Forms.Control.TabIndex%2A> 0, il secondo ha un <xref:System.Windows.Forms.Control.TabIndex%2A> di 1 e così via.

Inoltre, per impostazione predefinita, un controllo <xref:System.Windows.Forms.GroupBox> dispone di un proprio valore <xref:System.Windows.Forms.Control.TabIndex%2A>, ovvero un numero intero. Un controllo <xref:System.Windows.Forms.GroupBox> stesso non può avere lo stato attivo in fase di esecuzione. Pertanto, ogni controllo all'interno di un <xref:System.Windows.Forms.GroupBox> dispone di un proprio valore decimale <xref:System.Windows.Forms.Control.TabIndex%2A>, a partire da. 0. Naturalmente, quando viene incrementata la <xref:System.Windows.Forms.Control.TabIndex%2A> di un controllo <xref:System.Windows.Forms.GroupBox>, i controlli in esso contenuti verranno incrementati di conseguenza. Se è stato modificato un valore di <xref:System.Windows.Forms.Control.TabIndex%2A> compreso tra 5 e 6, il valore <xref:System.Windows.Forms.Control.TabIndex%2A> del primo controllo del gruppo viene modificato automaticamente in 6,0 e così via.

Infine, qualsiasi controllo dei molti sul form può essere ignorato nell'ordine di tabulazione. In genere, la pressione di Tab in successione in fase di esecuzione seleziona ogni controllo nell'ordine di tabulazione. Disattivando la proprietà <xref:System.Windows.Forms.Control.TabStop%2A>, è possibile passare un controllo nell'ordine di tabulazione del form.

## <a name="to-remove-a-control-from-the-tab-order"></a>Per rimuovere un controllo dall'ordine di tabulazione

Impostare la proprietà <xref:System.Windows.Forms.Control.TabStop%2A> del controllo su **false** nella finestra **Proprietà** .

Un controllo la cui proprietà <xref:System.Windows.Forms.Control.TabStop%2A> è stata impostata su `false` mantiene ancora la posizione nell'ordine di tabulazione, anche se il controllo viene ignorato quando si esegue il ciclo dei controlli con il tasto TAB.

> [!NOTE]
> Un gruppo di pulsanti di opzione ha una singola tabulazione in fase di esecuzione. Il pulsante selezionato, ovvero il pulsante con la proprietà <xref:System.Windows.Forms.RadioButton.Checked%2A> impostata su `true`, ha la proprietà <xref:System.Windows.Forms.Control.TabStop%2A> impostata automaticamente su `true`, mentre gli altri pulsanti hanno la proprietà <xref:System.Windows.Forms.Control.TabStop%2A> impostata su `false`. Per ulteriori informazioni sul raggruppamento di controlli <xref:System.Windows.Forms.RadioButton>, vedere [grouping Windows Forms RadioButton Controls to function as a set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
