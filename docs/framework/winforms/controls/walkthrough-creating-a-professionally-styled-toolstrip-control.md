---
title: 'Procedura dettagliata: creazione di un controllo ToolStrip professionale'
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
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab9adb72a174da25298b6ea104b002914de0cc40
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>Procedura dettagliata: creazione di un controllo ToolStrip professionale
È possibile assegnare l'applicazione <xref:System.Windows.Forms.ToolStrip> controlla l'aspetto professionale e un comportamento, scrivere la propria classe derivata dal <xref:System.Windows.Forms.ToolStripProfessionalRenderer> tipo.  
  
 Questa procedura dettagliata viene illustrato come utilizzare <xref:System.Windows.Forms.ToolStrip> controlli per creare un controllo composito simile a quella di **riquadro di spostamento** fornito da Microsoft® Outlook®. Nella procedura dettagliata vengono illustrate le attività seguenti:  
  
-   Creazione di un progetto libreria di controlli Windows.  
  
-   Progettazione del controllo StackView.  
  
-   Implementa un Renderer personalizzato.  
  
 Al termine, sarà necessario un controllo client personalizzato riutilizzabile con l'aspetto di un controllo di Microsoft Office® XP professional.  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: creare un controllo ToolStrip professionale](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Disporre di autorizzazioni sufficienti creare ed eseguire progetti di applicazione Windows Form nel computer in cui [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] è installato.  
  
## <a name="creating-a-windows-control-library-project"></a>Creazione di un progetto libreria di controlli Windows  
 Il primo passaggio consiste nel creare il progetto libreria di controlli.  
  
#### <a name="to-create-the-control-library-project"></a>Per creare il progetto libreria di controlli  
  
1.  Creare un nuovo progetto libreria di controlli Windows denominato `StackViewLibrary`.  
  
2.  In **Esplora**, eliminare il controllo del progetto predefinita eliminando il file di origine denominato "UserControl1. cs" o "UserControl1. vb", a seconda del linguaggio scelto.  
  
     Per ulteriori informazioni, vedere [NIB: procedura: escludere elementi, eliminazione e Rimuovi](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento il **StackViewLibrary** progetto. Assegnare il nuovo file di origine il nome di base di `StackView`.  
  
## <a name="designing-the-stackview-control"></a>Progettazione del controllo StackView  
 Il `StackView` è un controllo composito con un elemento figlio <xref:System.Windows.Forms.ToolStrip> controllo. Per ulteriori informazioni sui controlli compositi, vedere [varietà di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
#### <a name="to-design-the-stackview-control"></a>Per progettare il controllo StackView  
  
1.  Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.ToolStrip> controllo nell'area di progettazione.  
  
2.  Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.ToolStrip> proprietà del controllo in base alla tabella seguente.  
  
    |Proprietà|Valore|  
    |--------------|-----------|  
    |nome|`stackStrip`|  
    |CanOverflow|`false`|  
    |Dock|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |Tipo di carattere|`Tahoma, 10pt, style=Bold`|  
    |GripStyle.|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |Spaziatura interna|`0, 7, 0, 0`|  
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3.  In Progettazione Windows Form, fare clic su di <xref:System.Windows.Forms.ToolStrip> del controllo **Aggiungi** pulsante e aggiungere un <xref:System.Windows.Forms.ToolStripButton> per il `stackStrip` controllo.  
  
4.  Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.ToolStripButton> proprietà del controllo in base alla tabella seguente.  
  
    |Proprietà|Valore|  
    |--------------|-----------|  
    |nome|`mailStackButton`|  
    |CheckOnClick|true|  
    |CheckState|<xref:System.Windows.Forms.CheckState.Checked>|  
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |ImageAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |ImageTransparentColor|`238, 238, 238`|  
    |Margini|`0, 0, 0, 0`|  
    |Spaziatura interna|`3, 3, 3, 3`|  
    |Testo|**Posta elettronica**|  
    |TextAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5.  Ripetere il passaggio 7 per altri tre <xref:System.Windows.Forms.ToolStripButton> controlli.  
  
     Denominare i controlli `calendarStackButton`, `contactsStackButton`, e `tasksStackButton`. Impostare il valore della <xref:System.Windows.Forms.Control.Text%2A> proprietà **calendario**, **contatti**, e **attività**, rispettivamente.  
  
## <a name="handling-events"></a>Gestione degli eventi  
 Due eventi sono importanti per rendere il `StackView` controllo funzionino correttamente. Gestire il <xref:System.Windows.Forms.UserControl.Load> evento per posizionare correttamente il controllo. Gestire il <xref:System.Windows.Forms.ToolStripItem.Click> evento per ogni <xref:System.Windows.Forms.ToolStripButton> per fornire il `StackView` controllano il comportamento di stato simile al <xref:System.Windows.Forms.RadioButton> controllo.  
  
#### <a name="to-handle-events"></a>Per gestire gli eventi  
  
1.  In Progettazione Windows Form, selezionare il `StackView` controllo.  
  
2.  Nel **proprietà** finestra, fare clic su **eventi**.  
  
3.  Fare doppio clic per generare l'evento di caricamento di `StackView_Load` gestore dell'evento.  
  
4.  Nel gestore di eventi `StackView_Load` copiare e incollare il codice riportato di seguito.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  In Progettazione Windows Form, selezionare il `mailStackButton` controllo.  
  
6.  Nel **proprietà** finestra, fare clic su **eventi**.  
  
7.  Fare doppio clic dell'evento Click.  
  
     Progettazione Windows Form genera il `mailStackButton_Click` gestore dell'evento.  
  
8.  Rinominare il `mailStackButton_Click` gestore `stackButton_Click`.  
  
     Per ulteriori informazioni, vedere [procedura: rinominare un identificatore (Visual Basic)](http://msdn.microsoft.com/library/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).  
  
9. Inserire il codice seguente nel `stackButton_Click` gestore dell'evento.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. In Progettazione Windows Form, selezionare il `calendarStackButton` controllo.  
  
11. Nel **proprietà** finestra, impostare l'evento Click il `stackButton_Click` gestore dell'evento.  
  
12. Ripetere i passaggi 10 e 11 per il `contactsStackButton` e `tasksStackButton` controlli.  
  
## <a name="defining-icons"></a>Definizione delle icone  
 Ogni `StackView` pulsante è associata un'icona. Per comodità, ogni icona è rappresentato come una stringa con codifica Base64, che viene deserializzato prima di un <xref:System.Drawing.Bitmap> viene creato da esso. In un ambiente di produzione, vengono memorizzati i dati di bitmap come una risorsa, e le icone vengono visualizzate nella finestra di progettazione Windows Form. Per ulteriori informazioni, vedere [procedura: aggiungere immagini di sfondo a un Windows Form](http://msdn.microsoft.com/library/7a509ba2-055c-4ae6-b88a-54625c6d9aff).  
  
#### <a name="to-define-icons"></a>Per definire le icone  
  
1.  Nell'Editor di codice, inserire il codice seguente nel `StackView` definizione di classe. Questo codice inizializza le bitmap per il <xref:System.Windows.Forms.ToolStripButton> icone.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  Aggiungere una chiamata al `InitializeImages` metodo il `StackView` costruttore della classe.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a>Implementazione di un Renderer personalizzato  
 È possibile personalizzare la maggior parte degli elementi del `StackView` controllo mediante l'implementazione di una classe che deriva dalla <xref:System.Windows.Forms.ToolStripRenderer> classe. In questa procedura verrà implementata una <xref:System.Windows.Forms.ToolStripProfessionalRenderer> classe che consente di personalizzare il riquadro e disegna sfondi sfumati per il <xref:System.Windows.Forms.ToolStripButton> controlli.  
  
#### <a name="to-implement-a-custom-renderer"></a>Per implementare un renderer personalizzato  
  
1.  Inserire il codice seguente nel `StackView` definizione di controllo.  
  
     Questa è la definizione per il `StackRenderer` classe, che esegue l'override di <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, e <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> metodi per produrre un aspetto personalizzato.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  Nel `StackView` costruttore del controllo, creare una nuova istanza del `StackRenderer` e assegnare questa istanza con il `stackStrip` del controllo <xref:System.Windows.Forms.ToolStrip.Renderer%2A> proprietà.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a>Test del controllo StackView  
 Il `StackView` controllo deriva dalla <xref:System.Windows.Forms.UserControl> classe. Pertanto, è possibile testare il controllo con il **UserControl Test Container**. Per altre informazioni, vedere [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### <a name="to-test-the-stackview-control"></a>Per testare il controllo StackView  
  
1.  Premere F5 per compilare il progetto e avviare il **UserControl Test Container**.  
  
2.  Spostare il puntatore del mouse sui pulsanti del `StackView` controllare e quindi fare clic su un pulsante per visualizzare l'aspetto del relativo stato selezionato.  
  
## <a name="next-steps"></a>Passaggi successivi  
 In questa procedura dettagliata, è stato creato un controllo client personalizzato riutilizzabile con l'aspetto di un controllo di Office XP professional. È possibile utilizzare il <xref:System.Windows.Forms.ToolStrip> famiglia di controlli per molte altre operazioni:  
  
-   Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>. Per ulteriori informazioni, vedere [Cenni preliminari sul componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Creare un form con un menu standard popolato automaticamente. Per ulteriori informazioni, vedere [procedura dettagliata: fornire le voci di Menu Standard a un Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Creare un form MDI (interfaccia) con ancoraggio <xref:System.Windows.Forms.ToolStrip> controlli. Per ulteriori informazioni, vedere [procedura: creare un Form MDI con unione di Menu e controlli ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [Procedura: Specificare voci di menu standard in un form](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
