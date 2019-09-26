---
title: "Procedura dettagliata: Creazione di un'interfaccia di tipo Esplora risorse con i controlli ListView e TreeView usando la finestra di progettazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: d80f8e3bc729689b274af520bc37fda8417b0407
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "69658578"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>Procedura dettagliata: Creazione di un'interfaccia di tipo Esplora risorse con i controlli ListView e TreeView usando la finestra di progettazione

Uno dei vantaggi di Visual Studio è la possibilità di creare applicazioni Windows Forms professionali in un breve periodo di tempo. Uno scenario comune consiste nel creare un'interfaccia utente con <xref:System.Windows.Forms.ListView> i controlli e <xref:System.Windows.Forms.TreeView> che è simile alla funzionalità Esplora risorse dei sistemi operativi Windows. Esplora risorse Visualizza una struttura gerarchica dei file e delle cartelle nel computer di un utente.

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>Per creare il form contenente un controllo ListView e TreeView

1. Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**.

2. Nella finestra di dialogo **nuovo progetto** eseguire le operazioni seguenti:

    1. Nelle categorie scegliere **Visual Basic** o oggetto **visivo C#** .

    2. Nell'elenco dei modelli scegliere **Windows Forms applicazione**.

3. Fare clic su **OK**. Viene creato un nuovo progetto Windows Forms.

4. Aggiungere un <xref:System.Windows.Forms.SplitContainer> controllo al form e impostare la relativa <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà su <xref:System.Windows.Forms.DockStyle.Fill>.

5. Aggiungere un <xref:System.Windows.Forms.ImageList> oggetto `imageList1` denominato al modulo e usare il finestra proprietà per aggiungere due immagini: un'immagine di cartella e un'immagine del documento, in questo ordine.

6. Aggiungere un <xref:System.Windows.Forms.TreeView> controllo denominato `treeview1` al form e posizionarlo sul lato sinistro del <xref:System.Windows.Forms.SplitContainer> controllo. Nella finestra proprietà per `treeView1` eseguire le operazioni seguenti:

    1. Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.

    2. Impostare la proprietà <xref:System.Windows.Forms.TreeView.ImageList%2A> su `imagelist1.`

7. Aggiungere un <xref:System.Windows.Forms.ListView> controllo denominato `listView1` al form e posizionarlo sul lato destro del <xref:System.Windows.Forms.SplitContainer> controllo. Nella finestra proprietà per `listview1` eseguire le operazioni seguenti:

    1. Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.

    2. Impostare la proprietà <xref:System.Windows.Forms.ListView.View%2A> su <xref:System.Windows.Forms.View.Details>.

    3. Aprire l'editor della raccolta ColumnHeader facendo clic sui puntini![di sospensione (il pulsante con i puntini di sospensione (...](./media/visual-studio-ellipsis-button.png)) nella finestra proprietà <xref:System.Windows.Forms.ListView.Columns%2A> di Visual Studio.) nella proprietà **.** Aggiungere tre colonne e impostare la <xref:System.Windows.Forms.ColumnHeader.Text%2A> relativa proprietà `Name`rispettivamente `Type`su, `Last Modified`e. Fare clic su **OK** per chiudere la finestra di dialogo.

    4. Impostare la proprietà <xref:System.Windows.Forms.ListView.SmallImageList%2A> su `imageList1.`

8. Implementare il codice per popolare l' <xref:System.Windows.Forms.TreeView> oggetto con nodi e sottonodi. Aggiungere questo codice alla `Form1` classe.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. Poiché il codice precedente usa lo spazio dei nomi System.IO, aggiungere l'istruzione using o Import appropriata nella parte superiore del form.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. Chiamare il metodo di impostazione del passaggio precedente nel costruttore del form o <xref:System.Windows.Forms.Form.Load> nel metodo di gestione degli eventi. Aggiungere questo codice al costruttore del form.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. Gestire l' <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento per `treeview1`e implementare il **codice per popolare** `listview1` con il contenuto di un nodo quando si fa clic su un nodo. Aggiungere questo codice alla `Form1` classe.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     Se si usa C#, assicurarsi che l' <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento sia associato al relativo metodo di gestione degli eventi. Aggiungere questo codice al costruttore del form.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a>Verifica dell'applicazione

È ora possibile testare il form per assicurarsi che si comportano come previsto.

#### <a name="to-test-the-form"></a>Per testare il modulo

- Premere F5 per eseguire l'applicazione.

     Verrà visualizzato un form suddiviso contenente un <xref:System.Windows.Forms.TreeView> controllo che visualizza la directory del progetto sul lato sinistro e un <xref:System.Windows.Forms.ListView> controllo sul lato destro con tre colonne. È possibile attraversare il <xref:System.Windows.Forms.TreeView> selezionando i nodi della directory e il <xref:System.Windows.Forms.ListView> viene popolato con il contenuto della directory selezionata.

## <a name="next-steps"></a>Passaggi successivi

Questa applicazione fornisce un esempio di come è possibile usare <xref:System.Windows.Forms.TreeView> insieme i controlli e. <xref:System.Windows.Forms.ListView> Per ulteriori informazioni su questi controlli, vedere gli argomenti seguenti:

- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [Procedura: Aggiungere funzionalità di ricerca a un controllo ListView](how-to-add-search-capabilities-to-a-listview-control.md)

- [Procedura: Collegamento di un menu di scelta rapida a un nodo di TreeView](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [Controllo ListView](listview-control-windows-forms.md)
- [Procedura: Aggiungere e rimuovere nodi con il controllo TreeView Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedura: Aggiunta di colonne al controllo Windows Forms ListView](how-to-add-columns-to-the-windows-forms-listview-control.md)
