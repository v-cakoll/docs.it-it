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
ms.openlocfilehash: 8192151aa7cd5eddd99d39adb485e460074fdb99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768589"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>Procedura dettagliata: Creazione di un'interfaccia di tipo Esplora risorse con i controlli ListView e TreeView usando la finestra di progettazione
Uno dei vantaggi di Visual Studio è la possibilità di creare rapidamente applicazioni di Windows Forms dall'aspetto professionale della quantità di tempo. Uno scenario comune consiste nel creare un'interfaccia utente (UI) con <xref:System.Windows.Forms.ListView> e <xref:System.Windows.Forms.TreeView> controlli simile alla funzionalità di Windows Explorer dei sistemi operativi Windows. Windows Explorer visualizza una struttura gerarchica di file e cartelle nel computer dell'utente.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>Per creare il modulo che contiene un controllo ListView e TreeView  
  
1. Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**.  
  
2. Nel **nuovo progetto** dialogo casella, eseguire le operazioni seguenti:  
  
    1. Nelle categorie, scegliere **Visual Basic** oppure **Visual c#**.  
  
    2. Nell'elenco dei modelli, scegliere **Windows Forms Application**.  
  
3. Fare clic su **OK**. Viene creato un nuovo progetto Windows Form.  
  
4. Aggiungere un <xref:System.Windows.Forms.SplitContainer> controllo al form e impostarne relativi <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>.  
  
5. Aggiungere un <xref:System.Windows.Forms.ImageList> denominato `imageList1` al form e utilizzare la finestra delle proprietà per aggiungere due immagini: un'immagine di una cartella e un'immagine di documento, in quest'ordine.  
  
6. Aggiungere un <xref:System.Windows.Forms.TreeView> controllo denominato `treeview1` al form e posizionarla a sinistra del <xref:System.Windows.Forms.SplitContainer> controllo. Nella finestra proprietà per `treeView1` eseguire le operazioni seguenti:  
  
    1. Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
    2. Impostare la proprietà <xref:System.Windows.Forms.TreeView.ImageList%2A> su `imagelist1.`  
  
7. Aggiungere un <xref:System.Windows.Forms.ListView> controllo denominato `listView1` al form e posizionarlo a destra del <xref:System.Windows.Forms.SplitContainer> controllo. Nella finestra proprietà per `listview1` eseguire le operazioni seguenti:  
  
    1. Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
    2. Impostare la proprietà <xref:System.Windows.Forms.ListView.View%2A> su <xref:System.Windows.Forms.View.Details>.  
  
    3. Aprire l'Editor della raccolta ColumnHeader facendo clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) nella <xref:System.Windows.Forms.ListView.Columns%2A> proprietà **.** Aggiungere tre colonne e impostare loro <xref:System.Windows.Forms.ColumnHeader.Text%2A> proprietà `Name`, `Type`, e `Last Modified`, rispettivamente. Fare clic su **OK** per chiudere la finestra di dialogo.  
  
    4. Impostare la proprietà <xref:System.Windows.Forms.ListView.SmallImageList%2A> su `imageList1.`  
  
8. Implementare il codice per popolare il <xref:System.Windows.Forms.TreeView> con nodi principali e secondari. Aggiungere questo codice per il `Form1` classe.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. Poiché il codice precedente Usa lo spazio dei nomi System.IO, aggiungere l'utilizzo appropriato o Importa istruzione nella parte superiore del form.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. Chiamare il metodo di configurazione nel passaggio precedente nel costruttore del form o <xref:System.Windows.Forms.Form.Load> metodo di gestione degli eventi. Aggiungere questo codice al costruttore del form.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. Gestire il <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento `treeview1` **,** e implementare il codice per popolare `listview1` con contenuto di un nodo quando si fa clic su un nodo. Aggiungere questo codice per il `Form1` classe.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     Se si usa c#, assicurarsi di avere il <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento associato al relativo metodo di gestione degli eventi. Aggiungere questo codice al costruttore del form.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.  
  
#### <a name="to-test-the-form"></a>Per testare il form  
  
- Premere F5 per eseguire l'applicazione.  
  
     Verrà visualizzato un form di split contenente un <xref:System.Windows.Forms.TreeView> controllo che visualizza la directory del progetto sul lato sinistro, e un <xref:System.Windows.Forms.ListView> controllo sul lato destro con tre colonne. È possibile attraversare il <xref:System.Windows.Forms.TreeView> selezionando i nodi di directory e il <xref:System.Windows.Forms.ListView> viene popolato con il contenuto della directory selezionata.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione fornisce un esempio di come è possibile usare <xref:System.Windows.Forms.TreeView> e <xref:System.Windows.Forms.ListView> insieme i controlli. Per altre informazioni su questi controlli, vedere gli argomenti seguenti:  
  
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
- [Procedura: Aggiungere le funzionalità di ricerca a un controllo ListView](how-to-add-search-capabilities-to-a-listview-control.md)  
  
- [Procedura: Associare un Menu di scelta rapida a un nodo di TreeView](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [Controllo ListView](listview-control-windows-forms.md)
- [Procedura: Aggiungere e rimuovere nodi con il controllo TreeView di Windows Form](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere colonne al controllo ListView Windows Form](how-to-add-columns-to-the-windows-forms-listview-control.md)
