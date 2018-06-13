---
title: 'Procedura dettagliata: disposizione dei controlli in Windows Form utilizzando guide di allineamento'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: f8e8122f82bc6a8c4fab17b8b73c07d08bab4d26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541590"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a>Procedura dettagliata: disposizione dei controlli in Windows Form utilizzando guide di allineamento
Per molte applicazioni è estremamente importante la sistemazione precisa dei controlli nel form. Progettazione Windows Form offre diversi strumenti di layout a questo scopo. Uno dei più importanti è la <xref:System.Windows.Forms.Design.Behavior.SnapLine> funzionalità.  
  
 Le guide di allineamento mostrano precisamente dove allineare i controlli con altri controlli. E visualizzano le distanze consigliate per i margini tra i controlli, come specificato dalle linee guida dell'interfaccia utente di Windows. Per informazioni dettagliate, vedere [progettazione dell'interfaccia utente e lo sviluppo](http://go.microsoft.com/FWLink/?LinkId=83878).  
  
 Le guide di allineamento semplificano l'allineamento dei controlli, consentono di ottenere, professional aspetto e il comportamento (aspetto).  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione di un progetto Windows Form  
  
-   La spaziatura e allineamento di controlli utilizzando le guide di allineamento  
  
-   Allineamento dei Form e i margini di contenitore  
  
-   Allineamento di controlli raggruppati  
  
-   Utilizzando le guide di allineamento per posizionare un controllo definendone la dimensione  
  
-   Utilizzando le guide di allineamento quando si trascina un controllo dalla casella degli strumenti  
  
-   Ridimensionamento di controlli utilizzando le guide di allineamento  
  
-   Allineamento di un'etichetta di testo di un controllo  
  
-   Utilizzando le guide di allineamento con navigazione tramite tastiera  
  
-   Le guide di allineamento e i pannelli di Layout  
  
-   La disabilitazione di guide di allineamento  
  
 Al termine, si avrà una migliore comprensione del ruolo del layout riprodotto di allineamento.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un progetto di applicazione basata su Windows denominato "SnaplineExample". Per informazioni dettagliate, vedere [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Selezionare il form in Progettazione form.  
  
## <a name="spacing-and-aligning-controls-using-snaplines"></a>La spaziatura e allineamento di controlli utilizzando le guide di allineamento  
 Le guide di allineamento offrono un modo accurato e intuitivo per allineare i controlli nel form. Vengono visualizzati quando si desidera spostare uno o più controlli selezionati prossimità allineamento con un altro controllo o un set di controlli. La selezione verrà "bloccata" nella posizione suggerita lo spostamento oltre gli altri controlli.  
  
#### <a name="to-arrange-controls-using-snaplines"></a>Per disporre i controlli usando le guide di allineamento  
  
1.  Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nel form.  
  
2.  Spostare il <xref:System.Windows.Forms.Button> controllo nell'angolo in basso a destra del form. Le guide di allineamento che appaiono come il <xref:System.Windows.Forms.Button> controllo si avvicina ai bordi inferiore e destro del form. Tali guide indicano la distanza consigliata tra i bordi del controllo e il modulo.  
  
3.  Spostare il <xref:System.Windows.Forms.Button> controllo intorno ai bordi del form e notare dove vengono visualizzate le guide di allineamento. Al termine, spostare il <xref:System.Windows.Forms.Button> controllo vicino al centro della forma.  
  
4.  Trascinare un'altra <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nel form.  
  
5.  Spostare il secondo <xref:System.Windows.Forms.Button> controllare fino a quando non è quasi allineato al primo. Si noti la Guida di allineamento che appare in linea di base di testo di entrambi i pulsanti e il controllo che si sta spostando si blocca in una posizione che è perfettamente allineata con l'altro controllo.  
  
6.  Spostare il secondo <xref:System.Windows.Forms.Button> controllare fino a quando non è posizionato direttamente sopra il primo. Tenere presente le guide di allineamento che appaiono lungo i bordi sinistro e destro di entrambi i pulsanti e si noti che il controllo sta spostando si blocca in una posizione che è perfettamente allineata con l'altro controllo.  
  
7.  Selezionare una del <xref:System.Windows.Forms.Button> controlla e spostarlo accanto a altro, fino a quando non si stanno pressoché toccando. Si noti la Guida di allineamento che viene visualizzato tra di essi. La distanza è la distanza consigliata tra i bordi dei controlli. Si noti inoltre che il controllo a cui che si sta spostando si blocca in questa posizione.  
  
8.  Trascinare due <xref:System.Windows.Forms.Panel> dei controlli di **della casella degli strumenti** nel form.  
  
9. Spostare una del <xref:System.Windows.Forms.Panel> controlla fino a quando non è quasi allineato al primo. Tenere presente le guide di allineamento che appaiono lungo i bordi superiore e inferiore di entrambi i controlli e il controllo che si sta spostando si blocca in una posizione che è perfettamente allineata con l'altro controllo.  
  
## <a name="aligning-to-form-and-container-margins"></a>Allineamento dei Form e i margini di contenitore  
 Le guide di allineamento consentono di allineare i controlli ai margini del form e contenitore in modo coerente.  
  
#### <a name="to-align-controls-to-form-and-container-margins"></a>Per allineare i controlli per i margini del form e contenitore  
  
1.  Selezionare una del <xref:System.Windows.Forms.Button> controlla e spostarlo vicino al bordo destro del form, finché non viene visualizzata una Guida di allineamento. Distanza della Guida di allineamento dal bordo destro è la somma del controllo <xref:System.Windows.Forms.Control.Margin%2A> proprietà e il modulo <xref:System.Windows.Forms.Control.Padding%2A> i valori delle proprietà.  
  
> [!NOTE]
>  Se il modulo <xref:System.Windows.Forms.Control.Padding%2A> è impostata su 0,0,0,0, Progettazione Windows Form viene assegnato al form un <xref:System.Windows.Forms.Control.Padding%2A> valore 9,9,9,9. Per eseguire l'override di questo comportamento, assegnare un valore diverso da 0,0,0,0.  
  
1.  Modificare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Margin%2A> espandendo il <xref:System.Windows.Forms.Control.Margin%2A> voce il **proprietà** finestra e impostando il <xref:System.Windows.Forms.Padding.All%2A> proprietà su 0. Per informazioni dettagliate, vedere [procedura dettagliata: disposizione di controlli Windows Form usando spaziatura, margini e la proprietà AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md).  
  
2.  Spostare il <xref:System.Windows.Forms.Button> controllo vicino al bordo destro del form fino a quando non viene visualizzata una Guida di allineamento. La distanza è ora stabilita dal valore nel formato <xref:System.Windows.Forms.Control.Padding%2A> proprietà.  
  
3.  Trascinare un <xref:System.Windows.Forms.GroupBox> controllo il **della casella degli strumenti** nel form.  
  
4.  Modificare il valore del <xref:System.Windows.Forms.GroupBox> del controllo <xref:System.Windows.Forms.Control.Padding%2A> espandendo il <xref:System.Windows.Forms.Control.Padding%2A> voce il **proprietà** finestra e impostando il <xref:System.Windows.Forms.Padding.All%2A> proprietà a 10.  
  
5.  Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nel <xref:System.Windows.Forms.GroupBox> controllo.  
  
6.  Spostare il <xref:System.Windows.Forms.Button> controllo vicino al bordo destro del <xref:System.Windows.Forms.GroupBox> controllo finché non viene visualizzata una Guida di allineamento. Spostare il <xref:System.Windows.Forms.Button> controllo all'interno di <xref:System.Windows.Forms.GroupBox> controllo e osservare dove vengono visualizzate le guide di allineamento.  
  
## <a name="aligning-to-grouped-controls"></a>Allineamento di controlli raggruppati  
 È possibile utilizzare le guide di allineamento per allineare i controlli raggruppati nonché i controlli all'interno di un <xref:System.Windows.Forms.GroupBox> controllo.  
  
#### <a name="to-align-to-grouped-controls"></a>Per allineare i controlli raggruppati  
  
1.  Selezionare due controlli nel form. Spostare la selezione e le guide di allineamento che appaiono tra la selezione e gli altri controlli.  
  
2.  Trascinare un <xref:System.Windows.Forms.GroupBox> controllo il **della casella degli strumenti** nel form.  
  
3.  Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nel <xref:System.Windows.Forms.GroupBox> controllo.  
  
4.  Selezionare una del <xref:System.Windows.Forms.Button> controlla e spostarlo all'interno di <xref:System.Windows.Forms.GroupBox> controllo. Le guide di allineamento che vengono visualizzati i bordi del <xref:System.Windows.Forms.GroupBox> controllo. Si noti inoltre le guide di allineamento vengono visualizzati i bordi del <xref:System.Windows.Forms.Button> controllo che è contenuto il <xref:System.Windows.Forms.GroupBox> controllo. I controlli figlio di un controllo contenitore supportano anche le guide di allineamento.  
  
## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a>Utilizzando le guide di allineamento per posizionare un controllo definendone la dimensione  
 Le guide di allineamento consentono di che allineare controlla quando vengono innanzitutto posizionate su un form.  
  
#### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a>Utilizzare le guide di allineamento per posizionare un controllo definendone la dimensione  
  
1.  Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.Button> . Non trascinarla nel form.  
  
2.  Spostare il puntatore del mouse sull'area di progettazione del form. Osservare che il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.Button> associata. Si noti inoltre le guide di allineamento che appaiono per indicare le posizioni allineate per i <xref:System.Windows.Forms.Button> controllo.  
  
3.  Fare clic e tenere premuto il pulsante del mouse.  
  
4.  Trascinare il puntatore del mouse intorno al form. Si noti che viene disegnata una struttura, che indica la posizione e le dimensioni del controllo.  
  
5.  Trascinare il puntatore fino a quando non in linea con un altro controllo nel form. Si noti che viene visualizzata una Guida di allineamento per indicare l'allineamento.  
  
6.  Rilasciare il pulsante del mouse. Il controllo viene creato nella posizione e dimensioni indicate dalla struttura.  
  
## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a>Utilizzando le guide di allineamento quando si trascina un controllo dalla casella degli strumenti  
 Le guide di allineamento consentono di allineare controlla quando si trascina il **della casella degli strumenti** nel form.  
  
#### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a>Utilizzare le guide di allineamento quando si trascina un controllo dalla casella degli strumenti  
  
1.  Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nel form, senza rilasciare il pulsante del mouse.  
  
2.  Spostare il puntatore del mouse sull'area di progettazione del form. Si noti che il puntatore del mouse cambia per indicare la posizione in cui il nuovo <xref:System.Windows.Forms.Button> controllo verrà creato.  
  
3.  Trascinare il puntatore del mouse intorno al form. Le guide di allineamento che appaiono per indicare le posizioni allineate per i <xref:System.Windows.Forms.Button> controllo. Cercare una posizione che è allineata con altri controlli.  
  
4.  Rilasciare il pulsante del mouse. Il controllo viene creato nella posizione indicata dalle guide di allineamento.  
  
## <a name="resizing-controls-using-snaplines"></a>Ridimensionamento di controlli utilizzando le guide di allineamento  
 Le guide di allineamento consentono di allineare i controlli durante il ridimensionamento.  
  
#### <a name="to-resize-a-control-using-snaplines"></a>Per ridimensionare un controllo utilizzando le guide di allineamento  
  
1.  Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nel form.  
  
2.  Ridimensionare il <xref:System.Windows.Forms.Button> controllo agganciando uno dei quadratini di ridimensionamento e trascinandolo. Per informazioni dettagliate, vedere [procedura: ridimensionare i controlli in Windows Form](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md).  
  
3.  Trascinare il quadratino di ridimensionamento fino a quando una del <xref:System.Windows.Forms.Button> bordi del controllo è allineato con un altro controllo. Si noti che viene visualizzata una Guida di allineamento. Si noti inoltre che il quadratino di ridimensionamento si blocca nella posizione indicata dalla Guida di allineamento.  
  
4.  Ridimensionare il <xref:System.Windows.Forms.Button> controllo in diverse direzioni e allineare il quadratino di ridimensionamento di controlli diversi. Si noti come le guide di allineamento vengono visualizzati in diverse direzioni per indicare l'allineamento.  
  
## <a name="aligning-a-label-to-a-controls-text"></a>Allineamento di un'etichetta di testo di un controllo  
 Alcuni controlli offrono una Guida di allineamento per allineare il testo visualizzato degli altri controlli.  
  
#### <a name="to-align-a-label-to-a-controls-text"></a>Per allineare un'etichetta di testo di un controllo  
  
1.  Trascinare un <xref:System.Windows.Forms.TextBox> controllo il **della casella degli strumenti** nel form. Quando si trascina il <xref:System.Windows.Forms.TextBox> controllo nel form, fare clic sul glifo dello smart tag e selezionare il **impostare testo textBox1** opzione. Per informazioni dettagliate, vedere [procedura dettagliata: esecuzione di comuni attività utilizzando gli Smart tag nei controlli Windows Form](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md).  
  
2.  Trascinare un <xref:System.Windows.Forms.Label> controllo il **della casella degli strumenti** nel form.  
  
3.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Label>, <xref:System.Windows.Forms.Control.AutoSize%2A>, su `true`. Si noti che i bordi del controllo vengono regolati per adattarsi al testo visualizzato.  
  
4.  Spostare il <xref:System.Windows.Forms.Label> controllo a sinistra del <xref:System.Windows.Forms.TextBox> controllare, in modo che sia allineato al bordo inferiore del <xref:System.Windows.Forms.TextBox> controllo. Si noti la Guida di allineamento che viene visualizzato lungo il bordo inferiore dei due controlli.  
  
5.  Spostare il <xref:System.Windows.Forms.Label> controllo leggermente verso l'alto, finché il <xref:System.Windows.Forms.Label> testo e <xref:System.Windows.Forms.TextBox> testo sono allineate. Si noti la Guida di allineamento in uno stile differente viene visualizzato un messaggio quando i campi di testo di entrambi i controlli sono allineati.  
  
## <a name="using-snaplines-with-keyboard-navigation"></a>Utilizzando le guide di allineamento con navigazione tramite tastiera  
 Le guide di allineamento consentono di che allineare controlla quando vengono disposti utilizzando i tasti di direzione della tastiera.  
  
#### <a name="to-use-snaplines-with-keyboard-navigation"></a>Per utilizzare le guide di allineamento con navigazione tramite tastiera  
  
1.  Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nel form. Inserirlo nell'angolo superiore sinistro del form.  
  
2.  Premere CTRL + freccia giù. Si noti che il controllo viene spostato verso il basso il modulo nella prima posizione di allineamento orizzontale disponibile.  
  
3.  Premere CTRL + freccia GIÙ fino a quando il controllo raggiunge la fine del form. Tenere presente le posizioni occupate mentre vengono spostati verso il basso il modulo.  
  
4.  Premere CTRL + freccia destra. Si noti che il controllo viene spostato nel form per la prima posizione di allineamento verticale disponibili.  
  
5.  Premere CTRL + freccia destra fino a quando il controllo raggiunge il lato del form. Tenere presente le posizioni occupate mentre si sposta tra il modulo.  
  
6.  Spostare il controllo nel form con una combinazione di tasti di direzione. Si notino le posizioni che occupate dal controllo e le guide di allineamento che li accompagnano.  
  
7.  Premere MAIUSC + qualsiasi tasto di direzione per ridimensionare il <xref:System.Windows.Forms.Button> controllo in incrementi di un pixel.  
  
8.  Premere CTRL + MAIUSC + qualsiasi tasto di direzione per ridimensionare il <xref:System.Windows.Forms.Button> controllo in incrementi di Guida di allineamento.  
  
## <a name="snaplines-and-layout-panels"></a>Le guide di allineamento e i pannelli di Layout  
 Le guide di allineamento sono disabilitate in altri pannelli layout.  
  
#### <a name="to-selectively-disable-snaplines"></a>Per disabilitare selettivamente le guide di allineamento  
  
1.  Trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo il **della casella degli strumenti** nel form.  
  
2.  Fare doppio clic sull'icona del controllo <xref:System.Windows.Forms.Button> nella **Casella degli strumenti**. Viene visualizzato un pulsante nuovo nel <xref:System.Windows.Forms.TableLayoutPanel> prima cella del controllo.  
  
3.  Fare doppio clic su di <xref:System.Windows.Forms.Button> icona controllo il **della casella degli strumenti** altre due volte. In questo modo, una cella vuota nel <xref:System.Windows.Forms.TableLayoutPanel> controllo.  
  
4.  Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nella cella vuota del <xref:System.Windows.Forms.TableLayoutPanel> controllo. Si noti che non le guide di allineamento vengono visualizzati.  
  
5.  Trascinare il <xref:System.Windows.Forms.Button> controllare fuori il <xref:System.Windows.Forms.TableLayoutPanel> controllare e spostarlo il <xref:System.Windows.Forms.TableLayoutPanel> controllo. Si noti che le guide di allineamento vengono visualizzati di nuovo.  
  
## <a name="disabling-snaplines"></a>La disabilitazione di guide di allineamento  
 Le guide di allineamento sono attivate per impostazione predefinita. È possibile disabilitare in modo selettivo le guide di allineamento, oppure è possibile disabilitarli nell'ambiente di progettazione.  
  
#### <a name="to-selectively-disable-snaplines"></a>Per disabilitare selettivamente le guide di allineamento  
  
-   Premere il tasto ALT mentre si sposta un controllo nel form.  
  
     Si noti che non le guide di allineamento vengono visualizzati e il controllo si blocca in qualsiasi posizione di allineamento potenziale.  
  
#### <a name="to-disable-snaplines-in-the-design-environment"></a>Per disabilitare le guide di allineamento nell'ambiente di progettazione  
  
1.  Dal **strumenti** menu, aprire il **opzioni** la finestra di dialogo. Aprire la finestra di dialogo Progettazione Windows Form. Per informazioni dettagliate, vedere [generale, Progettazione Windows Form, la finestra di dialogo Opzioni](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).  
  
2.  Selezionare il **generale** nodo. Nel **modalità Layout** sezione, modificare la selezione da **le guide di allineamento** a **SnapToGrid**.  
  
3.  Fare clic su OK per applicare l'impostazione.  
  
4.  Selezionare un controllo sul form e spostarlo all'interno di altri controlli. Si noti che non vengono visualizzate le guide di allineamento.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Le guide di allineamento offrono modalità intuitive per l'allineamento dei controlli sul form. Per approfondire l'argomento, si consiglia di effettuare le seguenti operazioni:  
  
-   Provare a annidare un <xref:System.Windows.Forms.GroupBox> controllo all'interno di altra <xref:System.Windows.Forms.GroupBox> controllo. Sul posto un <xref:System.Windows.Forms.Button> controllo all'interno del figlio <xref:System.Windows.Forms.GroupBox> controllo e un altro nel controllo padre <xref:System.Windows.Forms.GroupBox> controllo. Spostare il <xref:System.Windows.Forms.Button> controlli per vedere come le guide di allineamento attraversano i limiti del contenitore.  
  
-   Creare una colonna di <xref:System.Windows.Forms.TextBox> controlli e una colonna corrispondente della <xref:System.Windows.Forms.Label> controlli. Impostare il valore della <xref:System.Windows.Forms.Label> dei controlli <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà `true`. Utilizzare le guide di allineamento per spostare il <xref:System.Windows.Forms.Label> controlla in modo che il testo visualizzato è allineato con il testo di <xref:System.Windows.Forms.TextBox> controlli.  
  
 Per informazioni sulla progettazione dell'interfaccia utente di Windows, vedere il manuale *Microsoft Windows User Experience, Official Guidelines for User Interface Developers e finestre di progettazione* Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>  
 [Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Procedura dettagliata: disposizione di controlli Windows Form usando spaziatura, margini e la proprietà AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)  
 [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
