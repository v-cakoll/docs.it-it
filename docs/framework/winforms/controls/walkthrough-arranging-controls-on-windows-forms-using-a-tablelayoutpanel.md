---
title: 'Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: f337164043014ed14d42e219f26ee2ec8be06662
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2019
ms.locfileid: "56305844"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel
Alcune applicazioni richiedono che il form abbia un layout che possa adattarsi automaticamente alle eventuali modifiche alle dimensioni del form o del contenuto del form. Per usare un layout dinamico senza gestire gli eventi <xref:System.Windows.Forms.Control.Layout> in modo esplicito nel codice è possibile usare un pannello di layout.  
  
 I controlli <xref:System.Windows.Forms.FlowLayoutPanel> e <xref:System.Windows.Forms.TableLayoutPanel> offrono modalità intuitive per disporre i controlli nel form. Entrambi i controlli forniscono una funzionalità configurabile e automatica per la verifica delle posizioni relative dei controlli figlio contenuti e funzionalità di layout dinamico in fase di esecuzione in modo che i controlli figlio possano essere ridimensionati e riposizionati quando le dimensioni del form padre cambiano. I pannelli layout possono essere annidati in altri pannelli layout per consentire la realizzazione di interfacce utente sofisticate.  
  
 <xref:System.Windows.Forms.FlowLayoutPanel> dispone i contenuti in una direzione di flusso specifica: orizzontale o verticale. Il contenuto può andare a capo da una riga a quella successiva o da una colonna a quella successiva. In alternativa, è possibile troncare il contenuto invece di usare il ritorno a capo. Per altre informazioni, vedere [Procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
 Il <xref:System.Windows.Forms.TableLayoutPanel> dispone i contenuti in una griglia, fornendo una funzionalità simile al codice HTML \<tabella > elemento. Il <xref:System.Windows.Forms.TableLayoutPanel> controllo consente di posizionare i controlli in un layout griglia senza che sia necessario specificare in modo preciso la posizione di ogni singolo controllo. Le celle vengono disposte in righe e colonne, e queste possono avere dimensioni diverse. Le celle possono essere unite in righe e colonne. Le celle possono contenere qualsiasi elemento è un modulo può contenere e un comportamento per la maggior parte degli altri aspetti dei contenitori.  
  
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo fornisce inoltre una funzionalità di ridimensionamento proporzionale in fase di esecuzione, in modo che il layout può cambiare facilmente in base al ridimensionamento del form. In questo modo il <xref:System.Windows.Forms.TableLayoutPanel> controllo è particolarmente utile per scopi come form di immissione dati e le applicazioni localizzate. Per altre informazioni, vedere [Procedura dettagliata: Creazione di un Form Windows ridimensionabile per immissione di dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)) e [procedura dettagliata: Creazione di un Form Windows localizzabili](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).  
  
 In generale, è consigliabile non usare un <xref:System.Windows.Forms.TableLayoutPanel> controllo come contenitore per l'intero layout. Usare <xref:System.Windows.Forms.TableLayoutPanel> controlli per fornire funzionalità di ridimensionamento proporzionale alle parti del layout.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione di un progetto Windows Form  
  
-   Disposizione dei controlli in righe e colonne  
  
-   Riga di impostazione e le proprietà delle colonne  
  
-   Spanning righe e colonne con un controllo  
  
-   Gestione automatica degli overflow  
  
-   Inserimento di controlli con doppio clic nella casella degli strumenti  
  
-   Inserimento di un controllo disegnandone il contorno  
  
-   Riassegnazione dei controlli esistenti a un padre diverso  
  
 Al termine, si avrà una migliore comprensione del ruolo svolto da queste importanti funzionalità di layout.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un progetto applicazione Windows denominato "TableLayoutPanelExample". Per altre informazioni, vedere [Procedura: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) .  
  
2.  Selezionare il form nel **Windows** **progettazione form**.  
  
## <a name="arranging-controls-in-rows-and-columns"></a>Disposizione dei controlli in righe e colonne  
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo consente di memorizzare facilmente disporre i controlli in righe e colonne.  
  
#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>Per disporre i controlli in righe e colonne usando TableLayoutPanel  
  
1.  Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form. Si noti che, per impostazione predefinita, il <xref:System.Windows.Forms.TableLayoutPanel> controllo dispone di quattro celle.  
  
2.  Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nel <xref:System.Windows.Forms.TableLayoutPanel> controllano e inserirla in una delle celle. Si noti che il <xref:System.Windows.Forms.Button> controllo viene creato all'interno della cella selezionata.  
  
3.  Trascinare tre ulteriori <xref:System.Windows.Forms.Button> dei controlli il **casella degli strumenti** nel <xref:System.Windows.Forms.TableLayoutPanel> controllo, in modo che ogni cella contiene un pulsante.  
  
4.  Selezionare il quadratino di ridimensionamento verticale tra le due colonne e spostarlo verso sinistra. Si noti che il <xref:System.Windows.Forms.Button> controlli nella prima colonna vengono ridimensionati per una larghezza inferiore, mentre la dimensione del <xref:System.Windows.Forms.Button> controlli nella seconda colonna rimane invariata.  
  
5.  Selezionare il quadratino di ridimensionamento verticale tra le due colonne e spostarlo a destra. Si noti che il <xref:System.Windows.Forms.Button> controlla nella prima colonna restituiti fino alle dimensioni originali, mentre il <xref:System.Windows.Forms.Button> controlli nella seconda colonna vengono spostati verso destra.  
  
6.  Spostare il quadratino di ridimensionamento orizzontale su e giù per visualizzare l'effetto sui controlli del pannello.  
  
## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Il posizionamento dei controlli all'interno delle celle mediante aggancio e ancoraggio  
 Il comportamento di ancoraggio dei controlli figlio in un <xref:System.Windows.Forms.TableLayoutPanel> è diverso da quello degli altri controlli contenitore. Il comportamento di ancoraggio dei controlli figlio è quello utilizzato per altri controlli contenitore.  
  
#### <a name="positioning-controls-within-cells"></a>Il posizionamento dei controlli all'interno delle celle  
  
1.  Selezionare il primo <xref:System.Windows.Forms.Button> controllo. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> in <xref:System.Windows.Forms.DockStyle.Fill>. Si noti che il <xref:System.Windows.Forms.Button> controllo si espande per riempire la cella.  
  
2.  Selezionare uno degli altri <xref:System.Windows.Forms.Button> controlli. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.Anchor%2A> in <xref:System.Windows.Forms.AnchorStyles.Right>. Si noti che è stato spostato in modo che il bordo destro è vicino al bordo destro della cella. La distanza tra i bordi è la somma del <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Margin%2A> proprietà e il pannello <xref:System.Windows.Forms.Control.Padding%2A> proprietà.  
  
3.  Modificare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà <xref:System.Windows.Forms.AnchorStyles.Right> e <xref:System.Windows.Forms.AnchorStyles.Left>. Si noti che il controllo viene ridimensionato in base alla larghezza della cella, con la <xref:System.Windows.Forms.Control.Margin%2A> e <xref:System.Windows.Forms.Control.Padding%2A> presi in considerazione i valori.  
  
4.  Ripetere i passaggi 2 e 3 con il <xref:System.Windows.Forms.AnchorStyles.Top> e <xref:System.Windows.Forms.AnchorStyles.Bottom> stili.  
  
## <a name="setting-row-and-column-properties"></a>Riga di impostazione e le proprietà delle colonne  
 È possibile impostare singole proprietà di righe e colonne usando il <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> e <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> raccolte.  
  
#### <a name="to-set-row-and-column-properties"></a>Per impostare le proprietà di riga e colonna  
  
1.  Selezionare il <xref:System.Windows.Forms.TableLayoutPanel> controllare nel **finestra di progettazione Windows Form**.  
  
2.  Nel **delle proprietà** windows, aprire il <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> raccolta facendo clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) pulsante accanto al **colonne** voce.  
  
3.  Selezionare la prima colonna e modificare il valore del relativo <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà <xref:System.Windows.Forms.SizeType.AutoSize>. Fare clic su **OK** per accettare la modifica. Si noti che la larghezza della prima colonna viene ridotta per adattarsi il <xref:System.Windows.Forms.Button> controllo. Si noti inoltre che la larghezza della colonna non è ridimensionabile.  
  
4.  Nel **delle proprietà** finestra, aprire il <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> raccolta e selezionare la prima colonna. Modificare il valore della proprietà <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> in <xref:System.Windows.Forms.SizeType.Percent>. Fare clic su **OK** per accettare la modifica. Ridimensionare il <xref:System.Windows.Forms.TableLayoutPanel> il controllo a una larghezza maggiore e che si espande la larghezza della prima colonna. Ridimensionare il <xref:System.Windows.Forms.TableLayoutPanel> il controllo a una larghezza inferiore e si noti che i pulsanti nella prima colonna vengono ridimensionati per adattarsi alla cella. Si noti inoltre che la larghezza della colonna è ridimensionabile.  
  
5.  Nel **delle proprietà** finestra, aprire il <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> raccolta e selezionare tutte le colonne elencate. Impostare il valore di ogni <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà <xref:System.Windows.Forms.SizeType.Percent>. Fare clic su **OK** per accettare la modifica. Ripetere l'operazione con il <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> raccolta.  
  
6.  Selezionare uno dei quadratini di ridimensionamento angolo e ridimensionare la larghezza e altezza del <xref:System.Windows.Forms.TableLayoutPanel> controllo. Si noti che le righe e colonne vengono ridimensionate come il <xref:System.Windows.Forms.TableLayoutPanel> modifiche apportate alle dimensioni del controllo. Si noti inoltre che le righe e colonne siano ridimensionabile con orizzontale e verticale quadratini di ridimensionamento.  
  
## <a name="spanning-rows-and-columns-with-a-control"></a>Spanning righe e colonne con un controllo  
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo aggiunge diverse nuove proprietà ai controlli in fase di progettazione. Due di queste proprietà sono `RowSpan` e `ColumnSpan`. È possibile usare queste proprietà per rendere un intervallo di controllo più di una riga o colonna.  
  
#### <a name="to-span-rows-and-columns-with-a-control"></a>Per inserire righe e colonne con un controllo  
  
1.  Selezionare il <xref:System.Windows.Forms.Button> controllo nella prima riga e della prima colonna.  
  
2.  Nel **delle proprietà** windows, modificare il valore della `ColumnSpan` proprietà **2**. Si noti che il <xref:System.Windows.Forms.Button> controllo occupa la prima colonna e la seconda colonna. Si noti inoltre che una riga supplementare è stato aggiunto per gestire questa modifica.  
  
3.  Ripetere il passaggio 2 per il `RowSpan` proprietà.  
  
## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Inserimento di controlli con doppio clic nella casella degli strumenti  
 <xref:System.Windows.Forms.TableLayoutPanel> può essere compilato facendo doppio clic sui controlli nella **Casella degli strumenti**.  
  
#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>Per inserire i controlli facendo doppio clic nella Casella degli strumenti  
  
1.  Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.  
  
2.  Fare doppio clic sull'icona del controllo <xref:System.Windows.Forms.Button> nella **Casella degli strumenti**. Si noti che un nuovo controllo pulsante visualizzato nei <xref:System.Windows.Forms.TableLayoutPanel> prima cella del controllo.  
  
3.  Fare doppio clic su diversi altri controlli nella **Casella degli strumenti**. Si noti che i nuovi controlli visualizzata successivamente nel <xref:System.Windows.Forms.TableLayoutPanel> celle non occupato del controllo. Si noti anche che il <xref:System.Windows.Forms.TableLayoutPanel> controllo si espande per inserire i nuovi controlli se nessuna cella open è disponibile.  
  
## <a name="automatic-handling-of-overflows"></a>Gestione automatica degli overflow  
 Quando si inseriscono i controlli nel <xref:System.Windows.Forms.TableLayoutPanel> (controllo), esauriscano le celle vuote per i nuovi controlli. Il <xref:System.Windows.Forms.TableLayoutPanel> controllo gestisce automaticamente questa situazione, aumentando il numero di celle.  
  
#### <a name="to-observe-automatic-handling-of-overflows"></a>Per osservare la gestione automatica degli overflow  
  
1.  Se sono presenti nelle celle vuote ancora la <xref:System.Windows.Forms.TableLayoutPanel> controllare, continuare a inserire nuovi <xref:System.Windows.Forms.Button> controlla fino al <xref:System.Windows.Forms.TableLayoutPanel> controllo è pieno.  
  
2.  Una volta il <xref:System.Windows.Forms.TableLayoutPanel> controllo è completo, fare doppio clic sui <xref:System.Windows.Forms.Button> icona nel **della casella degli strumenti** per inserire un altro <xref:System.Windows.Forms.Button> controllo. Si noti che il <xref:System.Windows.Forms.TableLayoutPanel> controllo Crea nuove celle per inserire il nuovo controllo. Inserire alcuni altri controlli e osservare il comportamento di ridimensionamento.  
  
3.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.TableLayoutPanel> , <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> , su <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Fare doppio clic sui <xref:System.Windows.Forms.Button> icona nel **della casella degli strumenti** per inserire <xref:System.Windows.Forms.Button> controlla fino al <xref:System.Windows.Forms.TableLayoutPanel> è pieno controllo. Fare doppio clic il <xref:System.Windows.Forms.Button> icona nel **della casella degli strumenti** nuovamente. Si noti che viene visualizzato un messaggio di errore dal **finestra di progettazione Windows Form** che informa che non è possibile creare righe e colonne aggiuntive.  
  
## <a name="inserting-a-control-by-drawing-its-outline"></a>Inserimento di un controllo disegnandone il contorno  
 È possibile inserire un controllo in <xref:System.Windows.Forms.TableLayoutPanel> e determinarne la dimensione disegnandone il contorno in una cella.  
  
#### <a name="to-insert-a-control-by-drawing-its-outline"></a>Per inserire un controllo disegnandone il contorno  
  
1.  Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.  
  
2.  Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.Button> . Non trascinarla nel form.  
  
3.  Spostare il puntatore del mouse sul controllo <xref:System.Windows.Forms.TableLayoutPanel> . Osservare che il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.Button> associata.  
  
4.  Fare clic e tenere premuto il pulsante del mouse.  
  
5.  Trascinare il puntatore del mouse per disegnare la struttura del controllo <xref:System.Windows.Forms.Button> . Una volta ottenuta la dimensione desiderata, rilasciare il pulsante del mouse. Si noti che il <xref:System.Windows.Forms.Button> controllo viene memorizzato nella cella in cui è stata disegnata la struttura del controllo.  
  
## <a name="multiple-controls-within-cells-are-not-permitted"></a>Non sono consentiti più controlli all'interno delle celle  
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo può contenere solo un controllo figlio per ogni cella.  
  
#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>Per dimostrare che non sono consentiti più controlli all'interno delle celle  
  
-   Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nel <xref:System.Windows.Forms.TableLayoutPanel> controllano e rilasciarlo in una delle celle occupate. Si noti che il <xref:System.Windows.Forms.TableLayoutPanel> controllo non consente di eliminare il <xref:System.Windows.Forms.Button> controllo nella cella occupata.  
  
## <a name="swapping-controls"></a>Scambio di controlli  
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo consente lo scambio dei controlli tra due diverse celle.  
  
#### <a name="to-swap-controls"></a>Per spostarsi tra controlli  
  
-   Trascinare uno del <xref:System.Windows.Forms.Button> controlli da una cella occupata e rilasciarlo in un'altra cella occupata. Si noti che i due controlli vengono spostati da una cella in altra.  
  
## <a name="next-steps"></a>Passaggi successivi  
 È possibile ottenere un layout complesso usando i pannelli e i controlli di layout in combinazione. Per approfondire l'argomento, si consiglia di effettuare le seguenti operazioni:  
  
-   Provare a ridimensionare uno del <xref:System.Windows.Forms.Button> controlli a una dimensione più grande e notare l'effetto sul layout.  
  
-   Incollare una selezione di più controlli nel <xref:System.Windows.Forms.TableLayoutPanel> controllare e prendere nota l'inserimento di controlli.  
  
-   I pannelli layout possono contenere altri pannelli layout. Provare a rilasciare un controllo <xref:System.Windows.Forms.TableLayoutPanel> nel controllo esistente.  
  
-   Ancorare il controllo <xref:System.Windows.Forms.TableLayoutPanel> al form padre. Ridimensionare il form e notare l'effetto sul layout.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers (Esperienza utente di Microsoft Windows, Linee guida ufficiali per analisti e sviluppatori dell'interfaccia utente). Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
- [Procedura dettagliata: Creazione di un Form Windows ridimensionabile per immissione dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [Procedura dettagliata: Creazione di un Form Windows localizzabili](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [Procedure consigliate per il controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)
- [Panoramica sulla proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
- [Procedura: Ancorare i controlli in Windows Form](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)
- [Procedura: Ancoraggio dei controlli in Windows Form](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
- [Procedura dettagliata: Definire il layout dei Windows Form usando spaziatura, margini e la proprietà AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
