---
title: Imposta ordine di tabulazione dei controlli
description: Informazioni su come impostare l'ordine di tabulazione dei controlli nella Windows Forms. Impostare l'ordine di tabulazione con Visual Studio o usando la proprietà TabIndex nell'Finestra Proprietà.
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
ms.openlocfilehash: 3d16da1ac73cc030b92bb36c4bfa3a79985339bf
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903362"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Procedura: impostare l'ordine di tabulazione in Windows Forms

L'ordine di tabulazione è l'ordine in cui un utente sposta lo stato attivo da un controllo a un altro premendo il tasto TAB. Ogni form ha un proprio ordine di tabulazione. Per impostazione predefinita, l'ordine di tabulazione corrisponde all'ordine in cui sono stati creati i controlli. La numerazione dell'ordine di tabulazione inizia con zero.

## <a name="to-set-the-tab-order-of-a-control"></a>Per impostare l'ordine di tabulazione di un controllo

1. In Visual Studio scegliere **ordine di tabulazione**dal menu **Visualizza** .

   In questo modo viene attivata la modalità di selezione dell'ordine di tabulazione nel form. Un numero (che rappresenta la <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà) viene visualizzato nell'angolo superiore sinistro di ogni controllo.

2. Fare clic sui controlli in sequenza per stabilire l'ordine di tabulazione desiderato.

   > [!NOTE]
   > La posizione di un controllo all'interno dell'ordine di tabulazione può essere impostata su qualsiasi valore maggiore o uguale a 0. Quando si verificano duplicati, l'ordine z dei due controlli viene valutato e il controllo nella parte superiore viene a schede per primo. (L'ordine z è il livello visivo dei controlli in un form lungo l'asse z del form [Depth]. L'ordine z determina i controlli che si trovano davanti ad altri controlli. Per ulteriori informazioni sull'ordine z, vedere la pagina relativa ai [livelli di oggetti su Windows Forms](how-to-layer-objects-on-windows-forms.md).

3. Al termine, selezionare di nuovo **ordine di tabulazione** dal menu **Visualizza** per lasciare la modalità ordine di tabulazione.

   > [!NOTE]
   > I controlli che non possono ottenere lo stato attivo, nonché i controlli disabilitati e invisibili, non hanno una <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà e non sono inclusi nell'ordine di tabulazione. Quando un utente preme il tasto TAB, questi controlli vengono ignorati.

In alternativa, è possibile impostare l'ordine di tabulazione nell'Finestra Proprietà utilizzando la <xref:System.Windows.Forms.Control.TabIndex%2A> Proprietà. La <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà di un controllo determina la posizione in cui è posizionata nell'ordine di tabulazione. Per impostazione predefinita, il primo controllo disegnato ha un <xref:System.Windows.Forms.Control.TabIndex%2A> valore pari a 0, il secondo ha un valore <xref:System.Windows.Forms.Control.TabIndex%2A> pari a 1 e così via.

Inoltre, per impostazione predefinita, un <xref:System.Windows.Forms.GroupBox> controllo ha un proprio <xref:System.Windows.Forms.Control.TabIndex%2A> valore, ovvero un numero intero. Un <xref:System.Windows.Forms.GroupBox> controllo non può avere lo stato attivo in fase di esecuzione. Pertanto, ogni controllo all'interno di un oggetto <xref:System.Windows.Forms.GroupBox> ha un proprio valore decimale <xref:System.Windows.Forms.Control.TabIndex%2A> , a partire da. 0. Naturalmente, quando l'oggetto <xref:System.Windows.Forms.Control.TabIndex%2A> di un <xref:System.Windows.Forms.GroupBox> controllo viene incrementato, i controlli in esso contenuti verranno incrementati di conseguenza. Se è stato modificato un <xref:System.Windows.Forms.Control.TabIndex%2A> valore compreso tra 5 e 6, il <xref:System.Windows.Forms.Control.TabIndex%2A> valore del primo controllo del gruppo viene automaticamente modificato in 6,0 e così via.

Infine, qualsiasi controllo dei molti sul form può essere ignorato nell'ordine di tabulazione. In genere, la pressione di Tab in successione in fase di esecuzione seleziona ogni controllo nell'ordine di tabulazione. Disattivando la <xref:System.Windows.Forms.Control.TabStop%2A> proprietà, è possibile passare un controllo nell'ordine di tabulazione del form.

## <a name="to-remove-a-control-from-the-tab-order"></a>Per rimuovere un controllo dall'ordine di tabulazione

Impostare la proprietà del controllo <xref:System.Windows.Forms.Control.TabStop%2A> su **false** nella finestra **proprietà** .

Un controllo la cui <xref:System.Windows.Forms.Control.TabStop%2A> proprietà è stata impostata su `false` mantiene ancora la posizione nell'ordine di tabulazione, anche se il controllo viene ignorato quando si scorre il controllo con il tasto TAB.

> [!NOTE]
> Un gruppo di pulsanti di opzione ha una singola tabulazione in fase di esecuzione. Il pulsante selezionato (ovvero il pulsante con la relativa <xref:System.Windows.Forms.RadioButton.Checked%2A> proprietà impostata su `true` ) dispone automaticamente della <xref:System.Windows.Forms.Control.TabStop%2A> proprietà impostata su `true` , mentre gli altri pulsanti hanno la <xref:System.Windows.Forms.Control.TabStop%2A> proprietà impostata su `false` . Per ulteriori informazioni sul raggruppamento di <xref:System.Windows.Forms.RadioButton> controlli, vedere [raggruppamento Windows Forms controlli RadioButton per funzionare come un set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).

## <a name="see-also"></a>Vedere anche

- [Controlli di Windows Forms](index.md)
- [Controlli da utilizzare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
