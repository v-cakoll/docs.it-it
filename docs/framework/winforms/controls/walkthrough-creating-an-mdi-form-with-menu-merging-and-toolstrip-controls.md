---
title: 'Procedura dettagliata: Creazione di un Form MDI con unione di Menu e controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: f4e6bc0faf0dc088d919ee929a7bf320d6e169c4
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664952"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Procedura dettagliata: Creazione di un Form MDI con unione di Menu e controlli ToolStrip
Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu. I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.  
  
 Questa procedura dettagliata illustra come usare <xref:System.Windows.Forms.ToolStripPanel> controlli con un form MDI. Il form supporta anche l'unione dei menu con menu figlio. Nella procedura dettagliata vengono illustrate le attività seguenti:  
  
-   Creazione di un progetto Windows Form.  
  
-   Creazione del menu principale per il form. Il nome effettivo del menu variano.  
  
-   Aggiunta il <xref:System.Windows.Forms.ToolStripPanel> controllare per il **casella degli strumenti**.  
  
-   Creazione di un form figlio.  
  
-   Disposizione <xref:System.Windows.Forms.ToolStripPanel> controlli l'ordine z.  
  
 Al termine, si avrà un form MDI che supporta l'unione di menu e movable <xref:System.Windows.Forms.ToolStrip> controlli.  
  
 Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Creare un Form MDI con unione di Menu e controlli ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Autorizzazioni sufficienti per essere in grado di creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un progetto di applicazione Windows denominato **MDI** (**File** > **nuovo** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).  
  
2.  Nella finestra di progettazione Windows Form, selezionare il form.  
  
3.  Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.Form.IsMdiContainer%2A> a `true`.  
  
## <a name="creating-the-main-menu"></a>Creazione del Menu principale  
 Form padre MDI contiene il menu principale. Nel menu principale contiene una voce **finestra**. Con il **finestra** voce di menu, è possibile creare form figlio. Voci di menu da form figlio vengono unite nel menu principale.  
  
#### <a name="to-create-the-main-menu"></a>Per creare il menu principale  
  
1.  Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.  
  
2.  Aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> per il <xref:System.Windows.Forms.MenuStrip> controllano e denominarlo **finestra**.  
  
3.  Selezionare il controllo <xref:System.Windows.Forms.MenuStrip>.  
  
4.  Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà `ToolStripMenuItem1`.  
  
5.  Aggiungere un elemento secondario per il **finestra** voce di menu e quindi denominare l'elemento secondario **New**.  
  
6.  Nella finestra Proprietà, fare clic su **eventi**.  
  
7.  Fare doppio clic il <xref:System.Windows.Forms.ToolStripItem.Click> evento.  
  
     Finestra di progettazione Windows Form genera un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> evento.  
  
8.  Inserire il codice seguente nel gestore eventi.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a>Aggiunta del controllo ToolStripPanel nella casella degli strumenti  
 Quando si usa <xref:System.Windows.Forms.MenuStrip> controlli con un form MDI, è necessario disporre di <xref:System.Windows.Forms.ToolStripPanel> controllo. È necessario aggiungere il <xref:System.Windows.Forms.ToolStripPanel> controllare per il **della casella degli strumenti** per compilare il form MDI in Progettazione Windows Form.  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a>Per aggiungere il controllo ToolStripPanel nella casella degli strumenti  
  
1.  Aprire il **casella degli strumenti**e quindi fare clic sul **tutti i Windows Form** pressione di tab per visualizzare i controlli Windows Form disponibili.  
  
2.  Per aprire il menu di scelta rapida e scegliere **Scegli elementi**.  
  
3.  Nel **Scegli elementi della casella degli strumenti** finestra di dialogo, scorrere verso il basso il **Name** colonna fino a individuare **ToolStripPanel**.  
  
4.  Selezionare la casella di controllo da **ToolStripPanel**, quindi fare clic su **OK**.  
  
     Il <xref:System.Windows.Forms.ToolStripPanel> controllo viene visualizzato nei **casella degli strumenti**.  
  
## <a name="creating-a-child-form"></a>Creazione di un Form figlio  
 In questa procedura, si definirà una classe di form figlio separata che dispone di una propria <xref:System.Windows.Forms.MenuStrip> controllo. Le voci di menu per questo modulo vengono unite con quelle del form padre.  
  
#### <a name="to-define-a-child-form"></a>Per definire un form figlio  
  
1.  Aggiungere un nuovo form denominato `ChildForm` al progetto.  
  
     Per altre informazioni, vedere [Procedura: Aggiungi Windows Form a un progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).  
  
2.  Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form figlio.  
  
3.  Scegliere il <xref:System.Windows.Forms.MenuStrip> glifo smart tag del controllo (![glifo Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e quindi selezionare **Modifica elementi**.  
  
4.  Nel **Editor della raccolta Items** finestra di dialogo, aggiungere un nuovo <xref:System.Windows.Forms.ToolStripMenuItem> denominato **ChildMenuItem** al menu figlio.  
  
     Per altre informazioni, vedere [Editor di raccolta Items di ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).  
  
## <a name="testing-the-form"></a>Il modulo di test  
  
#### <a name="to-test-your-form"></a>Per testare il form  
  
1.  Premere F5 per compilare ed eseguire il form.  
  
2.  Scegliere il **finestra** voce di menu per aprire il menu di scelta e quindi fare clic su **New**.  
  
     Nell'area client MDI del form viene creato un nuovo form figlio. Menu del form figlio verrà unito nel menu principale.  
  
3.  Chiudere il form figlio.  
  
     Menu del form figlio viene rimosso dal menu principale.  
  
4.  Fare clic su **New** più volte.  
  
     I form figlio vengono automaticamente elencati sotto la **finestra** perché la voce del menu di <xref:System.Windows.Forms.MenuStrip> del controllo <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà viene assegnato.  
  
## <a name="adding-toolstrip-support"></a>Aggiunta del supporto di ToolStrip  
 In questa procedura, si aggiungeranno quattro <xref:System.Windows.Forms.ToolStrip> controlli al form padre MDI. Ciascuna <xref:System.Windows.Forms.ToolStrip> controllo viene aggiunto all'interno di un <xref:System.Windows.Forms.ToolStripPanel> controllo, che viene ancorato al bordo del form.  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a>Per aggiungere controlli ToolStrip al form padre MDI  
  
1.  Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.ToolStripPanel> controllo nel form.  
  
2.  Con il <xref:System.Windows.Forms.ToolStripPanel> controllo è selezionata, fare doppio clic il <xref:System.Windows.Forms.ToolStrip> controllare nel **della casella degli strumenti**.  
  
     Oggetto <xref:System.Windows.Forms.ToolStrip> viene creato nel controllo di <xref:System.Windows.Forms.ToolStripPanel> controllo.  
  
3.  Selezionare il controllo <xref:System.Windows.Forms.ToolStripPanel>.  
  
4.  Nella finestra Proprietà modificare il valore del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Left>.  
  
     Il <xref:System.Windows.Forms.ToolStripPanel> controllano il controllo viene ancorato al lato sinistro del modulo, di sotto del menu principale. L'area client MDI viene adattata per accogliere il <xref:System.Windows.Forms.ToolStripPanel> controllo.  
  
5.  Ripetere i passaggi da 1 a 4.  
  
     Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controllo nella parte superiore del form.  
  
     Il <xref:System.Windows.Forms.ToolStripPanel> controllo è ancorato di sotto del menu principale, ma a destra del primo <xref:System.Windows.Forms.ToolStripPanel> controllo. Questo passaggio dimostra l'importanza dell'ordine z il corretto posizionamento <xref:System.Windows.Forms.ToolStripPanel> controlli.  
  
6.  Ripetere i passaggi da 1 a 4 per due altre <xref:System.Windows.Forms.ToolStripPanel> controlli.  
  
     Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controlli a destra e inferiore del form.  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a>Disposizione dei controlli ToolStripPanel l'ordine Z  
 La posizione di un ancoraggio <xref:System.Windows.Forms.ToolStripPanel> controllo sul form MDI viene determinato in base alla posizione del controllo nell'ordine z. È possibile definire facilmente l'ordine z dei controlli nella finestra Struttura documento.  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a>Per disporre i controlli ToolStripPanel l'ordine Z  
  
1.  Nel **View** menu, fare clic su **Other Windows**e quindi fare clic su **struttura documento**.  
  
     La disposizione delle <xref:System.Windows.Forms.ToolStripPanel> controlli della procedura precedente è conforme allo standard. Questo avviene perché l'ordine z non sia corretto. Utilizzare la finestra Struttura documento per modificare l'ordine z dei controlli.  
  
2.  Nella finestra Struttura documento, selezionare **ToolStripPanel4**.  
  
3.  Fare clic sul pulsante freccia in giù più volte, fino alla **ToolStripPanel4** è nella parte inferiore dell'elenco.  
  
     Il **ToolStripPanel4** controllo è ancorato alla parte inferiore del modulo, di sotto degli altri controlli.  
  
4.  Selezionare **ToolStripPanel2**.  
  
5.  Fare clic sul pulsante freccia in giù una sola volta per posizionare il controllo in terzo luogo nell'elenco.  
  
     Il **ToolStripPanel2** controllo è ancorato alla parte superiore del form, sotto il menu principale e di sopra degli altri controlli.  
  
6.  Selezionare diversi controlli del **struttura documento** finestra e spostarli in posizioni diverse nell'ordine z. Notare l'effetto dello z-order nel posizionamento di controlli ancorati. Usare CTRL-Z o **Undo** nel **modificare** menu annullare le modifiche.  
  
## <a name="checkpoint"></a>Checkpoint  
  
#### <a name="to-test-your-form"></a>Per testare il form  
  
1.  Premere F5 per compilare ed eseguire il form.  
  
2.  Scegliere il triangolo di ridimensionamento di un <xref:System.Windows.Forms.ToolStrip> controllo e trascinare il controllo in diverse posizioni nel form.  
  
     È possibile trascinare un <xref:System.Windows.Forms.ToolStrip> controllo da una <xref:System.Windows.Forms.ToolStripPanel> controllo a altro.  
  
## <a name="next-steps"></a>Passaggi successivi  
 In questa procedura dettagliata, si have creato un form padre MDI con <xref:System.Windows.Forms.ToolStrip> controlli e unione di menu. È possibile usare il <xref:System.Windows.Forms.ToolStrip> della famiglia di controlli per molte altre operazioni:  
  
-   Creare i menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>. Per altre informazioni, vedere [Cenni preliminari sul componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Creato un form con un menu standard popolato automaticamente. Per altre informazioni, vedere [Procedura dettagliata: Inserimento di voci di Menu Standard in un Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Assegnare il <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale. Per altre informazioni, vedere [Procedura: Impostare il ToolStrip Renderer per un'applicazione](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Procedura: Creare form padre MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)
- [Procedura: Creare form figlio MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)
- [Procedura: Inserire un MenuStrip in un Menu a discesa MDI](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [Controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
