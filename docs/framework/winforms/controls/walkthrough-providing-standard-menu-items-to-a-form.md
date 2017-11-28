---
title: 'Procedura dettagliata: inserimento di voci di menu standard in un form'
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
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1eccb033dd07f634f3629fd6f314eaa3df56b422
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Procedura dettagliata: inserimento di voci di menu standard in un form
È possibile fornire un menu standard nei form tramite il controllo <xref:System.Windows.Forms.MenuStrip>.  
  
 Questa procedura dettagliata viene illustrato come utilizzare un <xref:System.Windows.Forms.MenuStrip> controllo per creare un menu standard. Il modulo risponde anche quando un utente seleziona una voce di menu. Nella procedura dettagliata vengono illustrate le attività seguenti:  
  
-   Creazione di un progetto Windows Form.  
  
-   Creazione di un menu standard.  
  
-   Creazione di un <xref:System.Windows.Forms.StatusStrip> controllo.  
  
-   Gestisce la selezione di elementi di menu.  
  
 Al termine, si disporrà di un form con un menu standard che consente di visualizzare voci di menu selezionate in un <xref:System.Windows.Forms.StatusStrip> controllo.  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: fornire le voci di Menu Standard a un Form](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Disporre di autorizzazioni sufficienti creare ed eseguire progetti di applicazione Windows Form nel computer in cui [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] è installato.  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un progetto di applicazione Windows denominato **StandardMenuForm**.  
  
     Per altre informazioni, vedere [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  In Progettazione Windows Form, selezionare il form.  
  
## <a name="creating-a-standard-menu"></a>Creazione di un Menu Standard  
 Progettazione Windows Form è possibile popolare automaticamente un <xref:System.Windows.Forms.MenuStrip> controllo con voci di menu standard.  
  
#### <a name="to-create-a-standard-menu"></a>Per creare un menu standard  
  
1.  Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.  
  
2.  Fare clic su di <xref:System.Windows.Forms.MenuStrip> glifo dello smart tag del controllo (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e selezionare **Inserisci elementi Standard**.  
  
     Il <xref:System.Windows.Forms.MenuStrip> controllo venga popolato con le voci di menu standard.  
  
3.  Fare clic su di **File** voce di menu per visualizzare le relative voci di menu predefinite e icone corrispondenti.  
  
## <a name="creating-a-statusstrip-control"></a>Creazione di un controllo StatusStrip  
 Utilizzare il <xref:System.Windows.Forms.StatusStrip> controllo per visualizzare lo stato delle applicazioni Windows Form. Nell'esempio corrente, le voci di menu selezionate dall'utente vengono visualizzate un <xref:System.Windows.Forms.StatusStrip> controllo.  
  
#### <a name="to-create-a-statusstrip-control"></a>Per creare un controllo StatusStrip  
  
1.  Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.StatusStrip> controllo nel form.  
  
     Il <xref:System.Windows.Forms.StatusStrip> controllo viene ancorato automaticamente nella parte inferiore del form.  
  
2.  Fare clic su di <xref:System.Windows.Forms.StatusStrip> del controllo pulsante di menu a discesa e selezionare **StatusLabel** per aggiungere un <xref:System.Windows.Forms.ToolStripStatusLabel> controllo il <xref:System.Windows.Forms.StatusStrip> controllo.  
  
## <a name="handling-item-selection"></a>Selezione di elementi di gestione  
 Gestire il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento rispondere quando l'utente seleziona una voce di menu.  
  
#### <a name="to-handle-item-selection"></a>Per gestire la selezione di elementi  
  
1.  Fare clic su di **File** voce di menu che è stato creato in creazione una sezione di Menu Standard.  
  
2.  Nel **proprietà** finestra, fare clic su **eventi**.  
  
3.  Fare doppio clic su di <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.  
  
     Progettazione Windows Form genera un gestore eventi per il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.  
  
4.  Inserire il codice seguente nel gestore eventi.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  Inserire il `UpdateStatus` definizione di metodo di utilità nel form.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a>Checkpoint  
  
#### <a name="to-test-your-form"></a>Per verificare il modulo  
  
1.  Premere F5 per compilare ed eseguire il modulo.  
  
2.  Fare clic su di **File** voce di menu per aprire il menu.  
  
3.  Nel **File** menu, fare clic su uno degli elementi per selezionarlo.  
  
     Il <xref:System.Windows.Forms.StatusStrip> controllo Visualizza l'elemento selezionato.  
  
## <a name="next-steps"></a>Passaggi successivi  
 In questa procedura dettagliata, è stato creato un form con un menu standard. È possibile utilizzare il <xref:System.Windows.Forms.ToolStrip> famiglia di controlli per molte altre operazioni:  
  
-   Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>. Per ulteriori informazioni, vedere [Cenni preliminari sul componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Creare un form MDI (interfaccia) con ancoraggio <xref:System.Windows.Forms.ToolStrip> controlli. Per ulteriori informazioni, vedere [procedura dettagliata: creazione di un Form MDI con unione di Menu e controlli ToolStrip](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
-   Assegnare il <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale. Per ulteriori informazioni, vedere [procedura: impostare il ToolStrip Renderer per un'applicazione](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
