---
title: 'Procedura dettagliata: Disposizione dei controlli in Windows Forms usando le guide di allineamento'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: 15ff9ad710b49caf35767acf498a8e55b238d84c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343038"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a>Procedura dettagliata: Disposizione dei controlli in Windows Forms usando le guide di allineamento
Per molte applicazioni è estremamente importante la sistemazione precisa dei controlli nel form. Finestra di progettazione Windows Form offre molti strumenti di layout per eseguire questa operazione. Uno dei più importanti è la <xref:System.Windows.Forms.Design.Behavior.SnapLine> funzionalità.  
  
 Le guide di allineamento mostrano esattamente dove allineare i controlli con altri controlli. Illustrano inoltre le distanze consigliate per i margini tra i controlli, come specificato dalle linee guida dell'interfaccia utente di Windows. Per informazioni dettagliate, vedere [sviluppo e progettazione dell'interfaccia utente](https://go.microsoft.com/FWLink/?LinkId=83878).  
  
 Le guide di allineamento semplificano l'allineamento dei controlli, consentono di ottenere, professionale aspetto e comportamento (aspetto).  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione di un progetto Windows Form  
  
-   La spaziatura e allineamento dei controlli con guide di allineamento  
  
-   Allineamento al Form e i margini di contenitore  
  
-   Allineamento a controlli raggruppati  
  
-   Usando le guide di allineamento per posizionare un controllo definendo la dimensione  
  
-   Usando le guide di allineamento quando si trascina un controllo dalla casella degli strumenti  
  
-   Ridimensionamento di controlli con guide di allineamento  
  
-   Allineare un'etichetta di testo di un controllo  
  
-   Usando le guide di allineamento con navigazione tramite tastiera  
  
-   Le guide di allineamento e i pannelli di Layout  
  
-   La disabilitazione delle guide di allineamento  
  
 Al termine, si avrà una conoscenza di layout ruolo della funzionalità di guide di allineamento.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1. Creare un progetto di applicazione basata su Windows denominato "SnaplineExample" (**File** > **New** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).  
  
2. Selezionare il form in Progettazione Windows Form.  
  
## <a name="spacing-and-aligning-controls-using-snaplines"></a>La spaziatura e allineamento dei controlli con guide di allineamento  
 Le guide di allineamento offrono un modo intuitivo e accurato per allineare i controlli sul form. Vengono visualizzate quando si sposta uno o più controlli selezionati quasi una posizione che sarà allineata con un altro controllo o set di controlli. La selezione verrà "bloccata" per la posizione consigliata quando si sposta oltre agli altri controlli.  
  
#### <a name="to-arrange-controls-using-snaplines"></a>Per disporre i controlli usando le guide di allineamento  
  
1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.  
  
2. Spostare il <xref:System.Windows.Forms.Button> controllo nell'angolo in basso a destra del form. Le guide di allineamento che appaiono come il <xref:System.Windows.Forms.Button> controllo sta per raggiungere i bordi inferiore e destro del form. Queste guide di allineamento visualizzano la distanza consigliata tra i bordi del controllo e il modulo.  
  
3. Spostare il <xref:System.Windows.Forms.Button> controllo intorno ai bordi del form e notare in cui vengono visualizzate le guide di allineamento. Al termine, spostare il <xref:System.Windows.Forms.Button> controllo vicino al centro della forma.  
  
4. Trascinare un'altra <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nel form.  
  
5. Spostare il secondo <xref:System.Windows.Forms.Button> controllare fino a quando non è quasi livello con il primo. Si noti la Guida di allineamento che appare in linea di base di testo di entrambi i pulsanti e il controllo che si sta spostando si blocca in una posizione che è perfettamente allineata con l'altro controllo.  
  
6. Spostare il secondo <xref:System.Windows.Forms.Button> controllare fino a quando non è posizionato direttamente sopra la prima. Tenere presente le guide di allineamento che appaiono lungo i bordi sinistro e destro di entrambi i pulsanti e si noti che il controllo sta spostando si blocca in una posizione che è perfettamente allineata con l'altro controllo.  
  
7. Selezionare una del <xref:System.Windows.Forms.Button> controlla e spostarlo accanto a altro, fino a quando non si stanno quasi toccando. Si noti la Guida di allineamento che viene visualizzato tra di essi. La distanza è la distanza consigliata tra i bordi dei controlli. Si noti inoltre che il controllo che si sposta si blocca in questa posizione.  
  
8. Trascinare due <xref:System.Windows.Forms.Panel> dei controlli il **casella degli strumenti** nel form.  
  
9. Spostare una del <xref:System.Windows.Forms.Panel> controlla fino a quando non è quasi livello con il primo. Tenere presente le guide di allineamento che appaiono lungo i bordi superiore e inferiore di entrambi i controlli e che si blocca il controllo che si sposta in una posizione che è perfettamente allineata con l'altro controllo.  
  
## <a name="aligning-to-form-and-container-margins"></a>Allineamento al Form e i margini di contenitore  
 Le guide di allineamento consentono di allineare i controlli ai margini del form e contenitori in modo coerente.  
  
#### <a name="to-align-controls-to-form-and-container-margins"></a>Per allineare i controlli per i margini di form e contenitori  
  
1. Selezionare una del <xref:System.Windows.Forms.Button> controlla e spostarlo vicino al bordo destro del form fino a quando non viene visualizzata una Guida di allineamento. Distanza della Guida di allineamento tra il bordo destro è la somma del controllo <xref:System.Windows.Forms.Control.Margin%2A> proprietà e il form <xref:System.Windows.Forms.Control.Padding%2A> i valori delle proprietà.  
  
> [!NOTE]
>  Se il modulo <xref:System.Windows.Forms.Control.Padding%2A> è impostata su 0,0,0,0, Progettazione Windows Form viene assegnato al form un nascoste <xref:System.Windows.Forms.Control.Padding%2A> pari a 9,9,9,9. Per modificare questo comportamento, assegnare un valore diverso da 0,0,0,0.  
  
1. Modificare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Margin%2A> proprietà espandendo il <xref:System.Windows.Forms.Control.Margin%2A> voce nella **proprietà** finestra e impostando il <xref:System.Windows.Forms.Padding.All%2A> proprietà su 0. Per informazioni dettagliate, vedere [procedura dettagliata: Definire il layout dei Windows Form controlli con spaziatura, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md).  
  
2. Spostare il <xref:System.Windows.Forms.Button> controllo vicino al bordo destro del form fino a quando non viene visualizzata una Guida di allineamento. La distanza è ora stabilita tramite il valore dell'oggetto del form <xref:System.Windows.Forms.Control.Padding%2A> proprietà.  
  
3. Trascinare un controllo <xref:System.Windows.Forms.GroupBox> dalla **Casella degli strumenti** al form.  
  
4. Modificare il valore della <xref:System.Windows.Forms.GroupBox> del controllo <xref:System.Windows.Forms.Control.Padding%2A> proprietà espandendo il <xref:System.Windows.Forms.Control.Padding%2A> voce nella **proprietà** finestra e impostando il <xref:System.Windows.Forms.Padding.All%2A> proprietà a 10.  
  
5. Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nel <xref:System.Windows.Forms.GroupBox> controllo.  
  
6. Spostare il <xref:System.Windows.Forms.Button> controllo vicino al bordo destro del <xref:System.Windows.Forms.GroupBox> controllare fino a quando non viene visualizzata una Guida di allineamento. Spostare il <xref:System.Windows.Forms.Button> controllo all'interno di <xref:System.Windows.Forms.GroupBox> nota in cui vengono visualizzate le guide di allineamento e controllo.  
  
## <a name="aligning-to-grouped-controls"></a>Allineamento a controlli raggruppati  
 È possibile usare le guide di allineamento per allineare i controlli raggruppati nonché i controlli all'interno di un <xref:System.Windows.Forms.GroupBox> controllo.  
  
#### <a name="to-align-to-grouped-controls"></a>In modo da allinearsi ai controlli raggruppati  
  
1. Selezionare due dei controlli sul form. Spostare la selezione e le guide di allineamento che appaiono tra la selezione e degli altri controlli.  
  
2. Trascinare un controllo <xref:System.Windows.Forms.GroupBox> dalla **Casella degli strumenti** al form.  
  
3. Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nel <xref:System.Windows.Forms.GroupBox> controllo.  
  
4. Selezionare una delle <xref:System.Windows.Forms.Button> controlla e spostarla all'interno di <xref:System.Windows.Forms.GroupBox> controllo. Le guide di allineamento che vengono visualizzati in corrispondenza dei bordi del <xref:System.Windows.Forms.GroupBox> controllo. Si noti anche le guide di allineamento che vengono visualizzati in corrispondenza dei bordi del <xref:System.Windows.Forms.Button> controllo contenuto dal <xref:System.Windows.Forms.GroupBox> controllo. I controlli che sono elementi figlio di un controllo contenitore supportano anche le guide di allineamento.  
  
## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a>Usando le guide di allineamento per posizionare un controllo definendo la dimensione  
 Le guide di allineamento consentono di che allineare controlla quando è prima di tutto inserirli in un form.  
  
#### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a>Usare le guide di allineamento per inserire un controllo definendo la dimensione  
  
1. Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.Button> . Non trascinarla nel form.  
  
2. Spostare il puntatore del mouse sull'area di progettazione del form. Osservare che il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.Button> associata. Si noti anche le guide di allineamento che sembrano indicare le posizioni allineate per i <xref:System.Windows.Forms.Button> controllo.  
  
3. Fare clic e tenere premuto il pulsante del mouse.  
  
4. Trascinare il puntatore del mouse intorno al form. Si noti che viene disegnato un contorno, che indica la posizione e le dimensioni del controllo.  
  
5. Trascinare il puntatore fino a quando non Allinea con un altro controllo nel form. Si noti che viene visualizzata una Guida di allineamento per indicare l'allineamento.  
  
6. Rilasciare il pulsante del mouse. Il controllo viene creato nella posizione e dimensioni indicate dalla struttura.  
  
## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a>Usando le guide di allineamento quando si trascina un controllo dalla casella degli strumenti  
 Consentono di guide di allineamento allineare i controlli quando si trascina il **casella degli strumenti** nel form.  
  
#### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a>Usare le guide di allineamento quando si trascina un controllo dalla casella degli strumenti  
  
1. Trascinare un <xref:System.Windows.Forms.Button> controllare dal **della casella degli strumenti** nel form, ma non rilasciare il pulsante del mouse.  
  
2. Spostare il puntatore del mouse sull'area di progettazione del form. Si noti che il puntatore del mouse cambia per indicare la posizione in cui la nuova <xref:System.Windows.Forms.Button> controllo verrà creato.  
  
3. Trascinare il puntatore del mouse intorno al form. Le guide di allineamento che sembrano indicare le posizioni allineate per i <xref:System.Windows.Forms.Button> controllo. Trovare una posizione che è allineata con altri controlli.  
  
4. Rilasciare il pulsante del mouse. Il controllo viene creato nella posizione indicata dalle guide di allineamento.  
  
## <a name="resizing-controls-using-snaplines"></a>Ridimensionamento di controlli con guide di allineamento  
 Le guide di allineamento consentono di allineare i controlli durante il ridimensionamento.  
  
#### <a name="to-resize-a-control-using-snaplines"></a>Per ridimensionare un controllo usando le guide di allineamento  
  
1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.  
  
2. Ridimensionare il <xref:System.Windows.Forms.Button> controllo agganciando uno dei quadratini di ridimensionamento e trascinandolo. Per informazioni dettagliate, vedere [Procedura: Ridimensionare i controlli Windows Form](how-to-resize-controls-on-windows-forms.md).  
  
3. Trascinare il quadratino di ridimensionamento fino a quando uno del <xref:System.Windows.Forms.Button> bordi del controllo è allineato a un altro controllo. Si noti che viene visualizzata una Guida di allineamento. Si noti inoltre che il quadratino di ridimensionamento si blocca nella posizione indicata dalla Guida di allineamento.  
  
4. Ridimensionare il <xref:System.Windows.Forms.Button> controllare in direzioni diverse e allineare il quadratino di ridimensionamento diversi controlli. Si noti come le guide di allineamento vengono visualizzati in diversi orientamenti per indicare l'allineamento.  
  
## <a name="aligning-a-label-to-a-controls-text"></a>Allineare un'etichetta di testo di un controllo  
 Alcuni controlli offrono una Guida di allineamento per allineare il testo visualizzato degli altri controlli.  
  
#### <a name="to-align-a-label-to-a-controls-text"></a>Per allineare un'etichetta di testo di un controllo  
  
1. Trascinare un controllo <xref:System.Windows.Forms.TextBox> dalla **Casella degli strumenti** al form. Quando si rilascia il <xref:System.Windows.Forms.TextBox> sul form, fare clic sul glifo smart tag e selezionare il **impostare il testo da textBox1** opzione. Per informazioni dettagliate, vedere [procedura dettagliata: Esecuzione di attività comuni usando gli Smart tag nei Windows Form controlli](performing-common-tasks-using-smart-tags-on-wf-controls.md).  
  
2. Trascinare un controllo <xref:System.Windows.Forms.Label> dalla **Casella degli strumenti** al form.  
  
3. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Label> , <xref:System.Windows.Forms.Control.AutoSize%2A> , su `true`. Si noti che i bordi del controllo vengono regolati per adattarsi al testo visualizzato.  
  
4. Spostare il <xref:System.Windows.Forms.Label> a sinistra del controllo il <xref:System.Windows.Forms.TextBox> controllare, in modo che sia allineato al bordo inferiore del <xref:System.Windows.Forms.TextBox> controllo. Si noti la Guida di allineamento che viene visualizzato lungo il bordo inferiore dei due controlli.  
  
5. Spostare il <xref:System.Windows.Forms.Label> controllo leggermente verso l'alto, fino al <xref:System.Windows.Forms.Label> testo e <xref:System.Windows.Forms.TextBox> testo sono allineate. Si noti la Guida di allineamento in modo diverso con stile viene visualizzato un messaggio quando i campi di testo di entrambi i controlli sono allineati.  
  
## <a name="using-snaplines-with-keyboard-navigation"></a>Usando le guide di allineamento con navigazione tramite tastiera  
 Le guide di allineamento consentono di che allineare controlla quando vengono disposti con i tasti della tastiera.  
  
#### <a name="to-use-snaplines-with-keyboard-navigation"></a>Usare le guide di allineamento con navigazione tramite tastiera  
  
1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form. Inserirlo nell'angolo superiore sinistro del form.  
  
2. Premere CTRL + freccia giù. Si noti che il controllo viene spostato verso il basso il modulo per la prima posizione di allineamento orizzontale disponibile.  
  
3. Premere CTRL + freccia GIÙ fino a quando il controllo raggiunge la fine del form. Si notino le posizioni in cui è contenuto durante lo spostamento verso il basso il modulo.  
  
4. Premere CTRL + freccia destra. Si noti che il controllo viene spostato nel form per la prima posizione di allineamento verticale disponibili.  
  
5. Premere CTRL + freccia destra fino a quando il controllo raggiunge il lato del form. Si notino le posizioni che occupa durante lo spostamento tra i form.  
  
6. Spostare il controllo nel form con una combinazione di tasti di direzione. Si notino le posizioni che occupate dal controllo e le guide di allineamento che li accompagnano.  
  
7. Premere MAIUSC + qualsiasi tasto di direzione per ridimensionare il <xref:System.Windows.Forms.Button> controllo in incrementi di un pixel.  
  
8. Premere CTRL + MAIUSC + qualsiasi tasto di direzione per ridimensionare il <xref:System.Windows.Forms.Button> controllo in incrementi di Guida di allineamento.  
  
## <a name="snaplines-and-layout-panels"></a>Le guide di allineamento e i pannelli di Layout  
 Le guide di allineamento sono disabilitate in altri pannelli layout.  
  
#### <a name="to-selectively-disable-snaplines"></a>Per disabilitare in modo selettivo le guide di allineamento  
  
1. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.  
  
2. Fare doppio clic sull'icona del controllo <xref:System.Windows.Forms.Button> nella **Casella degli strumenti**. Si noti che un nuovo controllo pulsante visualizzato nei <xref:System.Windows.Forms.TableLayoutPanel> prima cella del controllo.  
  
3. Fare doppio clic il <xref:System.Windows.Forms.Button> icona del controllo nel **della casella degli strumenti** altre due volte. In tal modo una cella vuota nel <xref:System.Windows.Forms.TableLayoutPanel> controllo.  
  
4. Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** alla cella vuota del <xref:System.Windows.Forms.TableLayoutPanel> controllo. Si noti che delle guide di allineamento vengono visualizzati.  
  
5. Trascinare il <xref:System.Windows.Forms.Button> controllare fuori il <xref:System.Windows.Forms.TableLayoutPanel> controllano e spostarlo il <xref:System.Windows.Forms.TableLayoutPanel> controllo. Si noti che le guide di allineamento vengono visualizzati anche in questo caso.  
  
## <a name="disabling-snaplines"></a>La disabilitazione delle guide di allineamento  
 Le guide di allineamento viene attivate per impostazione predefinita. È possibile disabilitare le guide di allineamento in modo selettivo, oppure è possibile disabilitarli nell'ambiente di progettazione.  
  
#### <a name="to-selectively-disable-snaplines"></a>Per disabilitare in modo selettivo le guide di allineamento  
  
-   Premere il tasto ALT mentre si sposta un controllo nel form.  
  
     Si noti che delle guide di allineamento vengono visualizzati il controllo non viene bloccato in qualsiasi posizione di allineamento potenziali.  
  
#### <a name="to-disable-snaplines-in-the-design-environment"></a>Per disabilitare le guide di allineamento nell'ambiente di progettazione  
  
1. Dal **Tools** menu, aprire il **opzioni** nella finestra di dialogo. Aprire la finestra di dialogo di progettazione di Windows Form. Per informazioni dettagliate, vedere [generale, finestra di progettazione Windows Form, finestra di dialogo Opzioni](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).  
  
2. Selezionare il **generale** nodo. Nel **modalità Layout** sezione, modificare la selezione dalla **guide di allineamento** a **SnapToGrid**.  
  
3. Fare clic su OK per applicare l'impostazione.  
  
4. Selezionare un controllo sul form e spostarla all'interno di altri controlli. Si noti che non vengono visualizzate le guide di allineamento.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Le guide di allineamento offrono modalità intuitive per l'allineamento dei controlli sul form. Per approfondire l'argomento, si consiglia di effettuare le seguenti operazioni:  
  
-   Provare l'annidamento una <xref:System.Windows.Forms.GroupBox> controllo all'interno di altra <xref:System.Windows.Forms.GroupBox> controllo. Sul posto un <xref:System.Windows.Forms.Button> controllo entro l'elemento figlio <xref:System.Windows.Forms.GroupBox> controllo e l'altro nel controllo padre <xref:System.Windows.Forms.GroupBox> controllo. Spostare il <xref:System.Windows.Forms.Button> controlli per vedere come le guide di allineamento superano i limiti del contenitore.  
  
-   Creare una colonna di <xref:System.Windows.Forms.TextBox> controlli e una colonna corrispondente della <xref:System.Windows.Forms.Label> controlli. Impostare il valore della <xref:System.Windows.Forms.Label> controlli <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà `true`. Usare le guide di allineamento per spostare il <xref:System.Windows.Forms.Label> controlla in modo che il testo visualizzato è allineato con il testo nel <xref:System.Windows.Forms.TextBox> controlli.  
  
 Per informazioni sulla progettazione dell'interfaccia utente di Windows, vedere il libro *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and progettisti* Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Forms usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli Windows Forms con spaziatura interna, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md)
- [Disposizione di controlli in Windows Form](arranging-controls-on-windows-forms.md)
