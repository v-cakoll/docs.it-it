---
title: 'Procedura: impostare l''ordine di tabulazione in Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d514b20381b44102076c776d12181df3838e4eaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Procedura: impostare l'ordine di tabulazione in Windows Form
Ordine di tabulazione è l'ordine in cui un utente si sposta lo stato attivo da un controllo a un altro premendo il tasto TAB. Ogni modulo contiene il proprio ordine di tabulazione. Per impostazione predefinita, l'ordine di tabulazione è lo stesso ordine in cui vengono creati i controlli. La numerazione dell'ordine di tabulazione inizia da zero.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-the-tab-order-of-a-control"></a>Per impostare l'ordine di tabulazione, di un controllo  
  
1.  Nel **vista** menu, fare clic su **ordine di tabulazione**.  
  
     Questa operazione attiva la modalità di selezione dell'ordine di tabulazione nel form. Un numero (che rappresenta il <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà) viene visualizzata nell'angolo superiore sinistro di ogni controllo.  
  
2.  Fare clic sui controlli in modo sequenziale per stabilire l'ordine di tabulazione desiderato.  
  
    > [!NOTE]
    >  Sul posto di un controllo all'interno dell'ordine di tabulazione possibile impostare qualsiasi valore maggiore o uguale a 0. Quando si verificano i duplicati, l'ordine z dei due controlli viene valutato e il controllo nella parte superiore viene assegnato la prima. (L'ordine z è l'ordine di disposizione visual dei controlli in un form lungo l'asse z del form [profondità]. L'ordine z determina quali controlli si trovano davanti altri controlli.) Per ulteriori informazioni sull'ordine z, vedere [disposizione di oggetti in Windows Form](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).  
  
3.  Al termine, fare clic su **ordine di tabulazione** sul **vista** menu per uscire dalla modalità di ordine di tabulazione.  
  
    > [!NOTE]
    >  I controlli che non è possibile ottenere lo stato attivo, nonché controlli invisibili e disabilitati, non sono un <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà e non vengono inclusi nell'ordine di tabulazione. Quando un utente preme il tasto TAB, questi controlli vengono ignorati.  
  
 In alternativa, è possibile impostare l'ordine di tabulazione nella finestra proprietà utilizzando il <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà. Il <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà di un controllo determina la posizione nell'ordine di tabulazione. Per impostazione predefinita, il primo controllo creato ha un <xref:System.Windows.Forms.Control.TabIndex%2A> valore pari a 0, il secondo è un <xref:System.Windows.Forms.Control.TabIndex%2A> 1 e così via.  
  
 Inoltre, per impostazione predefinita, un <xref:System.Windows.Forms.GroupBox> controllo dispone di una propria <xref:System.Windows.Forms.Control.TabIndex%2A> valore, ovvero un numero intero. Oggetto <xref:System.Windows.Forms.GroupBox> controllo stesso non può avere lo stato attivo in fase di esecuzione. Pertanto, ogni controllo all'interno di un <xref:System.Windows.Forms.GroupBox> ha un proprio decimale <xref:System.Windows.Forms.Control.TabIndex%2A> valore, che inizia con,0. Naturalmente, come il <xref:System.Windows.Forms.Control.TabIndex%2A> di un <xref:System.Windows.Forms.GroupBox> controllo viene incrementato, i controlli in esso contenuti verranno incrementati di conseguenza. Se è stato modificato un <xref:System.Windows.Forms.Control.TabIndex%2A> valore compreso tra 5 e 6, il <xref:System.Windows.Forms.Control.TabIndex%2A> valore del primo controllo in un gruppo viene automaticamente modificato in 6.0 e così via.  
  
 Infine, è possibile ignorare qualsiasi controllo presente nel form nell'ordine di tabulazione. In genere, premendo il tasto TAB successivamente in fase di esecuzione consente di selezionare ogni controllo nell'ordine di tabulazione. Disattivando il <xref:System.Windows.Forms.Control.TabStop%2A> proprietà, è possibile ignorare un controllo nell'ordine di tabulazione del form.  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a>Per rimuovere un controllo dall'ordine di tabulazione  
  
1.  Impostare il controllo <xref:System.Windows.Forms.Control.TabStop%2A> proprietà `false` nella finestra Proprietà.  
  
     Un controllo cui <xref:System.Windows.Forms.Control.TabStop%2A> è impostata su `false` ancora mantiene la propria posizione nell'ordine di tabulazione, anche se il controllo viene ignorato quando si passano attraverso i controlli con il tasto TAB.  
  
    > [!NOTE]
    >  Un gruppo di pulsanti di opzione ha una sola scheda di arrestare in fase di esecuzione. Pulsante selezionato (vale a dire, il pulsante con relativo <xref:System.Windows.Forms.RadioButton.Checked%2A> proprietà impostata su `true`) è relativo <xref:System.Windows.Forms.Control.TabStop%2A> proprietà impostata automaticamente su `true`, mentre per gli altri pulsanti loro <xref:System.Windows.Forms.Control.TabStop%2A> proprietà impostata su `false`. Per ulteriori informazioni sul raggruppamento <xref:System.Windows.Forms.RadioButton> controlli, vedere [raggruppare controlli RadioButton Windows Form per funzione come un Set](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)  
 [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controlli Windows Form per funzione](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
