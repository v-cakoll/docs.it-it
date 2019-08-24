---
title: 'Procedura dettagliata: Disposizione dei controlli in Windows Forms usando le guide di allineamento'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 83f0365ffb7335cb67c729c5a113e550c119191a
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69986996"
---
# <a name="walkthrough-arrange-controls-on-windows-forms-using-snaplines"></a>Procedura dettagliata: Disporre i controlli Windows Forms usando le guide di allineamento

Per molte applicazioni è estremamente importante la sistemazione precisa dei controlli nel form. Il Progettazione Windows Form fornisce molti strumenti di layout a questo scopo. Uno dei più importanti è la <xref:System.Windows.Forms.Design.Behavior.SnapLine> funzionalità.

Le guide di allineamento mostrano esattamente dove allineare i controlli con altri controlli. Vengono inoltre visualizzate le distanze consigliate per i margini tra i controlli, come specificato dalle [linee guida dell'interfaccia utente di Windows](/windows/win32/uxguide/guidelines).

Le guide di allineamento semplificano l'allineamento dei controlli, per un aspetto e un comportamento professionali e nitidi.

## <a name="create-the-project"></a>Creare il progetto

1. In Visual Studio creare un progetto di applicazione basato su Windows denominato "SnaplineExample".

2. Selezionare il form nella finestra di progettazione dei form.

## <a name="space-and-align-controls"></a>Spazi e allineamento di controlli

Le guide di allineamento consentono di allineare i controlli nel modulo in modo accurato e intuitivo. Vengono visualizzati quando si trasferisce un controllo o un controllo selezionato vicino a una posizione che verrebbe allineata a un altro controllo o a un set di controlli. La selezione verrà "agganciata" alla posizione suggerita mentre viene spostata oltre gli altri controlli.

### <a name="to-arrange-controls-using-snaplines"></a>Per disporre i controlli mediante le guide di allineamento

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.

2. Spostare il <xref:System.Windows.Forms.Button> controllo nell'angolo inferiore destro del form. Si noti che le guide di allineamento <xref:System.Windows.Forms.Button> visualizzate come il controllo si avvicinano ai bordi inferiore e destro del form. Queste guide di allineamento visualizzano la distanza consigliata tra i bordi del controllo e il form.

3. Spostare il <xref:System.Windows.Forms.Button> controllo intorno ai bordi del form e annotare il punto in cui vengono visualizzate le guide di allineamento. Al termine, spostare il <xref:System.Windows.Forms.Button> controllo vicino al centro del form.

4. Trascinare un <xref:System.Windows.Forms.Button> altro controllo dalla **casella degli strumenti** nel form.

5. Spostare il secondo <xref:System.Windows.Forms.Button> controllo fino a quando non è quasi a livello del primo. Si noti la guide di allineamento visualizzata in corrispondenza della linea di base del testo di entrambi i pulsanti e si noti che il controllo spostato si blocca in una posizione che è esattamente a livello dell'altro controllo.

6. Spostare il secondo <xref:System.Windows.Forms.Button> controllo fino a quando non viene posizionato immediatamente sopra la prima. Si notino le guide di allineamento visualizzate lungo i bordi sinistro e destro di entrambi i pulsanti e si noti che il controllo spostato si blocca in una posizione esattamente allineata con l'altro controllo.

7. Selezionare uno dei <xref:System.Windows.Forms.Button> controlli e spostarlo vicino all'altro, fino a quando non sono quasi in contatto. Si noti la guide di allineamento visualizzata tra di essi. Questa distanza è la distanza consigliata tra i bordi dei controlli. Si noti inoltre che il controllo spostato si blocca in questa posizione.

8. Trascinare due <xref:System.Windows.Forms.Panel> controlli dalla **casella degli strumenti** nel form.

9. Spostare uno dei <xref:System.Windows.Forms.Panel> controlli fino a quando non è quasi il primo livello. Si notino le guide di allineamento visualizzate lungo i bordi superiore e inferiore di entrambi i controlli e si noti che il controllo spostato si blocca in una posizione che è esattamente a livello dell'altro controllo.

## <a name="align-to-form-and-container-margins"></a>Allinea al form e ai margini del contenitore

Le guide di allineamento consentono di allineare i controlli ai margini dei moduli e dei contenitori in modo coerente.

1. Selezionare uno dei <xref:System.Windows.Forms.Button> controlli e spostarlo vicino al bordo destro del form finché non viene visualizzata una guide di allineamento. La distanza della guide di allineamento dal bordo destro è la somma della <xref:System.Windows.Forms.Control.Margin%2A> proprietà del controllo e dei valori delle <xref:System.Windows.Forms.Control.Padding%2A> proprietà del modulo.

   > [!NOTE]
   > Se la <xref:System.Windows.Forms.Control.Padding%2A> proprietà del form è impostata su 0, 0, 0, 0, il progettazione Windows Form fornisce al form un <xref:System.Windows.Forms.Control.Padding%2A> valore ombreggiato pari a 9, 9, 9, 9. Per eseguire l'override di questo comportamento, assegnare un valore diverso da 0, 0, 0, 0.

2. Modificare il <xref:System.Windows.Forms.Button> valore della <xref:System.Windows.Forms.Control.Margin%2A> proprietà del controllo espandendo la <xref:System.Windows.Forms.Control.Margin%2A> voce nella finestra **Proprietà** e impostando la <xref:System.Windows.Forms.Padding.All%2A> proprietà su 0. Per informazioni dettagliate, [vedere Procedura dettagliata: Layout Windows Forms controlli con spaziatura interna, margini e la proprietà](windows-forms-controls-padding-autosize.md)AutoSize.

3. Spostare il <xref:System.Windows.Forms.Button> controllo vicino al bordo destro del form finché non viene visualizzata una guide di allineamento. Questa distanza è ora fornita dal valore della <xref:System.Windows.Forms.Control.Padding%2A> proprietà del form.

4. Trascinare un controllo <xref:System.Windows.Forms.GroupBox> dalla **Casella degli strumenti** al form.

5. Modificare il <xref:System.Windows.Forms.GroupBox> valore della <xref:System.Windows.Forms.Control.Padding%2A> proprietà del controllo espandendo la <xref:System.Windows.Forms.Control.Padding%2A> voce nella finestra **Proprietà** e impostando la <xref:System.Windows.Forms.Padding.All%2A> proprietà su 10.

6. Trascinare un <xref:System.Windows.Forms.Button> controllo dalla <xref:System.Windows.Forms.GroupBox> **casella degli strumenti** nel controllo.

7. Spostare il <xref:System.Windows.Forms.Button> controllo vicino al bordo destro <xref:System.Windows.Forms.GroupBox> del controllo fino a quando non viene visualizzata una guide di allineamento. Spostare il <xref:System.Windows.Forms.Button> controllo all'interno <xref:System.Windows.Forms.GroupBox> del controllo e prendere nota della posizione in cui vengono visualizzate le guide di allineamento.

## <a name="align-to-grouped-controls"></a>Allinea a controlli raggruppati

È possibile utilizzare le guide di allineamento per allineare i controlli raggruppati e i <xref:System.Windows.Forms.GroupBox> controlli all'interno di un controllo.

1. Selezionare due dei controlli nel form. Spostare la selezione e prendere nota delle guide di allineamento visualizzate tra la selezione e gli altri controlli.

2. Trascinare un controllo <xref:System.Windows.Forms.GroupBox> dalla **Casella degli strumenti** al form.

3. Trascinare un <xref:System.Windows.Forms.Button> controllo dalla <xref:System.Windows.Forms.GroupBox> **casella degli strumenti** nel controllo.

4. Selezionare uno dei <xref:System.Windows.Forms.Button> controlli e spostarlo intorno al <xref:System.Windows.Forms.GroupBox> controllo. Prendere nota delle guide di allineamento visualizzate ai bordi del <xref:System.Windows.Forms.GroupBox> controllo. Si notino inoltre le guide di allineamento visualizzate ai bordi <xref:System.Windows.Forms.Button> del controllo contenuto nel <xref:System.Windows.Forms.GroupBox> controllo. Anche i controlli figlio di un controllo contenitore supportano le guide di allineamento.

## <a name="use-snaplines-to-place-a-control-by-outlining-its-size"></a>Utilizzare le guide di allineamento per posizionare un controllo in base alla relativa dimensione

1. Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.Button> . Non trascinarla nel form.

2. Spostare il puntatore del mouse sull'area di progettazione del form. Osservare che il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.Button> associata. Prendere nota anche delle guide di allineamento che sembrano suggerire posizioni allineate per il <xref:System.Windows.Forms.Button> controllo.

3. Fare clic e tenere premuto il pulsante del mouse.

4. Trascinare il puntatore del mouse intorno al form. Si noti che viene disegnata una struttura che indica la posizione e le dimensioni del controllo.

5. Trascinare il puntatore finché non viene allineato con un altro controllo nel form. Si noti che viene visualizzata una linea di allineamento per indicare l'allineamento.

6. Rilasciare il pulsante del mouse. Il controllo viene creato in corrispondenza della posizione e delle dimensioni indicate dal contorno.

## <a name="use-snaplines-when-dragging-a-control-from-the-toolbox"></a>Utilizzare le guide di allineamento quando si trascina un controllo dalla casella degli strumenti

1. Trascinare un <xref:System.Windows.Forms.Button> controllo dalla **casella degli strumenti** nel form, ma non rilasciare il pulsante del mouse.

2. Spostare il puntatore del mouse sull'area di progettazione del form. Si noti che il puntatore cambia per indicare la posizione in cui verrà <xref:System.Windows.Forms.Button> creato il nuovo controllo.

3. Trascinare il puntatore del mouse intorno al form. Prendere nota delle guide di allineamento visualizzate per suggerire posizioni allineate per il <xref:System.Windows.Forms.Button> controllo. Trovare una posizione allineata con altri controlli.

4. Rilasciare il pulsante del mouse. Il controllo viene creato nella posizione indicata dalle guide di allineamento.

## <a name="resize-a-control-using-snaplines"></a>Ridimensionare un controllo utilizzando le guide di allineamento

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.

2. Ridimensionare <xref:System.Windows.Forms.Button> il controllo afferrando uno degli handle di ridimensionamento dell'angolo e il trascinamento. Per informazioni dettagliate, vedere [Procedura: Ridimensionare i controlli](how-to-resize-controls-on-windows-forms.md)Windows Forms.

3. Trascinare il quadratino di ridimensionamento fino <xref:System.Windows.Forms.Button> a quando uno dei bordi del controllo non è allineato a un altro controllo. Si noti che viene visualizzata una guide di allineamento. Si noti inoltre che il quadratino di ridimensionamento viene agganciato alla posizione indicata dalla Guide di allineamento.

4. Ridimensionare <xref:System.Windows.Forms.Button> il controllo in direzioni diverse e allineare il quadratino di ridimensionamento a controlli diversi. Si noti come le guide di allineamento vengono visualizzate in diversi orientamenti per indicare l'allineamento.

## <a name="align-a-label-to-a-controls-text"></a>Allinea un'etichetta al testo di un controllo

1. Trascinare un controllo <xref:System.Windows.Forms.TextBox> dalla **Casella degli strumenti** al form. Quando si rilascia il <xref:System.Windows.Forms.TextBox> controllo sul form, fare clic sul glifo smart tag e selezionare l'opzione **Imposta testo su TextBox1** . Per informazioni dettagliate, [vedere Procedura dettagliata: Esecuzione di attività comuni tramite smart tag sui controlli](performing-common-tasks-using-smart-tags-on-wf-controls.md)Windows Forms.

2. Trascinare un controllo <xref:System.Windows.Forms.Label> dalla **Casella degli strumenti** al form.

3. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Label> , <xref:System.Windows.Forms.Control.AutoSize%2A> , su `true`. Si noti che i bordi del controllo vengono adattati per adattarsi al testo visualizzato.

4. Spostare il <xref:System.Windows.Forms.Label> controllo a sinistra <xref:System.Windows.Forms.TextBox> del controllo, in modo che sia allineato al bordo inferiore del <xref:System.Windows.Forms.TextBox> controllo. Si noti la guide di allineamento visualizzata lungo i bordi inferiore dei due controlli.

5. Spostare il <xref:System.Windows.Forms.Label> controllo leggermente verso l'alto, <xref:System.Windows.Forms.Label> fino a quando <xref:System.Windows.Forms.TextBox> il testo e il testo non sono allineati. Si noti la linea di allineamento con stile diverso visualizzata, che indica quando i campi di testo di entrambi i controlli sono allineati.

## <a name="use-snaplines-with-keyboard-navigation"></a>Usare le guide di allineamento con la navigazione da tastiera

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form. Posizionarlo nell'angolo superiore sinistro del form.

2. Premere **CTRL**+**freccia giù**. Si noti che il controllo sposta verso il basso il form fino alla prima posizione di allineamento orizzontale disponibile.

3. Premere **CTRL**+**freccia giù** finché il controllo non raggiunge la fine del form. Si notino le posizioni occupate quando si sposta verso il basso il form.

4. Premere **CTRL**+**freccia destra**. Si noti che il controllo passa attraverso il form alla prima posizione di allineamento verticale disponibile.

5. Premere **CTRL**+**freccia destra** finché il controllo non raggiunge il lato del form. Prendere nota delle posizioni che occupano durante lo spostamento nel form.

6. Spostare il controllo intorno al form con una combinazione di tasti di direzione. Si notino le posizioni occupate dal controllo e le guide di allineamento che li accompagnano.

7. Premere **MAIUSC**+**tasti** di direzione per ridimensionare il <xref:System.Windows.Forms.Button> controllo in base a incrementi di un pixel.

8. Premere **CTRL**+ <xref:System.Windows.Forms.Button>MAIUSCtasti+di direzione per ridimensionare il controllo negli incrementi della guide di allineamento.

## <a name="selectively-disable-snaplines"></a>Disabilitare selettivamente le guide di allineamento

1. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.

2. Fare doppio clic sull'icona del controllo <xref:System.Windows.Forms.Button> nella **Casella degli strumenti**. Si noti che viene visualizzato un nuovo controllo Button <xref:System.Windows.Forms.TableLayoutPanel> nella prima cella del controllo.

3. Fare doppio clic <xref:System.Windows.Forms.Button> sull'icona del controllo nella **casella degli strumenti** per due volte. Questa operazione lascia una cella vuota nel <xref:System.Windows.Forms.TableLayoutPanel> controllo.

4. Trascinare un <xref:System.Windows.Forms.Button> controllo dalla **casella degli strumenti** nella cella <xref:System.Windows.Forms.TableLayoutPanel> vuota del controllo. Si noti che non vengono visualizzate guide di allineamento.

5. Trascinare il <xref:System.Windows.Forms.Button> controllo dal <xref:System.Windows.Forms.TableLayoutPanel> controllo e spostarlo intorno al <xref:System.Windows.Forms.TableLayoutPanel> controllo. Si noti che le guide di allineamento sono di nuovo visualizzate.

## <a name="disable-snaplines"></a>Disabilita guide di allineamento

Premere il tasto **ALT** e spostando un controllo intorno al modulo.

Non viene visualizzata alcuna linea di allineamento e il controllo non si blocca in nessuna delle posizioni di allineamento possibili.

### <a name="to-disable-snaplines-in-the-design-environment"></a>Per disabilitare le guide di allineamento nell'ambiente di progettazione

1. Dal menu **strumenti** aprire la finestra di dialogo **Opzioni** . Selezionare **Progettazione Windows Form**.

2. Selezionare il nodo **generale** . Nella sezione **modalità layout** modificare la selezione da guide di **allineamento** a **SnapToGrid**.

3. Selezionare **OK** per applicare l'impostazione.

4. Selezionare un controllo nel form e spostarlo intorno agli altri controlli. Si noti che le guide di allineamento non vengono visualizzate.

## <a name="next-steps"></a>Passaggi successivi

Le guide di allineamento offrono un mezzo intuitivo per allineare i controlli nel form. Per approfondire l'argomento, si consiglia di effettuare le seguenti operazioni:

- Provare a annidare <xref:System.Windows.Forms.GroupBox> un controllo all' <xref:System.Windows.Forms.GroupBox> interno di un altro controllo. Inserire un <xref:System.Windows.Forms.Button> controllo all'interno del <xref:System.Windows.Forms.GroupBox> controllo figlio e un altro all'interno <xref:System.Windows.Forms.GroupBox> del controllo padre. Spostare i <xref:System.Windows.Forms.Button> controlli per verificare il modo in cui le guide di allineamento attraversano i limiti del contenitore.

- Creare una colonna di <xref:System.Windows.Forms.TextBox> controlli e una colonna corrispondente di <xref:System.Windows.Forms.Label> controlli. Impostare il valore della <xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà Controls su `true`. Utilizzare le guide di allineamento <xref:System.Windows.Forms.Label> per spostare i controlli <xref:System.Windows.Forms.TextBox> in modo che il testo visualizzato venga allineato al testo dei controlli.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [Procedura dettagliata: Disposizione di controlli in Windows Forms tramite FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: Disposizione di controlli in Windows Forms tramite TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Layout Windows Forms controlli con spaziatura interna, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md)
