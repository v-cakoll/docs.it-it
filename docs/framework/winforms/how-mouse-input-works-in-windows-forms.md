---
title: Input del mouse in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
ms.openlocfilehash: 7817b6a414f313cd2891fe0e124e230643b06e07
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725325"
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Input del mouse in Windows Form
Ricevere e gestire l'input del mouse è una parte importante di tutte le applicazioni Windows. È possibile gestire gli eventi del mouse per eseguire un'azione nell'applicazione o usare informazioni sulla posizione del mouse per eseguire l'hit testing o altre azioni. Inoltre, è possibile modificare il modo in cui i controlli nell'applicazione gestiscono l'input del mouse. Questo argomento descrive questi eventi mouse in modo dettagliato e su come ottenere e modificare le impostazioni di sistema per il puntatore del mouse. Per altre informazioni sui dati forniti con il mouse vengono generati gli eventi e l'ordine in cui il puntatore del mouse, fare clic su eventi, vedere [eventi Mouse in Windows Form](mouse-events-in-windows-forms.md).  
  
## <a name="mouse-location-and-hit-testing"></a>Posizione del mouse e Hit Testing  
 Quando l'utente sposta il puntatore del mouse, il sistema operativo passa il puntatore del mouse. Il puntatore del mouse contiene un singolo pixel, chiamato l'area sensibile, che il sistema operativo tiene traccia e riconosce come la posizione del puntatore. Quando l'utente sposta il mouse o preme un pulsante del mouse, il <xref:System.Windows.Forms.Control> che contiene il <xref:System.Windows.Forms.Cursor.HotSpot%2A> genera l'evento del mouse appropriato. È possibile ottenere la posizione corrente del mouse con il <xref:System.Windows.Forms.MouseEventArgs.Location%2A> proprietà del <xref:System.Windows.Forms.MouseEventArgs> quando si gestisce un evento del mouse o tramite il <xref:System.Windows.Forms.Cursor.Position%2A> proprietà del <xref:System.Windows.Forms.Cursor> classe. È possibile usare successivamente le informazioni sulla posizione del mouse per eseguire l'hit testing e quindi eseguire un'azione in base alla posizione del mouse. Funzionalità di hit testing è incorporata vari controlli in Windows Form, ad esempio la <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> e <xref:System.Windows.Forms.DataGridView> controlli. Utilizzato con l'evento del mouse appropriato, <xref:System.Windows.Forms.Control.MouseHover> ad esempio, eseguire l'hit testing è molto utile per determinare quando l'applicazione deve eseguire un'azione specifica.  
  
## <a name="mouse-events"></a>Eventi del mouse  
 Il modo principale per rispondere all'input del mouse è per gestire gli eventi del mouse. Nella tabella seguente mostra gli eventi di mouse e descrive quando vengono generati.  
  
|Evento del mouse|Descrizione|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|Questo evento si verifica quando viene rilasciato il pulsante del mouse, in genere prima il <xref:System.Windows.Forms.Control.MouseUp> evento. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>. Gestire questo evento quando ti servono solamente determinare quando si verifica un clic.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Questo evento si verifica quando l'utente fa clic con il mouse il controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>. Gestire questo evento quando è necessario ottenere informazioni sul mouse quando si verifica un clic.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Questo evento si verifica quando si fa doppio clic sul controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>. Gestire questo evento quando ti servono solamente determinare quando si verifica un doppio clic.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Questo evento si verifica quando l'utente fa doppio clic con il controllo con il mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>. Gestire questo evento quando è necessario ottenere informazioni sul mouse quando si verifica un doppio clic.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Questo evento si verifica quando il puntatore del mouse è posizionato sopra il controllo e l'utente preme un pulsante del mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Questo evento si verifica quando il puntatore del mouse entra nell'area client o del bordo del controllo, a seconda del tipo di controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Questo evento si verifica quando il puntatore del mouse si arresta e si sofferma sul controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Questo evento si verifica quando il puntatore del mouse esce dall'area del bordo o un client del controllo, a seconda del tipo del controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Questo evento si verifica quando il puntatore del mouse viene spostato mentre si trova su un controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Questo evento si verifica quando il puntatore del mouse è posizionato sopra il controllo e l'utente rilascia un pulsante del mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Questo evento si verifica quando l'utente ruota la rotellina del mouse mentre il controllo ha lo stato attivo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>. È possibile usare la <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> proprietà di <xref:System.Windows.Forms.MouseEventArgs> determinare fino a quando è stata fatta scorrere il puntatore del mouse.|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>Modificando l'Input del Mouse e rilevare le impostazioni di sistema  
 È possibile rilevare e modificare il modo in cui un controllo gestisce l'input del mouse che deriva dal controllo e usando il <xref:System.Windows.Forms.Control.GetStyle%2A> e <xref:System.Windows.Forms.Control.SetStyle%2A> metodi. Il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo accetta una combinazione bit per bit di <xref:System.Windows.Forms.ControlStyles> i valori per determinare se il controllo avrà standard fare clic o fare doppio clic sul comportamento o se il controllo gestirà la propria elaborazione del mouse. Inoltre, il <xref:System.Windows.Forms.SystemInformation> classe include proprietà che descrivono le funzionalità del mouse e specificare la modalità di interazione del mouse con il sistema operativo. Nella tabella seguente sono riepilogate queste proprietà.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Ottiene le dimensioni, in pixel, dell'area in cui l'utente deve fare clic due volte per il sistema operativo consideri i due clic come un doppio clic.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Ottiene il numero massimo di millisecondi che può trascorrere tra il primo e secondo clic affinché il sistema operativo consideri l'azione del mouse un doppio clic.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Ottiene il numero di pulsanti del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Ottiene un valore che indica se le funzioni dei pulsanti sinistro e destro sono state invertite.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Ottiene le dimensioni, in pixel, del rettangolo all'interno del quale il puntatore del mouse deve rimanere per l'intervallo di tempo richiesto perché sia generato un messaggio visualizzato al passaggio del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Ottiene il tempo, in millisecondi, per il quale il puntatore del mouse deve soffermarsi nell'area rettangolare sensibile al passaggio del mouse prima che venga generato un messaggio.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Ottiene un valore che indica se è installato un mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Ottiene un valore che indica la velocità del mouse corrente, da 1 a 20.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Ottiene un valore che indica se è installato un mouse con rotellina del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Ottiene la quantità del valore delta dell'incremento di una rotazione della rotellina del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Ottiene il numero di righe da scorrere quando viene ruotata la rotellina del mouse.|  
  
## <a name="see-also"></a>Vedere anche
- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
- [Mouse Capture in Windows Form](mouse-capture-in-windows-forms.md)
- [Puntatori del mouse in Windows Form](mouse-pointers-in-windows-forms.md)
