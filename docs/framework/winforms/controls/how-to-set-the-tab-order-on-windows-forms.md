---
title: "Procedura: impostare l'ordine di tabulazione in Windows Form"
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
ms.openlocfilehash: 74244ae4e3692ed210b2a8f1513b035c85e98376
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486831"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Procedura: impostare l'ordine di tabulazione in Windows Form
L'ordine di tabulazione è l'ordine in cui un utente si sposta lo stato attivo da un controllo a un'altra premendo il tasto TAB. Ogni modulo contiene un proprio ordine di tabulazione. Per impostazione predefinita, l'ordine di tabulazione è lo stesso l'ordine in cui sono stati creati i controlli. Ordine di tabulazione la numerazione inizia da zero.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-tab-order-of-a-control"></a>Per impostare l'ordine di tabulazione di un controllo  
  
1.  Nel **View** menu, fare clic su **ordine di tabulazione**.  
  
     Questa operazione attiva la modalità di selezione dell'ordine di tabulazione nel form. Un numero (che rappresenta il <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà) visualizzato nell'angolo in alto a sinistra di ogni controllo.  
  
2.  Scegliere i controlli in modo sequenziale per stabilire l'ordine di tabulazione desiderato.  
  
    > [!NOTE]
    >  Posizione di un controllo all'interno dell'ordine di tabulazione possibile impostare su qualsiasi valore maggiore o uguale a 0. Quando si verificano i duplicati, l'ordine z dei due controlli viene valutata e il controllo nella parte superiore a schede per primo. (Nell'ordine z è disposizione visiva di controlli in un form insieme all'asse z del form [profondità]. L'ordine z determina quali controlli vengono prima di altri controlli.) Per altre informazioni sull'ordine z, vedere [disposizione di oggetti in Windows Form](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).  
  
3.  Al termine, fare clic su **ordine di tabulazione** nel **visualizzazione** menu nuovo per uscire dalla modalità di ordine di tabulazione.  
  
    > [!NOTE]
    >  I controlli che non è possibile ottenere lo stato attivo, nonché controlli disabilitati e invisibili, non è un <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà e non vengono inclusi nell'ordine di tabulazione. Quando un utente preme il tasto TAB, questi controlli vengono ignorati.  
  
 In alternativa, è possibile impostare l'ordine di tabulazione nella finestra proprietà utilizzando il <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà. Il <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà di un controllo determina la posizione nell'ordine di tabulazione. Per impostazione predefinita, il primo controllo creato ha un <xref:System.Windows.Forms.Control.TabIndex%2A> valore pari a 0, il secondo contiene un <xref:System.Windows.Forms.Control.TabIndex%2A> 1 e così via.  
  
 Inoltre, per impostazione predefinita, un <xref:System.Windows.Forms.GroupBox> controllo ha un proprio <xref:System.Windows.Forms.Control.TabIndex%2A> valore, ovvero un numero intero. Oggetto <xref:System.Windows.Forms.GroupBox> controllo stesso non può avere lo stato attivo in fase di esecuzione. Di conseguenza, ogni controllo all'interno di un <xref:System.Windows.Forms.GroupBox> ha un proprio decimale <xref:System.Windows.Forms.Control.TabIndex%2A> valore, che inizia con,0. Naturalmente, come le <xref:System.Windows.Forms.Control.TabIndex%2A> di un <xref:System.Windows.Forms.GroupBox> controllo viene incrementato, verranno incrementati di conseguenza i controlli in esso contenuti. Se è stata modificata una <xref:System.Windows.Forms.Control.TabIndex%2A> valore compreso tra 5 e 6, la <xref:System.Windows.Forms.Control.TabIndex%2A> valore del primo controllo in un gruppo viene automaticamente modificato in 6.0 e così via.  
  
 Infine, qualsiasi controllo presente sul form può essere ignorato nell'ordine di tabulazione. In genere, preme TAB in successione in fase di esecuzione consente di selezionare ogni controllo nell'ordine di tabulazione. Disattivando il <xref:System.Windows.Forms.Control.TabStop%2A> proprietà, è possibile apportare un controllo venga trasmessa nell'ordine di tabulazione del form.  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a>Per rimuovere un controllo dall'ordine di tabulazione  
  
1.  Impostare il controllo <xref:System.Windows.Forms.Control.TabStop%2A> proprietà `false` nella finestra Proprietà.  
  
     Controllare l'oggetto la cui proprietà <xref:System.Windows.Forms.Control.TabStop%2A> proprietà è stata impostata `false` ancora mantiene la propria posizione nell'ordine di tabulazione, anche se il controllo viene ignorato quando si passano tra i controlli con il tasto TAB.  
  
    > [!NOTE]
    >  Un gruppo di pulsanti di opzione ha una sola scheda di arrestare in fase di esecuzione. Il pulsante selezionato (, ovvero il pulsante con relativo <xref:System.Windows.Forms.RadioButton.Checked%2A> proprietà impostata su `true`) è relativo <xref:System.Windows.Forms.Control.TabStop%2A> automaticamente impostata su `true`, mentre per gli altri pulsanti relativi <xref:System.Windows.Forms.Control.TabStop%2A> proprietà impostata su `false`. Per altre informazioni sul raggruppamento <xref:System.Windows.Forms.RadioButton> controlli, vedere [raggruppamento controlli RadioButton Windows Form alla funzione come un Set](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)  
 [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controlli Windows Form per funzione](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
