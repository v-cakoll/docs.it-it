---
title: Disposizione di controlli mediante guide di allineamento
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3b88f64fca8d3f11308f1cbfde97de2e6c2f22cc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740213"
---
# <a name="walkthrough-arrange-controls-on-windows-forms-using-snaplines"></a>Procedura dettagliata: disporre i controlli sui Windows Forms usando le guide di allineamento

Per molte applicazioni è estremamente importante la sistemazione precisa dei controlli nel form. Il Progettazione Windows Form fornisce molti strumenti di layout a questo scopo. Uno dei più importanti è la <xref:System.Windows.Forms.Design.Behavior.SnapLine> funzionalità.

Le guide di allineamento mostrano esattamente dove allineare i controlli con altri controlli. Vengono inoltre visualizzate le distanze consigliate per i margini tra i controlli, come specificato dalle [linee guida dell'interfaccia utente di Windows](/windows/win32/uxguide/guidelines).

Le guide di allineamento semplificano l'allineamento dei controlli, per un aspetto e un comportamento professionali e nitidi.

## <a name="create-the-project"></a>Creare il progetto

1. In Visual Studio creare un progetto di applicazione basato su Windows denominato "SnaplineExample".

2. Selezionare il form in Progettazione form.

## <a name="space-and-align-controls"></a>Spazi e allineamento di controlli

Le guide di allineamento consentono di allineare i controlli nel modulo in modo accurato e intuitivo. Vengono visualizzati quando si trasferisce un controllo o un controllo selezionato vicino a una posizione che verrebbe allineata a un altro controllo o a un set di controlli. La selezione verrà "agganciata" alla posizione suggerita mentre viene spostata oltre gli altri controlli.

### <a name="to-arrange-controls-using-snaplines"></a>Per disporre i controlli mediante le guide di allineamento

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.

2. Spostare il controllo <xref:System.Windows.Forms.Button> nell'angolo inferiore destro del form. Si noti che le guide di allineamento visualizzate come controllo <xref:System.Windows.Forms.Button> si avvicinano ai bordi inferiore e destro del form. Queste guide di allineamento visualizzano la distanza consigliata tra i bordi del controllo e il form.

3. Spostare il controllo <xref:System.Windows.Forms.Button> intorno ai bordi del form e annotare il punto in cui vengono visualizzate le guide di allineamento. Al termine, spostare il controllo <xref:System.Windows.Forms.Button> vicino al centro del form.

4. Trascinare un altro controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel form.

5. Spostare il secondo controllo <xref:System.Windows.Forms.Button> fino a quando non è quasi il primo livello. Si noti la guide di allineamento visualizzata in corrispondenza della linea di base del testo di entrambi i pulsanti e si noti che il controllo spostato si blocca in una posizione che è esattamente a livello dell'altro controllo.

6. Spostare il secondo controllo <xref:System.Windows.Forms.Button> finché non viene posizionato immediatamente sopra la prima. Si notino le guide di allineamento visualizzate lungo i bordi sinistro e destro di entrambi i pulsanti e si noti che il controllo spostato si blocca in una posizione esattamente allineata con l'altro controllo.

7. Selezionare uno dei controlli <xref:System.Windows.Forms.Button> e spostarlo vicino all'altro, fino a quando non sono quasi toccati. Si noti la guide di allineamento visualizzata tra di essi. Questa distanza è la distanza consigliata tra i bordi dei controlli. Si noti inoltre che il controllo spostato si blocca in questa posizione.

8. Trascinare due controlli <xref:System.Windows.Forms.Panel> dalla **casella degli strumenti** nel form.

9. Spostare uno dei controlli <xref:System.Windows.Forms.Panel> fino a quando non è quasi il primo livello. Si notino le guide di allineamento visualizzate lungo i bordi superiore e inferiore di entrambi i controlli e si noti che il controllo spostato si blocca in una posizione che è esattamente a livello dell'altro controllo.

## <a name="align-to-form-and-container-margins"></a>Allinea al form e ai margini del contenitore

Le guide di allineamento consentono di allineare i controlli ai margini dei moduli e dei contenitori in modo coerente.

1. Selezionare uno dei controlli <xref:System.Windows.Forms.Button> e spostarlo vicino al bordo destro del form finché non viene visualizzata una guide di allineamento. La distanza della guide di allineamento dal bordo destro è la somma della proprietà <xref:System.Windows.Forms.Control.Margin%2A> del controllo e dei valori della proprietà <xref:System.Windows.Forms.Control.Padding%2A> del modulo.

   > [!NOTE]
   > Se la proprietà <xref:System.Windows.Forms.Control.Padding%2A> del form è impostata su 0, 0, 0, 0, il Progettazione Windows Form fornisce al form un valore <xref:System.Windows.Forms.Control.Padding%2A> ombreggiato pari a 9, 9, 9, 9. Per eseguire l'override di questo comportamento, assegnare un valore diverso da 0, 0, 0, 0.

2. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.Margin%2A> del controllo <xref:System.Windows.Forms.Button> espandendo la voce <xref:System.Windows.Forms.Control.Margin%2A> nella finestra **Proprietà** e impostando la proprietà <xref:System.Windows.Forms.Padding.All%2A> su 0. Per informazioni dettagliate, vedere [procedura dettagliata: layout Windows Forms controlli con spaziatura interna, margini e proprietà AutoSize](windows-forms-controls-padding-autosize.md).

3. Spostare il controllo <xref:System.Windows.Forms.Button> vicino al bordo destro del form finché non viene visualizzata una guide di allineamento. Questa distanza è ora fornita dal valore della proprietà <xref:System.Windows.Forms.Control.Padding%2A> del modulo.

4. Trascinare un controllo <xref:System.Windows.Forms.GroupBox> dalla **Casella degli strumenti** al form.

5. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.Padding%2A> del controllo <xref:System.Windows.Forms.GroupBox> espandendo la voce <xref:System.Windows.Forms.Control.Padding%2A> nella finestra **Proprietà** e impostando la proprietà <xref:System.Windows.Forms.Padding.All%2A> su 10.

6. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel controllo <xref:System.Windows.Forms.GroupBox>.

7. Spostare il controllo <xref:System.Windows.Forms.Button> vicino al bordo destro del controllo <xref:System.Windows.Forms.GroupBox> fino a quando non viene visualizzata una guide di allineamento. Spostare il controllo <xref:System.Windows.Forms.Button> all'interno del controllo <xref:System.Windows.Forms.GroupBox> e prendere nota della posizione in cui vengono visualizzate le guide di allineamento.

## <a name="align-to-grouped-controls"></a>Allinea a controlli raggruppati

È possibile utilizzare le guide di allineamento per allineare i controlli raggruppati e i controlli all'interno di un controllo <xref:System.Windows.Forms.GroupBox>.

1. Selezionare due dei controlli nel form. Spostare la selezione e prendere nota delle guide di allineamento visualizzate tra la selezione e gli altri controlli.

2. Trascinare un controllo <xref:System.Windows.Forms.GroupBox> dalla **Casella degli strumenti** al form.

3. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel controllo <xref:System.Windows.Forms.GroupBox>.

4. Selezionare uno dei controlli <xref:System.Windows.Forms.Button> e spostarlo intorno al controllo <xref:System.Windows.Forms.GroupBox>. Prendere nota delle guide di allineamento visualizzate ai bordi del controllo <xref:System.Windows.Forms.GroupBox>. Si notino inoltre le guide di allineamento visualizzate ai bordi del controllo <xref:System.Windows.Forms.Button> contenuto nel controllo <xref:System.Windows.Forms.GroupBox>. Anche i controlli figlio di un controllo contenitore supportano le guide di allineamento.

## <a name="use-snaplines-to-place-a-control-by-outlining-its-size"></a>Utilizzare le guide di allineamento per posizionare un controllo in base alla relativa dimensione

1. Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.Button> . Non trascinarla nel form.

2. Spostare il puntatore del mouse sull'area di progettazione del form. Osservare che il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.Button> associata. Prendere nota anche delle guide di allineamento che sembrano suggerire posizioni allineate per il controllo <xref:System.Windows.Forms.Button>.

3. Fare clic e tenere premuto il pulsante del mouse.

4. Trascinare il puntatore del mouse intorno al form. Si noti che viene disegnata una struttura che indica la posizione e le dimensioni del controllo.

5. Trascinare il puntatore finché non viene allineato con un altro controllo nel form. Si noti che viene visualizzata una linea di allineamento per indicare l'allineamento.

6. Rilasciare il pulsante del mouse. Il controllo viene creato in corrispondenza della posizione e delle dimensioni indicate dal contorno.

## <a name="use-snaplines-when-dragging-a-control-from-the-toolbox"></a>Utilizzare le guide di allineamento quando si trascina un controllo dalla casella degli strumenti

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel form, ma non rilasciare il pulsante del mouse.

2. Spostare il puntatore del mouse sull'area di progettazione del form. Si noti che il puntatore cambia per indicare la posizione in cui verrà creato il nuovo controllo <xref:System.Windows.Forms.Button>.

3. Trascinare il puntatore del mouse intorno al form. Si notino le guide di allineamento che sembrano suggerire posizioni allineate per il controllo <xref:System.Windows.Forms.Button>. Trovare una posizione allineata con altri controlli.

4. Rilasciare il pulsante del mouse. Il controllo viene creato nella posizione indicata dalle guide di allineamento.

## <a name="resize-a-control-using-snaplines"></a>Ridimensionare un controllo utilizzando le guide di allineamento

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.

2. Ridimensionare il controllo <xref:System.Windows.Forms.Button> afferrando uno degli handle di ridimensionamento dell'angolo e il trascinamento. Per informazioni dettagliate, vedere [procedura: ridimensionare i controlli in Windows Forms](how-to-resize-controls-on-windows-forms.md).

3. Trascinare il quadratino di ridimensionamento fino a quando uno dei bordi del controllo <xref:System.Windows.Forms.Button> è allineato con un altro controllo. Si noti che viene visualizzata una guide di allineamento. Si noti inoltre che il quadratino di ridimensionamento viene agganciato alla posizione indicata dalla Guide di allineamento.

4. Ridimensionare il controllo <xref:System.Windows.Forms.Button> in direzioni diverse e allineare il quadratino di ridimensionamento a controlli diversi. Si noti come le guide di allineamento vengono visualizzate in diversi orientamenti per indicare l'allineamento.

## <a name="align-a-label-to-a-controls-text"></a>Allinea un'etichetta al testo di un controllo

1. Trascinare un controllo <xref:System.Windows.Forms.TextBox> dalla **Casella degli strumenti** al form. Quando si rilascia il controllo <xref:System.Windows.Forms.TextBox> sul form, fare clic sul glifo smart tag e selezionare l'opzione **imposta il testo su TextBox1** . Per informazioni dettagliate, vedere [procedura dettagliata: esecuzione di attività comuni usando gli smart tag nei controlli Windows Forms](performing-common-tasks-using-smart-tags-on-wf-controls.md).

2. Trascinare un controllo <xref:System.Windows.Forms.Label> dalla **Casella degli strumenti** al form.

3. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Label> , <xref:System.Windows.Forms.Control.AutoSize%2A> , su `true`. Si noti che i bordi del controllo vengono adattati per adattarsi al testo visualizzato.

4. Spostare il controllo <xref:System.Windows.Forms.Label> a sinistra del controllo <xref:System.Windows.Forms.TextBox>, in modo che sia allineato al bordo inferiore del controllo <xref:System.Windows.Forms.TextBox>. Si noti la guide di allineamento visualizzata lungo i bordi inferiore dei due controlli.

5. Spostare il controllo <xref:System.Windows.Forms.Label> leggermente verso l'alto, fino a quando il testo del <xref:System.Windows.Forms.Label> e il testo <xref:System.Windows.Forms.TextBox> non sono allineati. Si noti la linea di allineamento con stile diverso visualizzata, che indica quando i campi di testo di entrambi i controlli sono allineati.

## <a name="use-snaplines-with-keyboard-navigation"></a>Usare le guide di allineamento con la navigazione da tastiera

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form. Posizionarlo nell'angolo superiore sinistro del form.

2. Premere **Ctrl**+**freccia giù**. Si noti che il controllo sposta verso il basso il form fino alla prima posizione di allineamento orizzontale disponibile.

3. Premere **Ctrl**+**freccia giù** finché il controllo non raggiunge la fine del form. Si notino le posizioni occupate quando si sposta verso il basso il form.

4. Premere **Ctrl**+**freccia destra**. Si noti che il controllo passa attraverso il form alla prima posizione di allineamento verticale disponibile.

5. Premere **Ctrl**+**freccia destra** finché il controllo non raggiunge il lato del form. Prendere nota delle posizioni che occupano durante lo spostamento nel form.

6. Spostare il controllo intorno al form con una combinazione di tasti di direzione. Si notino le posizioni occupate dal controllo e le guide di allineamento che li accompagnano.

7. Premere **maiusc**+**tasti** di direzione per ridimensionare il controllo <xref:System.Windows.Forms.Button> in base a incrementi di un pixel.

8. Premere **Ctrl**+**MAIUSC**+i **tasti** di direzione per ridimensionare il controllo <xref:System.Windows.Forms.Button> negli incrementi della guide di allineamento.

## <a name="selectively-disable-snaplines"></a>Disabilitare selettivamente le guide di allineamento

1. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.

2. Fare doppio clic sull'icona del controllo <xref:System.Windows.Forms.Button> nella **Casella degli strumenti**. Si noti che viene visualizzato un nuovo controllo Button nella prima cella del controllo <xref:System.Windows.Forms.TableLayoutPanel>.

3. Fare doppio clic sull'icona del controllo <xref:System.Windows.Forms.Button> nella **casella degli strumenti** due volte. Questa operazione lascia una cella vuota nel controllo <xref:System.Windows.Forms.TableLayoutPanel>.

4. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nella cella vuota del controllo <xref:System.Windows.Forms.TableLayoutPanel>. Si noti che non vengono visualizzate guide di allineamento.

5. Trascinare il controllo <xref:System.Windows.Forms.Button> dal controllo <xref:System.Windows.Forms.TableLayoutPanel> e spostarlo intorno al controllo <xref:System.Windows.Forms.TableLayoutPanel>. Si noti che le guide di allineamento sono di nuovo visualizzate.

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

- Provare a annidare un controllo <xref:System.Windows.Forms.GroupBox> all'interno di un altro controllo <xref:System.Windows.Forms.GroupBox>. Inserire un controllo <xref:System.Windows.Forms.Button> all'interno del controllo <xref:System.Windows.Forms.GroupBox> figlio e un altro all'interno del controllo <xref:System.Windows.Forms.GroupBox> padre. Spostare i controlli <xref:System.Windows.Forms.Button> per verificare il modo in cui le guide di allineamento attraversano i limiti del contenitore.

- Creare una colonna di controlli <xref:System.Windows.Forms.TextBox> e una colonna corrispondente di controlli <xref:System.Windows.Forms.Label>. Impostare il valore della proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> dei controlli <xref:System.Windows.Forms.Label> su `true`. Utilizzare le guide di allineamento per spostare i controlli <xref:System.Windows.Forms.Label> in modo che il testo visualizzato venga allineato con il testo nei controlli <xref:System.Windows.Forms.TextBox>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione di controlli Windows Form con spaziatura, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md)
