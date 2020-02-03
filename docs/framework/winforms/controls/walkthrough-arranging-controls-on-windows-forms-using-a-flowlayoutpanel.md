---
title: Disporre i controlli con FlowLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- FlowLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
- controls [Windows Forms], arranging with FlowLayoutPanel
- layout [Windows Forms], walkthroughs
ms.assetid: a1744323-0316-49c2-992e-ebfc0a976b85
ms.openlocfilehash: 6df0a910ee346f319fbee835e5e632808630a99e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745408"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel"></a>Procedura dettagliata: disposizione dei controlli in Windows Form utilizzando FlowLayoutPanel

Alcune applicazioni richiedono che il form abbia un layout che possa adattarsi automaticamente alle eventuali modifiche alle dimensioni del form o del contenuto del form. Per usare un layout dinamico senza gestire gli eventi <xref:System.Windows.Forms.Control.Layout> in modo esplicito nel codice è possibile usare un pannello di layout.

I controlli <xref:System.Windows.Forms.FlowLayoutPanel> e <xref:System.Windows.Forms.TableLayoutPanel> offrono modalità intuitive per disporre i controlli nel form. Entrambi i controlli forniscono una funzionalità configurabile e automatica per la verifica delle posizioni relative dei controlli figlio contenuti e funzionalità di layout dinamico in fase di esecuzione in modo che i controlli figlio possano essere ridimensionati e riposizionati quando le dimensioni del form padre cambiano. I pannelli layout possono essere annidati in altri pannelli layout per consentire la realizzazione di interfacce utente sofisticate.

Il <xref:System.Windows.Forms.TableLayoutPanel> dispone il relativo contenuto in una griglia, fornendo una funzionalità simile all'elemento > della tabella HTML \<. Le celle vengono disposte in righe e colonne, e queste possono avere dimensioni diverse. Per altre informazioni, vedere [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).

<xref:System.Windows.Forms.FlowLayoutPanel> dispone i contenuti in una direzione di flusso specifica: orizzontale o verticale. Il contenuto può andare a capo da una riga a quella successiva o da una colonna a quella successiva. In alternativa, è possibile troncare il contenuto invece di usare il ritorno a capo. Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione di un progetto Windows Form

- Disposizione dei controlli in orizzontale e in verticale

- Modifica della direzione del flusso

- Inserimento di interruzioni di flusso

- Disposizione dei controlli con spaziatura e margini

- Inserimento di controlli con doppio clic nella casella degli strumenti

- Inserimento di un controllo disegnandone il contorno

- Inserimento di controlli con il cursore

- Riassegnazione dei controlli esistenti a un padre diverso

Al termine, sarà possibile comprendere il ruolo svolto da queste importanti funzionalità di layout.

## <a name="create-the-project"></a>Creare il progetto

1. In Visual Studio creare un progetto di applicazione basato su Windows denominato "FlowLayoutPanelExample" (**file** > **nuovo** > **progetto** > **Visual C#**  o **Visual Basic** > **desktop classico** > Windows Forms **applicazione**).

2. Selezionare il form in **Progettazione form**.

## <a name="arranging-controls-horizontally-and-vertically"></a>Disposizione dei controlli in orizzontale e in verticale
 Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> consente di posizionare i controlli lungo righe o colonne senza dover specificare in modo preciso la posizione di ogni singolo controllo.

 <xref:System.Windows.Forms.FlowLayoutPanel> consente l'adattamento delle dimensioni o del flusso dei controlli figlio quando cambiano le dimensioni del form padre.

### <a name="to-arrange-controls-horizontally-and-vertically-using-a-flowlayoutpanel"></a>Per disporre i controlli orizzontalmente e verticalmente usando FlowLayoutPanel

1. Trascinare un controllo <xref:System.Windows.Forms.FlowLayoutPanel> dalla **Casella degli strumenti** al form.

2. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** in <xref:System.Windows.Forms.FlowLayoutPanel>. Si noti come viene automaticamente spostato nell'angolo superiore sinistro del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

3. Trascinare un altro controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** in <xref:System.Windows.Forms.FlowLayoutPanel>. Si noti come il controllo <xref:System.Windows.Forms.Button> viene automaticamente spostato nella posizione accanto al primo controllo <xref:System.Windows.Forms.Button> . Se <xref:System.Windows.Forms.FlowLayoutPanel> non riesce a contenere i due controlli nella stessa riga perché è troppo piccolo, il nuovo controllo <xref:System.Windows.Forms.Button> viene automaticamente spostato nella riga successiva.

4. Trascinare diversi altri controlli <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** in <xref:System.Windows.Forms.FlowLayoutPanel>. Continuare a inserire controlli <xref:System.Windows.Forms.Button> finché uno non va a capo nella riga successiva.

5. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.FlowLayoutPanel> , <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> , su `false`. Si noti che i controlli figlio non scorrono più nella riga successiva, ma vengono spostati nella prima riga e troncati.

6. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.FlowLayoutPanel> , <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> , su `true`. Si noti che i controlli figlio vanno di nuovo a capo alla riga successiva.

7. Diminuire la larghezza del controllo <xref:System.Windows.Forms.FlowLayoutPanel> in modo che tutti i controlli <xref:System.Windows.Forms.Button> vengano spostati nella prima colonna.

8. Aumentare la larghezza del controllo <xref:System.Windows.Forms.FlowLayoutPanel> in modo che tutti i controlli <xref:System.Windows.Forms.Button> vengano spostati nella prima riga. Per poter inserire il controllo più largo, potrebbe essere necessario ridimensionare il form.

## <a name="changing-flow-direction"></a>Modifica della direzione del flusso
 La proprietà <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> consente di modificare la direzione secondo cui i controlli vengono disposti. È possibile disporre i controlli figlio da sinistra a destra, da destra a sinistra, dall'alto verso il basso o dal basso verso l'alto.

### <a name="to-change-the-flow-direction-in-a-flowlayoutpanel"></a>Per modificare la direzione del flusso in FlowLayoutPanel

1. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.FlowLayoutPanel> , <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> , su <xref:System.Windows.Forms.FlowDirection.TopDown>. Si noti che i controlli figlio vengono riorganizzati in una o più colonne, a seconda dell'altezza del controllo.

2. Ridimensionare <xref:System.Windows.Forms.FlowLayoutPanel> in modo che l'altezza sia inferiore alla colonna dei controlli <xref:System.Windows.Forms.Button> . Si noti che <xref:System.Windows.Forms.FlowLayoutPanel> riorganizza i controlli figlio in modo che scorrano nella colonna successiva. Continuare a diminuire l'altezza in modo da far scorrere i controlli figlio nelle colonne consecutive. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.FlowLayoutPanel> , <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> , su <xref:System.Windows.Forms.FlowDirection.RightToLeft>. Si noti che le posizioni dei controlli figlio sono invertite. Si osservi il layout quando si cambia il valore della proprietà <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> in <xref:System.Windows.Forms.FlowDirection.BottomUp>.

## <a name="inserting-flow-breaks"></a>Inserimento di interruzioni di flusso
 Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> fornisce la proprietà FlowBreak per i controlli figlio. Impostando il valore della proprietà FlowBreak su `true` , il controllo <xref:System.Windows.Forms.FlowLayoutPanel> interrompe il layout dei controlli nella direzione di flusso corrente ed esegue il wrapping alla riga o colonna successiva.

### <a name="to-insert-flow-breaks"></a>Per inserire le interruzioni del flusso

1. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.FlowLayoutPanel> , <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> , su <xref:System.Windows.Forms.FlowDirection.TopDown>.

2. Selezionare uno dei controlli <xref:System.Windows.Forms.Button> presenti al centro della colonna più a sinistra.

3. Impostare il valore della proprietà FlowBreak del controllo <xref:System.Windows.Forms.Button> su `true`. Si noti che la colonna viene interrotta e i controlli susseguenti al controllo <xref:System.Windows.Forms.Button> selezionato scorrono nella colonna successiva. Impostare il valore della proprietà FlowBreak del controllo <xref:System.Windows.Forms.Button> su `false` per ripristinare il comportamento originale.

## <a name="positioning-controls-using-docking-and-anchoring"></a>Posizionamento dei controlli usando l'ancoraggio e l'aggancio
 Il comportamento dell'ancoraggio e dell'aggancio dei controlli figlio è differente rispetto a quello di altri controlli contenitore. Sia l'ancoraggio che l'aggancio sono relativi al controllo più largo nella direzione del flusso.

### <a name="to-position-controls-using-docking-and-anchoring"></a>Per posizionare i controlli usando l'ancoraggio e l'aggancio

1. Aumentare la dimensione di <xref:System.Windows.Forms.FlowLayoutPanel> finché tutti i controlli <xref:System.Windows.Forms.Button> non vengono disposti in una colonna.

2. Selezionare il primo controllo <xref:System.Windows.Forms.Button> . Aumentarne la larghezza in modo che diventi circa il doppio dell'ampiezza degli altri controlli <xref:System.Windows.Forms.Button> .

3. Selezionare il secondo controllo <xref:System.Windows.Forms.Button> . Modificare il valore della proprietà <xref:System.Windows.Forms.Control.Anchor%2A> in <xref:System.Windows.Forms.AnchorStyles.Right>. Si noti che è stato spostato in modo che il bordo destro sia allineato con il bordo destro del primo controllo <xref:System.Windows.Forms.Button> .

4. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.Anchor%2A> su <xref:System.Windows.Forms.AnchorStyles.Right> e <xref:System.Windows.Forms.AnchorStyles.Left>. Si noti come la dimensione diventi uguale all'ampiezza del primo controllo <xref:System.Windows.Forms.Button> .

5. Selezionare il terzo controllo <xref:System.Windows.Forms.Button> . Modificare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> in <xref:System.Windows.Forms.DockStyle.Fill>. Si noti come la dimensione diventi uguale all'ampiezza del primo controllo <xref:System.Windows.Forms.Button> .

## <a name="arranging-controls-using-padding-and-margins"></a>Disposizione dei controlli con spaziatura e margini
 È anche possibile disporre i controlli in <xref:System.Windows.Forms.FlowLayoutPanel> modificando le proprietà <xref:System.Windows.Forms.Control.Padding%2A> e <xref:System.Windows.Forms.Control.Margin%2A> .

 La proprietà <xref:System.Windows.Forms.Control.Padding%2A> consente di determinare il posizionamento dei controlli in una cella del controllo <xref:System.Windows.Forms.FlowLayoutPanel> . Specifica la spaziatura tra i controlli figlio e il bordo del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

 La proprietà <xref:System.Windows.Forms.Control.Margin%2A> consente di determinare la spaziatura tra i controlli.

### <a name="to-arrange-controls-using-the-padding-and-margin-properties"></a>Per disporre i controlli usando le proprietà per spaziatura e margini

1. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.FlowLayoutPanel> , <xref:System.Windows.Forms.Control.Dock%2A> , su <xref:System.Windows.Forms.DockStyle.Fill>. Se il form è sufficientemente ampio, i controlli <xref:System.Windows.Forms.Button> verranno spostati nella prima colonna del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

2. Modificare il valore della proprietà <xref:System.Windows.Forms.FlowLayoutPanel> del controllo <xref:System.Windows.Forms.Control.Padding%2A> espandendo la voce <xref:System.Windows.Forms.Control.Padding%2A> nella finestra **Proprietà** e impostando la proprietà <xref:System.Windows.Forms.Padding.All%2A> su **20**. Per ulteriori informazioni, vedere [procedura dettagliata: layout Windows Forms controlli con spaziatura interna, margini e proprietà AutoSize](windows-forms-controls-padding-autosize.md). Si noti come i controlli figlio vengano spostati verso il centro del controllo <xref:System.Windows.Forms.FlowLayoutPanel> . L'aumento del valore della proprietà <xref:System.Windows.Forms.Control.Padding%2A> provoca l'allontanamento dei controlli figlio dai bordi del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

3. Selezionare tutti i controlli <xref:System.Windows.Forms.Button> in <xref:System.Windows.Forms.FlowLayoutPanel> e impostare il valore della proprietà <xref:System.Windows.Forms.Control.Margin%2A> su **20**. La spaziatura tra i controlli <xref:System.Windows.Forms.Button> aumenta in modo da allontanarli tra loro. Potrebbe essere necessario ingrandire il controllo <xref:System.Windows.Forms.FlowLayoutPanel> in modo da vedere tutti i controlli figlio.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Inserimento di controlli con doppio clic nella casella degli strumenti
 <xref:System.Windows.Forms.FlowLayoutPanel> può essere compilato facendo doppio clic sui controlli nella **Casella degli strumenti**.

### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>Per inserire i controlli facendo doppio clic nella Casella degli strumenti

1. Fare doppio clic sull'icona del controllo <xref:System.Windows.Forms.Button> nella **Casella degli strumenti**. Un nuovo controllo <xref:System.Windows.Forms.Button> viene visualizzato nel controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

2. Fare doppio clic su diversi altri controlli nella **Casella degli strumenti**. Si noti come nel controllo <xref:System.Windows.Forms.FlowLayoutPanel> vengano visualizzati in successione i nuovi controlli.

## <a name="inserting-a-control-by-drawing-its-outline"></a>Inserimento di un controllo disegnandone il contorno
 È possibile inserire un controllo in <xref:System.Windows.Forms.FlowLayoutPanel> e determinarne la dimensione disegnandone il contorno in una cella.

### <a name="to-insert-a-control-by-drawing-its-outline"></a>Per inserire un controllo disegnandone il contorno

1. Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.Button> . Non trascinarla nel form.

2. Spostare il puntatore del mouse sul controllo <xref:System.Windows.Forms.FlowLayoutPanel> . Osservare che il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.Button> associata.

3. Fare clic e tenere premuto il pulsante del mouse.

4. Trascinare il puntatore del mouse per disegnare la struttura del controllo <xref:System.Windows.Forms.Button> . Una volta ottenuta la dimensione desiderata, rilasciare il pulsante del mouse. Si noti che il controllo <xref:System.Windows.Forms.Button> viene creato nella prima posizione aperta del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

## <a name="inserting-controls-using-the-insertion-bar"></a>Inserimento dei controlli con la barra di inserimento
 In un controllo <xref:System.Windows.Forms.FlowLayoutPanel> , è possibile inserire i controlli in una posizione specifica. Quando si trascina un controllo in un'area client del controllo <xref:System.Windows.Forms.FlowLayoutPanel> , viene visualizzata una barra di inserimento per indicare dove il controllo verrà inserito.

### <a name="to-insert-a-control-using-the-caret"></a>Per inserire un controllo usando il cursore

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** nel controllo <xref:System.Windows.Forms.FlowLayoutPanel> e puntare sullo spazio tra i due controlli <xref:System.Windows.Forms.Button> . Si noti che viene disegnata una barra di inserimento, che indica il punto in cui verrà inserita la <xref:System.Windows.Forms.Button> quando viene rilasciata nel controllo <xref:System.Windows.Forms.FlowLayoutPanel>. Prima di rilasciare il nuovo controllo <xref:System.Windows.Forms.Button> in <xref:System.Windows.Forms.FlowLayoutPanel> , spostare il puntatore del mouse per osservare come si muove la barra di inserimento.

2. Rilasciare il nuovo controllo <xref:System.Windows.Forms.Button> in <xref:System.Windows.Forms.FlowLayoutPanel> . Si noti che il nuovo controllo <xref:System.Windows.Forms.Button> non è allineato agli altri perché è specificato un valore differente per la proprietà <xref:System.Windows.Forms.Control.Margin%2A> .

## <a name="reassigning-existing-controls-to-a-different-parent"></a>Riassegnazione dei controlli esistenti a un padre diverso
 È possibile assegnare i controlli presenti nel form a un nuovo controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

### <a name="to-reparent-existing-controls"></a>Per assegnare un nuovo elemento padre ai controlli esistenti

1. Trascinare i tre controlli <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form. Posizionarli uno accanto a altro, ma lasciarli non allineati.

2. Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> . Non trascinarla nel form.

3. Spostare il puntatore del mouse accanto ai tre controlli <xref:System.Windows.Forms.Button> . Osservare che il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> associata.

4. Fare clic e tenere premuto il pulsante del mouse.

5. Trascinare il puntatore del mouse per disegnare la struttura del controllo <xref:System.Windows.Forms.FlowLayoutPanel> . Disegnare la struttura intorno ai tre controlli <xref:System.Windows.Forms.Button> .

6. Rilasciare il pulsante del mouse. I tre controlli <xref:System.Windows.Forms.Button> vengono inseriti nel controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

## <a name="next-steps"></a>Passaggi successivi
 È possibile ottenere un layout complesso usando i pannelli e i controlli di layout in combinazione. Per approfondire l'argomento, si consiglia di effettuare le seguenti operazioni:

- Ridimensionare un controllo <xref:System.Windows.Forms.Button> per una dimensione più grande e notare l'effetto sul layout.

- I pannelli layout possono contenere altri pannelli layout. Provare a rilasciare un controllo <xref:System.Windows.Forms.TableLayoutPanel> nel controllo esistente.

- Ancorare il controllo <xref:System.Windows.Forms.FlowLayoutPanel> al form padre. Ridimensionare il form e notare l'effetto sul layout.

- Impostare la proprietà <xref:System.Windows.Forms.Control.Visible%2A> di un controllo su `false` e notare come <xref:System.Windows.Forms.FlowLayoutPanel> adatta il flusso in risposta.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Panoramica sulla proprietà AutoSize](autosize-property-overview.md)
- [Procedura: Ancorare i controlli in Windows Form](how-to-dock-controls-on-windows-forms.md)
- [Procedura: Agganciare i controlli in Windows Form](how-to-anchor-controls-on-windows-forms.md)
- [Procedura dettagliata: disposizione di controlli Windows Form usando spaziatura, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md)
