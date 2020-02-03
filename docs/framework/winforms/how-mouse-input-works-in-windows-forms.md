---
title: Funzionamento dell'input del mouse
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
ms.openlocfilehash: 1164974e65ca1e96c0650569626ad4140baf004e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739630"
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Input del mouse in Windows Form
La ricezione e la gestione di input del mouse è una parte importante di ogni applicazione Windows. È possibile gestire gli eventi del mouse per eseguire un'azione nell'applicazione oppure utilizzare le informazioni sulla posizione del mouse per eseguire hit testing o altre azioni. Inoltre, è possibile modificare il modo in cui i controlli dell'applicazione gestiscono l'input del mouse. In questo argomento vengono descritti in dettaglio questi eventi del mouse e viene illustrato come ottenere e modificare le impostazioni di sistema per il mouse. Per ulteriori informazioni sui dati forniti con gli eventi del mouse e sull'ordine in cui vengono generati gli eventi click del mouse, vedere [eventi del mouse in Windows Forms](mouse-events-in-windows-forms.md).  
  
## <a name="mouse-location-and-hit-testing"></a>Posizione del mouse e hit testing  
 Quando l'utente sposta il mouse, il sistema operativo sposta il puntatore del mouse. Il puntatore del mouse contiene un singolo pixel, denominato area sensibile, che il sistema operativo tiene traccia e riconosce come posizione dell'indicatore di misura. Quando l'utente sposta il mouse o preme un pulsante del mouse, il <xref:System.Windows.Forms.Control> che contiene l'<xref:System.Windows.Forms.Cursor.HotSpot%2A> genera l'evento del mouse appropriato. È possibile ottenere la posizione corrente del mouse con la proprietà <xref:System.Windows.Forms.MouseEventArgs.Location%2A> della <xref:System.Windows.Forms.MouseEventArgs> quando si gestisce un evento del mouse o utilizzando la proprietà <xref:System.Windows.Forms.Cursor.Position%2A> della classe <xref:System.Windows.Forms.Cursor>. Successivamente, è possibile utilizzare le informazioni sulla posizione del mouse per eseguire hit testing, quindi eseguire un'azione in base alla posizione del mouse. La funzionalità di hit testing è incorporata in diversi controlli in Windows Forms, ad esempio i controlli <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> e <xref:System.Windows.Forms.DataGridView>. Utilizzato con l'evento del mouse appropriato, <xref:System.Windows.Forms.Control.MouseHover> ad esempio, hit testing è molto utile per determinare quando l'applicazione deve eseguire un'azione specifica.  
  
## <a name="mouse-events"></a>Eventi del mouse  
 Il modo principale per rispondere all'input del mouse è quello di gestire gli eventi del mouse. Nella tabella seguente vengono illustrati gli eventi del mouse e viene descritto quando vengono generati.  
  
|Evento del mouse|Descrizione|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|Questo evento si verifica quando viene rilasciato il pulsante del mouse, in genere prima dell'evento <xref:System.Windows.Forms.Control.MouseUp>. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>. Gestire questo evento quando è necessario determinare solo quando si verifica un clic.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Questo evento si verifica quando l'utente fa clic sul controllo con il mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>. Gestire questo evento quando è necessario ottenere informazioni sul mouse quando si verifica un clic.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Questo evento si verifica quando si fa doppio clic sul controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>. Gestire questo evento quando è necessario determinare solo quando si verifica un doppio clic.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Questo evento si verifica quando l'utente fa doppio clic sul controllo con il mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>. Gestire questo evento quando è necessario ottenere informazioni sul mouse quando si verifica un doppio clic.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Questo evento si verifica quando il puntatore del mouse si trova sul controllo e l'utente preme un pulsante del mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Questo evento si verifica quando il puntatore del mouse entra nel bordo o nell'area client del controllo, a seconda del tipo di controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Questo evento si verifica quando il puntatore del mouse si arresta e si posiziona sul controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Questo evento si verifica quando il puntatore del mouse esce dal bordo o dall'area client del controllo, a seconda del tipo del controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Questo evento si verifica quando il puntatore del mouse viene spostato mentre si trova su un controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Questo evento si verifica quando il puntatore del mouse si trova sul controllo e l'utente rilascia un pulsante del mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Questo evento si verifica quando l'utente ruota la rotellina del mouse mentre il controllo ha lo stato attivo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>. È possibile utilizzare la proprietà <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> di <xref:System.Windows.Forms.MouseEventArgs> per determinare la distanza con cui il mouse è stato spostato.|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>Modifica dell'input del mouse e rilevamento delle impostazioni di sistema  
 È possibile rilevare e modificare il modo in cui un controllo gestisce l'input del mouse derivando dal controllo e utilizzando i metodi <xref:System.Windows.Forms.Control.GetStyle%2A> e <xref:System.Windows.Forms.Control.SetStyle%2A>. Il metodo <xref:System.Windows.Forms.Control.SetStyle%2A> accetta una combinazione bit per bit dei valori <xref:System.Windows.Forms.ControlStyles> per determinare se il controllo avrà un comportamento di clic o doppio clic standard o se il controllo gestirà l'elaborazione del mouse. Inoltre, la classe <xref:System.Windows.Forms.SystemInformation> include proprietà che descrivono le funzionalità del mouse e specificano il modo in cui il mouse interagisce con il sistema operativo. Nella tabella seguente sono riepilogate queste proprietà.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Ottiene le dimensioni, in pixel, dell'area in cui l'utente deve fare clic due volte affinché il sistema operativo consideri i due clic come un doppio clic.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Ottiene il numero massimo di millisecondi che possono trascorrere tra un primo clic e un secondo clic affinché il sistema operativo consideri l'azione del mouse come un doppio clic.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Ottiene il numero di pulsanti del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Ottiene un valore che indica se le funzioni dei pulsanti sinistro e destro sono state invertite.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Ottiene le dimensioni, in pixel, del rettangolo all'interno del quale il puntatore del mouse deve rimanere per l'intervallo di tempo richiesto perché sia generato un messaggio visualizzato al passaggio del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Ottiene il tempo, in millisecondi, per il quale il puntatore del mouse deve soffermarsi nell'area rettangolare sensibile al passaggio del mouse prima che venga generato un messaggio.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Ottiene un valore che indica se è installato un mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Ottiene un valore che indica la velocità corrente del mouse, da 1 a 20.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Ottiene un valore che indica se è installato un mouse con rotellina del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Ottiene la quantità del valore Delta dell'incremento di una singola rotazione della rotellina del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Ottiene il numero di righe da scorrere quando viene ruotata la rotellina del mouse.|  
  
## <a name="see-also"></a>Vedere anche

- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
- [Mouse Capture in Windows Form](mouse-capture-in-windows-forms.md)
- [Puntatori del mouse in Windows Form](mouse-pointers-in-windows-forms.md)
