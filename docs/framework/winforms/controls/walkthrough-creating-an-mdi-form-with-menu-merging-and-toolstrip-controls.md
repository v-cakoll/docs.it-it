---
title: 'Procedura dettagliata: creazione di un form MDI con unione di menu e controlli ToolStrip'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b170c3e3311dbbfb070a66107bd4f22407647bae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Procedura dettagliata: creazione di un form MDI con unione di menu e controlli ToolStrip
Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu. I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.  
  
 Questa procedura dettagliata viene illustrato come utilizzare <xref:System.Windows.Forms.ToolStripPanel> controlli con un form MDI. Il form supporta anche l'unione dei menu con menu figlio. Nella procedura dettagliata vengono illustrate le attività seguenti:  
  
-   Creazione di un progetto Windows Form.  
  
-   Creazione del menu principale per il modulo. Il nome effettivo del menu variano.  
  
-   Aggiunta di <xref:System.Windows.Forms.ToolStripPanel> controllo il **della casella degli strumenti**.  
  
-   Creazione di un form figlio.  
  
-   Disposizione <xref:System.Windows.Forms.ToolStripPanel> controlli in base all'ordine z.  
  
 Al termine, sarà necessario un form MDI che supporta l'unione di menu e mobili <xref:System.Windows.Forms.ToolStrip> controlli.  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: creare un Form MDI con unione di Menu e controlli ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Disporre di autorizzazioni sufficienti creare ed eseguire progetti di applicazione Windows Form nel computer in cui [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] è installato.  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un progetto applicazione Windows denominato **MDI**.  
  
     Per altre informazioni, vedere [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  In Progettazione Windows Form, selezionare il form.  
  
3.  Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.Form.IsMdiContainer%2A> a `true`.  
  
## <a name="creating-the-main-menu"></a>Creazione del Menu principale  
 Form padre MDI contiene il menu principale. Nel menu principale contiene una voce **finestra**. Con il **finestra** voce di menu, è possibile creare form figlio. Voci di menu da form figlio vengono unite nel menu principale.  
  
#### <a name="to-create-the-main-menu"></a>Per creare menu principale  
  
1.  Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.  
  
2.  Aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> per il <xref:System.Windows.Forms.MenuStrip> controllare e denominarlo **finestra**.  
  
3.  Selezionare il controllo <xref:System.Windows.Forms.MenuStrip>.  
  
4.  Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà `ToolStripMenuItem1`.  
  
5.  Aggiungere un elemento secondario per il **finestra** voce di menu e quindi nome dell'elemento secondario **New**.  
  
6.  Nella finestra Proprietà fare clic su **eventi**.  
  
7.  Fare doppio clic su di <xref:System.Windows.Forms.ToolStripItem.Click> evento.  
  
     Progettazione Windows Form genera un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> evento.  
  
8.  Inserire il codice seguente nel gestore eventi.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a>Aggiunta del controllo ToolStripPanel alla casella degli strumenti  
 Quando si utilizza <xref:System.Windows.Forms.MenuStrip> controlli con un form MDI è necessario disporre di <xref:System.Windows.Forms.ToolStripPanel> controllo. È necessario aggiungere il <xref:System.Windows.Forms.ToolStripPanel> controllo il **della casella degli strumenti** per compilare il form MDI in Progettazione Windows Form.  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a>Per aggiungere il controllo ToolStripPanel alla casella degli strumenti  
  
1.  Aprire il **della casella degli strumenti**e quindi fare clic su di **tutti i Windows Form** scheda per visualizzare i controlli Windows Form disponibili.  
  
2.  Per aprire il menu di scelta rapida e scegliere **Scegli elementi**.  
  
3.  Nel **Scegli elementi della casella degli strumenti** la finestra di dialogo, scorrere verso il basso il **nome** colonna fino a individuare **ToolStripPanel**.  
  
4.  Selezionare la casella di controllo da **ToolStripPanel**, quindi fare clic su **OK**.  
  
     Il <xref:System.Windows.Forms.ToolStripPanel> verrà visualizzato un controllo di **della casella degli strumenti**.  
  
## <a name="creating-a-child-form"></a>Creazione di un Form figlio  
 In questa procedura, definire una classe di form figlio separata che dispone di una propria <xref:System.Windows.Forms.MenuStrip> controllo. Le voci di menu per questo form vengono unite con quelle del form padre.  
  
#### <a name="to-define-a-child-form"></a>Per definire un form figlio  
  
1.  Aggiungere un nuovo form denominato `ChildForm` al progetto.  
  
     Per ulteriori informazioni, vedere [procedura: aggiungere Windows Form a un progetto](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
2.  Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form figlio.  
  
3.  Fare clic sul <xref:System.Windows.Forms.MenuStrip> glifo dello smart tag del controllo (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), quindi selezionare **Modifica elementi**.  
  
4.  Nel **Editor della raccolta Items** finestra di dialogo, aggiungere un nuovo <xref:System.Windows.Forms.ToolStripMenuItem> denominato **ChildMenuItem** al menu figlio.  
  
     Per ulteriori informazioni, vedere [Editor raccolta Items di ToolStrip](http://msdn.microsoft.com/en-us/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).  
  
## <a name="testing-the-form"></a>Il modulo di test  
  
#### <a name="to-test-your-form"></a>Per verificare il modulo  
  
1.  Premere F5 per compilare ed eseguire il modulo.  
  
2.  Fare clic su di **finestra** voce di menu per aprire il menu e quindi fare clic su **New**.  
  
     Nell'area di client MDI del form, viene creato un nuovo form figlio. Menu del form figlio verrà unito nel menu principale.  
  
3.  Chiudere il form figlio.  
  
     Menu del form figlio viene rimosso dal menu principale.  
  
4.  Fare clic su **New** più volte.  
  
     I form figlio automaticamente sono elencati sotto la W**finestra** perché la voce del menu di <xref:System.Windows.Forms.MenuStrip> del controllo <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà viene assegnato.  
  
## <a name="adding-toolstrip-support"></a>Aggiunta del supporto di ToolStrip  
 In questa procedura, si aggiungeranno quattro <xref:System.Windows.Forms.ToolStrip> controlli al form padre MDI. Ogni <xref:System.Windows.Forms.ToolStrip> controllo viene aggiunto all'interno di un <xref:System.Windows.Forms.ToolStripPanel> controllo viene ancorato al bordo del form.  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a>Per aggiungere controlli ToolStrip al form padre MDI  
  
1.  Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.ToolStripPanel> controllo nel form.  
  
2.  Con il <xref:System.Windows.Forms.ToolStripPanel> controllo selezionato, fare doppio clic sul <xref:System.Windows.Forms.ToolStrip> controllo il **della casella degli strumenti**.  
  
     Oggetto <xref:System.Windows.Forms.ToolStrip> controllo viene creato nel <xref:System.Windows.Forms.ToolStripPanel> controllo.  
  
3.  Selezionare il controllo <xref:System.Windows.Forms.ToolStripPanel>.  
  
4.  Nella finestra Proprietà modificare il valore del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Left>.  
  
     Il <xref:System.Windows.Forms.ToolStripPanel> controllare il controllo viene ancorato al lato sinistro del form, di sotto del menu principale. L'area client MDI viene ridimensionato il <xref:System.Windows.Forms.ToolStripPanel> controllo.  
  
5.  Ripetere i passaggi da 1 a 4.  
  
     Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controllo nella parte superiore del form.  
  
     Il <xref:System.Windows.Forms.ToolStripPanel> controllo viene ancorato di sotto del menu principale, ma a destra del primo <xref:System.Windows.Forms.ToolStripPanel> controllo. Questo passaggio viene illustrata l'importanza dell'ordine z per il corretto posizionamento <xref:System.Windows.Forms.ToolStripPanel> controlli.  
  
6.  Ripetere i passaggi da 1 a 4 per altre due <xref:System.Windows.Forms.ToolStripPanel> controlli.  
  
     Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controlli a destra e inferiore del form.  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a>Disposizione dei controlli ToolStripPanel dall'ordine Z  
 La posizione di un ancorato <xref:System.Windows.Forms.ToolStripPanel> controllo sul form MDI è determinato dalla posizione del controllo nell'ordine z. È possibile disporre facilmente l'ordine z dei controlli nella finestra Struttura documento.  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a>Per disporre i controlli ToolStripPanel dall'ordine Z  
  
1.  Nel **vista** menu, fare clic su **altre finestre**, quindi fare clic su **struttura documento**.  
  
     La disposizione del <xref:System.Windows.Forms.ToolStripPanel> controlli della procedura precedente è conforme allo standard. In questo modo l'ordine z non è corretto. Utilizzare la finestra Struttura documento per modificare l'ordine z dei controlli.  
  
2.  Nella finestra Struttura documento selezionare **ToolStripPanel4**.  
  
3.  Fare clic sul pulsante freccia in giù più volte, fino a **ToolStripPanel4** nella parte inferiore dell'elenco.  
  
     Il **ToolStripPanel4** controllo è ancorato alla parte inferiore del form, di sotto degli altri controlli.  
  
4.  Selezionare **ToolStripPanel2**.  
  
5.  Fare clic sul pulsante freccia in giù una volta per posizionare il controllo terzo nell'elenco.  
  
     Il **ToolStripPanel2** controllo viene ancorato alla parte superiore del modulo, di sotto del menu principale e di sopra degli altri controlli.  
  
6.  Selezionare vari controlli di **struttura documento** finestra e spostarli in posizioni diverse nell'ordine z. Notare l'effetto dello z-order sul posizionamento dei controlli ancorati. Utilizzare CTRL-Z o **Annulla** sul **modifica** menu per annullare le modifiche.  
  
## <a name="checkpoint"></a>Checkpoint  
  
#### <a name="to-test-your-form"></a>Per verificare il modulo  
  
1.  Premere F5 per compilare ed eseguire il modulo.  
  
2.  Fare clic su riquadro di ridimensionamento di un <xref:System.Windows.Forms.ToolStrip> controllo e trascinare il controllo in diverse posizioni nel form.  
  
     È possibile trascinare un <xref:System.Windows.Forms.ToolStrip> controllo da uno <xref:System.Windows.Forms.ToolStripPanel> controllo a un altro.  
  
## <a name="next-steps"></a>Passaggi successivi  
 In questa procedura dettagliata creato un form padre MDI con <xref:System.Windows.Forms.ToolStrip> unione dei menu e controlli. È possibile utilizzare il <xref:System.Windows.Forms.ToolStrip> famiglia di controlli per molte altre operazioni:  
  
-   Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>. Per ulteriori informazioni, vedere [Cenni preliminari sul componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Creare un form con un menu standard popolato automaticamente. Per ulteriori informazioni, vedere [procedura dettagliata: fornire le voci di Menu Standard a un Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Assegnare il <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale. Per ulteriori informazioni, vedere [procedura: impostare il ToolStrip Renderer per un'applicazione](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Procedura: Creare form padre MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Procedura: Creare form figlio MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Procedura: Inserire un MenuStrip in un menu a discesa MDI](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [Controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
