---
title: Disposizione di controlli mediante TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 803a56f6416cf3b718890e96cf9f36ae6c4ee471
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740325"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Procedura dettagliata: disposizione dei controlli in Windows Form utilizzando TableLayoutPanel

Alcune applicazioni richiedono che il form abbia un layout che possa adattarsi automaticamente alle eventuali modifiche alle dimensioni del form o del contenuto del form. Per usare un layout dinamico senza gestire gli eventi <xref:System.Windows.Forms.Control.Layout> in modo esplicito nel codice è possibile usare un pannello di layout.

I controlli <xref:System.Windows.Forms.FlowLayoutPanel> e <xref:System.Windows.Forms.TableLayoutPanel> offrono modalità intuitive per disporre i controlli nel form. Entrambi i controlli forniscono una funzionalità configurabile e automatica per la verifica delle posizioni relative dei controlli figlio contenuti e funzionalità di layout dinamico in fase di esecuzione in modo che i controlli figlio possano essere ridimensionati e riposizionati quando le dimensioni del form padre cambiano. I pannelli layout possono essere annidati in altri pannelli layout per consentire la realizzazione di interfacce utente sofisticate.

<xref:System.Windows.Forms.FlowLayoutPanel> dispone i contenuti in una direzione di flusso specifica: orizzontale o verticale. Il contenuto può andare a capo da una riga a quella successiva o da una colonna a quella successiva. In alternativa, è possibile troncare il contenuto invece di usare il ritorno a capo. Per ulteriori informazioni, vedere [procedura dettagliata: disposizione dei controlli in Windows Forms tramite FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

Il <xref:System.Windows.Forms.TableLayoutPanel> dispone il relativo contenuto in una griglia, fornendo una funzionalità simile all'elemento > della tabella HTML \<. Il controllo <xref:System.Windows.Forms.TableLayoutPanel> consente di posizionare i controlli in un layout di griglia senza che sia necessario specificare esattamente la posizione di ogni singolo controllo. Le celle vengono disposte in righe e colonne, e queste possono avere dimensioni diverse. Le celle possono essere unite tra righe e colonne. Le celle possono contenere qualsiasi elemento che un modulo può contenere e comportarsi nella maggior parte degli altri aspetti come contenitori.

Il controllo <xref:System.Windows.Forms.TableLayoutPanel> fornisce anche una funzionalità di ridimensionamento proporzionale in fase di esecuzione, in modo che il layout possa variare senza problemi quando il form viene ridimensionato. In questo modo il controllo <xref:System.Windows.Forms.TableLayoutPanel> è particolarmente adatto a scopi quali moduli di immissione dati e applicazioni localizzate. Per ulteriori informazioni, vedere [procedura dettagliata: creazione di un Windows Form ridimensionabile per l'immissione di dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)) e [procedura dettagliata: creazione di un Windows form localizzabile](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).

In generale, non è consigliabile usare un controllo <xref:System.Windows.Forms.TableLayoutPanel> come contenitore per l'intero layout. Usare <xref:System.Windows.Forms.TableLayoutPanel> controlli per fornire funzionalità di ridimensionamento proporzionale alle parti del layout.

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione di un progetto Windows Form

- Disposizione di controlli in righe e colonne

- Impostazione delle proprietà di righe e colonne

- Spanning di righe e colonne con un controllo

- Gestione automatica degli overflow

- Inserimento di controlli con doppio clic nella casella degli strumenti

- Inserimento di un controllo disegnandone il contorno

- Riassegnazione dei controlli esistenti a un padre diverso

Al termine, si avrà una migliore comprensione del ruolo svolto da queste importanti funzionalità di layout.

## <a name="creating-the-project"></a>Creazione del progetto

Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.

#### <a name="to-create-the-project"></a>Per creare il progetto

1. Creare un progetto di applicazione Windows denominato "TableLayoutPanelExample". Per altre informazioni, vedere [procedura: creare un Windows Forms Application progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) .

2. Selezionare il form in progettazione **Windows** **form**.

## <a name="arranging-controls-in-rows-and-columns"></a>Disposizione di controlli in righe e colonne

Il controllo <xref:System.Windows.Forms.TableLayoutPanel> consente di disporre facilmente i controlli in righe e colonne.

#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>Per disporre i controlli in righe e colonne utilizzando TableLayoutPanel

1. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form. Si noti che, per impostazione predefinita, il controllo <xref:System.Windows.Forms.TableLayoutPanel> dispone di quattro celle.

2. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel controllo <xref:System.Windows.Forms.TableLayoutPanel> e rilasciarlo in una delle celle. Si noti che il controllo <xref:System.Windows.Forms.Button> viene creato all'interno della cella selezionata.

3. Trascinare altri tre <xref:System.Windows.Forms.Button> controlli dalla **casella degli strumenti** nel controllo <xref:System.Windows.Forms.TableLayoutPanel>, in modo che ogni cella contenga un pulsante.

4. Estrarre il quadratino di ridimensionamento verticale tra le due colonne e spostarlo a sinistra. Si noti che i controlli <xref:System.Windows.Forms.Button> nella prima colonna vengono ridimensionati a una larghezza inferiore, mentre la dimensione dei controlli <xref:System.Windows.Forms.Button> nella seconda colonna rimane invariata.

5. Estrarre il quadratino di ridimensionamento verticale tra le due colonne e spostarlo a destra. Si noti che i controlli <xref:System.Windows.Forms.Button> nella prima colonna restituiscono le dimensioni originali, mentre i controlli <xref:System.Windows.Forms.Button> nella seconda colonna vengono spostati a destra.

6. Spostare il quadratino di ridimensionamento orizzontale verso l'alto e verso il basso per vedere l'effetto sui controlli nel pannello.

## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Posizionamento di controlli all'interno di celle usando l'ancoraggio e l'aggancio

Il comportamento di ancoraggio dei controlli figlio in un <xref:System.Windows.Forms.TableLayoutPanel> differisce dal comportamento di altri controlli contenitore. Il comportamento di ancoraggio dei controlli figlio è identico a quello di altri controlli contenitore.

#### <a name="positioning-controls-within-cells"></a>Posizionamento di controlli all'interno di celle

1. Selezionare il primo controllo <xref:System.Windows.Forms.Button>. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> in <xref:System.Windows.Forms.DockStyle.Fill>. Si noti che il controllo <xref:System.Windows.Forms.Button> si espande per riempire la cella.

2. Selezionare uno degli altri controlli <xref:System.Windows.Forms.Button>. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.Anchor%2A> in <xref:System.Windows.Forms.AnchorStyles.Right>. Si noti che viene spostato in modo che il bordo destro sia vicino al bordo destro della cella. La distanza tra i bordi è la somma della proprietà <xref:System.Windows.Forms.Control.Margin%2A> del controllo <xref:System.Windows.Forms.Button> e della proprietà <xref:System.Windows.Forms.Control.Padding%2A> del pannello.

3. Modificare il valore della proprietà <xref:System.Windows.Forms.Control.Anchor%2A> del controllo <xref:System.Windows.Forms.Button> in <xref:System.Windows.Forms.AnchorStyles.Right> e <xref:System.Windows.Forms.AnchorStyles.Left>. Si noti che il controllo viene ridimensionato in base alla larghezza della cella, con i valori <xref:System.Windows.Forms.Control.Margin%2A> e <xref:System.Windows.Forms.Control.Padding%2A> presi in considerazione.

4. Ripetere i passaggi 2 e 3 con gli stili <xref:System.Windows.Forms.AnchorStyles.Top> e <xref:System.Windows.Forms.AnchorStyles.Bottom>.

## <a name="setting-row-and-column-properties"></a>Impostazione delle proprietà di righe e colonne

È possibile impostare singole proprietà di righe e colonne utilizzando le raccolte <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> e <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>.

#### <a name="to-set-row-and-column-properties"></a>Per impostare le proprietà di righe e colonne

1. Selezionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> nel **Progettazione Windows Form**.

2. Nelle finestre **Proprietà** aprire la raccolta <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> facendo clic sui puntini di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla voce **colonne** .

3. Selezionare la prima colonna e modificare il valore della proprietà <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> in <xref:System.Windows.Forms.SizeType.AutoSize>. Fare clic su **OK** per accettare la modifica. Si noti che la larghezza della prima colonna viene ridotta per adattarsi al controllo <xref:System.Windows.Forms.Button>. Si noti inoltre che la larghezza della colonna non è ridimensionabile.

4. Nella finestra **Proprietà** aprire la raccolta <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> e selezionare la prima colonna. Modificare il valore della proprietà <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> in <xref:System.Windows.Forms.SizeType.Percent>. Fare clic su **OK** per accettare la modifica. Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> a una larghezza maggiore e notare che la larghezza della prima colonna viene espansa. Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> a una larghezza inferiore e notare che i pulsanti nella prima colonna vengono ridimensionati per adattarsi alla cella. Si noti inoltre che la larghezza della colonna è ridimensionabile.

5. Nella finestra **Proprietà** aprire la raccolta <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> e selezionare tutte le colonne elencate. Impostare il valore di ogni proprietà <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> su <xref:System.Windows.Forms.SizeType.Percent>. Fare clic su **OK** per accettare la modifica. Ripetere il <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> insieme.

6. Acquisire uno degli handle di ridimensionamento dell'angolo e ridimensionare sia la larghezza che l'altezza del controllo <xref:System.Windows.Forms.TableLayoutPanel>. Si noti che le righe e le colonne vengono ridimensionate quando le dimensioni del controllo <xref:System.Windows.Forms.TableLayoutPanel> cambiano. Si noti inoltre che le righe e le colonne sono ridimensionabili con gli handle di ridimensionamento orizzontale e verticale.

## <a name="spanning-rows-and-columns-with-a-control"></a>Spanning di righe e colonne con un controllo

Il controllo <xref:System.Windows.Forms.TableLayoutPanel> aggiunge diverse nuove proprietà ai controlli in fase di progettazione. Due di queste proprietà sono `RowSpan` e `ColumnSpan`. È possibile utilizzare queste proprietà per fare in modo che un controllo si estenda su più di una riga o colonna.

#### <a name="to-span-rows-and-columns-with-a-control"></a>Per estendere righe e colonne con un controllo

1. Selezionare il controllo <xref:System.Windows.Forms.Button> nella prima riga e nella prima colonna.

2. Nelle finestre delle **Proprietà** modificare il valore della proprietà `ColumnSpan` su **2**. Si noti che il controllo <xref:System.Windows.Forms.Button> compila la prima colonna e la seconda colonna. Si noti inoltre che è stata aggiunta una riga aggiuntiva per adattarsi a questa modifica.

3. Ripetere il passaggio 2 per la proprietà `RowSpan`.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Inserimento di controlli con doppio clic nella casella degli strumenti

<xref:System.Windows.Forms.TableLayoutPanel> può essere compilato facendo doppio clic sui controlli nella **Casella degli strumenti**.

#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>Per inserire i controlli facendo doppio clic nella Casella degli strumenti

1. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.

2. Fare doppio clic sull'icona del controllo <xref:System.Windows.Forms.Button> nella **Casella degli strumenti**. Si noti che viene visualizzato un nuovo controllo Button nella prima cella del controllo <xref:System.Windows.Forms.TableLayoutPanel>.

3. Fare doppio clic su diversi altri controlli nella **Casella degli strumenti**. Si noti che i nuovi controlli vengono visualizzati in successione nelle celle non occupate del controllo <xref:System.Windows.Forms.TableLayoutPanel>. Si noti inoltre che il controllo <xref:System.Windows.Forms.TableLayoutPanel> si espande in modo da contenere i nuovi controlli se non sono disponibili celle aperte.

## <a name="automatic-handling-of-overflows"></a>Gestione automatica degli overflow

Quando si inseriscono controlli nel controllo <xref:System.Windows.Forms.TableLayoutPanel>, è possibile che vengano esaurite le celle vuote per i nuovi controlli. Il controllo <xref:System.Windows.Forms.TableLayoutPanel> gestisce automaticamente questa situazione aumentando il numero di celle.

#### <a name="to-observe-automatic-handling-of-overflows"></a>Per osservare la gestione automatica degli overflow

1. Se nel controllo <xref:System.Windows.Forms.TableLayoutPanel> sono ancora presenti celle vuote, continuare a inserire nuovi controlli <xref:System.Windows.Forms.Button> finché il controllo <xref:System.Windows.Forms.TableLayoutPanel> non è pieno.

2. Una volta completato il controllo <xref:System.Windows.Forms.TableLayoutPanel>, fare doppio clic sull'icona <xref:System.Windows.Forms.Button> nella **casella degli strumenti** per inserire un altro controllo <xref:System.Windows.Forms.Button>. Si noti che il controllo <xref:System.Windows.Forms.TableLayoutPanel> crea nuove celle per supportare il nuovo controllo. Inserire altri controlli e osservare il comportamento di ridimensionamento.

3. Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.TableLayoutPanel> , <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> , su <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Fare doppio clic sull'icona <xref:System.Windows.Forms.Button> nella **casella degli strumenti** per inserire <xref:System.Windows.Forms.Button> controlli finché il controllo <xref:System.Windows.Forms.TableLayoutPanel> non è pieno. Fare di nuovo clic sull'icona <xref:System.Windows.Forms.Button> nella **casella degli strumenti** . Si noti che viene visualizzato un messaggio di errore dall' **Progettazione Windows Form** che informa che non è possibile creare righe e colonne aggiuntive.

## <a name="inserting-a-control-by-drawing-its-outline"></a>Inserimento di un controllo disegnandone il contorno

È possibile inserire un controllo in <xref:System.Windows.Forms.TableLayoutPanel> e determinarne la dimensione disegnandone il contorno in una cella.

#### <a name="to-insert-a-control-by-drawing-its-outline"></a>Per inserire un controllo disegnandone il contorno

1. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.

2. Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.Button> . Non trascinarla nel form.

3. Spostare il puntatore del mouse sul controllo <xref:System.Windows.Forms.TableLayoutPanel> . Osservare che il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.Button> associata.

4. Fare clic e tenere premuto il pulsante del mouse.

5. Trascinare il puntatore del mouse per disegnare la struttura del controllo <xref:System.Windows.Forms.Button> . Una volta ottenuta la dimensione desiderata, rilasciare il pulsante del mouse. Si noti che il controllo <xref:System.Windows.Forms.Button> viene creato nella cella in cui è stato disegnato il contorno del controllo.

## <a name="multiple-controls-within-cells-are-not-permitted"></a>Non sono consentiti più controlli all'interno di celle

Il controllo <xref:System.Windows.Forms.TableLayoutPanel> può contenere un solo controllo figlio per cella.

#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>Per dimostrare che non sono consentiti più controlli all'interno di celle

- Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel controllo <xref:System.Windows.Forms.TableLayoutPanel> e rilasciarlo in una delle celle occupate. Si noti che il controllo <xref:System.Windows.Forms.TableLayoutPanel> non consente di rilasciare il controllo <xref:System.Windows.Forms.Button> nella cella occupata.

## <a name="swapping-controls"></a>Scambio di controlli

Il controllo <xref:System.Windows.Forms.TableLayoutPanel> consente di scambiare i controlli che occupano due celle diverse.

#### <a name="to-swap-controls"></a>Per scambiare i controlli

- Trascinare uno dei controlli <xref:System.Windows.Forms.Button> da una cella occupata e rilasciarlo su un'altra cella occupata. Si noti che i due controlli vengono spostati da una cella all'altra.

## <a name="next-steps"></a>Passaggi successivi

È possibile ottenere un layout complesso usando i pannelli e i controlli di layout in combinazione. Per approfondire l'argomento, si consiglia di effettuare le seguenti operazioni:

- Provare a ridimensionare uno dei controlli <xref:System.Windows.Forms.Button> a una dimensione più grande e notare l'effetto sul layout.

- Incollare una selezione di più controlli nel controllo <xref:System.Windows.Forms.TableLayoutPanel> e osservare come vengono inseriti i controlli.

- I pannelli layout possono contenere altri pannelli layout. Provare a rilasciare un controllo <xref:System.Windows.Forms.TableLayoutPanel> nel controllo esistente.

- Ancorare il controllo <xref:System.Windows.Forms.TableLayoutPanel> al form padre. Ridimensionare il form e notare l'effetto sul layout.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Procedura dettagliata: creazione di un Windows Form ridimensionabile per l'inserimento di dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [Procedura dettagliata: creazione di un Windows form localizzabile](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [Procedure consigliate per il controllo TableLayoutPanel](best-practices-for-the-tablelayoutpanel-control.md)
- [Panoramica sulla proprietà AutoSize](autosize-property-overview.md)
- [Procedura: Ancorare i controlli in Windows Form](how-to-dock-controls-on-windows-forms.md)
- [Procedura: Agganciare i controlli in Windows Form](how-to-anchor-controls-on-windows-forms.md)
- [Procedura dettagliata: Disposizione di controlli Windows Form con spaziatura, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md)
