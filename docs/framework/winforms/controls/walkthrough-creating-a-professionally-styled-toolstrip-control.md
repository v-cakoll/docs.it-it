---
title: 'Procedura dettagliata: Creazione di un controllo ToolStrip professionale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 526cb509d780abdbf3db6e15504616de19daae83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336551"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>Procedura dettagliata: Creazione di un controllo ToolStrip professionale
È possibile assegnare l'applicazione <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale scrivendo una classe personalizzata derivata dal <xref:System.Windows.Forms.ToolStripProfessionalRenderer> tipo.  
  
 Questa procedura dettagliata illustra come usare <xref:System.Windows.Forms.ToolStrip> controlli per creare un controllo composito che è simile al **riquadro di spostamento** fornito da Microsoft® Outlook®. Nella procedura dettagliata vengono illustrate le attività seguenti:  
  
-   Creazione di un progetto libreria di controlli Windows.  
  
-   Progettazione del controllo StackView.  
  
-   Implementazione di un Renderer personalizzato.  
  
 Al termine, sarà necessario un controllo riutilizzabile client personalizzata con l'aspetto di un controllo di Microsoft Office® XP professional.  
  
 Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Creare un controllo ToolStrip professionale](how-to-create-a-professionally-styled-toolstrip-control.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Autorizzazioni sufficienti per essere in grado di creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.  
  
## <a name="creating-a-windows-control-library-project"></a>Creazione di un progetto di libreria di controlli Windows  
 Il primo passaggio consiste nel creare il progetto di libreria di controlli.  
  
#### <a name="to-create-the-control-library-project"></a>Per creare il progetto di libreria di controlli  
  
1. Creare un nuovo progetto di libreria di controlli di Windows denominato `StackViewLibrary`.  
  
2. Nelle **Esplora soluzioni**, eliminare il controllo del progetto predefinita eliminando il file di origine denominato "UserControl1.cs" o "UserControl1", a seconda del linguaggio che preferisci.  
  
     Per altre informazioni, vedere [Procedura: Rimuovere, eliminare ed escludere elementi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).  
  
3. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> di elemento per il **StackViewLibrary** progetto. Assegnare al nuovo file di origine il nome di base `StackView`.  
  
## <a name="designing-the-stackview-control"></a>Progettazione del controllo StackView  
 Il `StackView` è un controllo composito con un elemento figlio <xref:System.Windows.Forms.ToolStrip> controllo. Per altre informazioni sui controlli compositi, vedere [tipi di controlli personalizzati](varieties-of-custom-controls.md).  
  
#### <a name="to-design-the-stackview-control"></a>Per progettare il controllo StackView  
  
1. Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.ToolStrip> controllo all'area di progettazione.  
  
2. Nel **delle proprietà** impostare nella finestra Proprietà la <xref:System.Windows.Forms.ToolStrip> proprietà del controllo in base alla tabella riportata di seguito.  
  
    |Proprietà|Value|  
    |--------------|-----------|  
    |Nome|`stackStrip`|  
    |CanOverflow|`false`|  
    |Dock|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |Carattere|`Tahoma, 10pt, style=Bold`|  
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |Spaziatura interna|`0, 7, 0, 0`|  
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3. Nella finestra di progettazione Windows Form, fare clic sui <xref:System.Windows.Forms.ToolStrip> del controllo **Add** pulsante e aggiungere un <xref:System.Windows.Forms.ToolStripButton> per il `stackStrip` controllo.  
  
4. Nel **delle proprietà** impostare nella finestra Proprietà la <xref:System.Windows.Forms.ToolStripButton> proprietà del controllo in base alla tabella riportata di seguito.  
  
    |Proprietà|Value|  
    |--------------|-----------|  
    |Nome|`mailStackButton`|  
    |CheckOnClick|true|  
    |Oggetto CheckState|<xref:System.Windows.Forms.CheckState.Checked>|  
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |ImageAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |ImageTransparentColor|`238, 238, 238`|  
    |Margini|`0, 0, 0, 0`|  
    |Spaziatura interna|`3, 3, 3, 3`|  
    |Testo|**Posta elettronica**|  
    |TextAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5. Ripetere il passaggio 7 per altri tre <xref:System.Windows.Forms.ToolStripButton> controlli.  
  
     Denominare i controlli `calendarStackButton`, `contactsStackButton`, e `tasksStackButton`. Impostare il valore della <xref:System.Windows.Forms.Control.Text%2A> proprietà **calendario**, **contatti**, e **attività**, rispettivamente.  
  
## <a name="handling-events"></a>Gestione degli eventi  
 Due eventi sono importanti per rendere il `StackView` controllo funzionare correttamente. Gestire il <xref:System.Windows.Forms.UserControl.Load> posizionare correttamente il controllo dell'evento. Gestire il <xref:System.Windows.Forms.ToolStripItem.Click> evento per ogni <xref:System.Windows.Forms.ToolStripButton> per concedere il `StackView` controllano il comportamento di stato simile al <xref:System.Windows.Forms.RadioButton> controllo.  
  
#### <a name="to-handle-events"></a>Per gestire gli eventi  
  
1. Nella finestra di progettazione Windows Form, selezionare il `StackView` controllo.  
  
2. Nella finestra **Proprietà** fare clic su **Eventi**.  
  
3. Fare doppio clic per generare l'evento di caricamento di `StackView_Load` gestore dell'evento.  
  
4. Nel gestore di eventi `StackView_Load` copiare e incollare il codice riportato di seguito.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5. Nella finestra di progettazione Windows Form, selezionare il `mailStackButton` controllo.  
  
6. Nella finestra **Proprietà** fare clic su **Eventi**.  
  
7. Fare doppio clic dell'evento Click.  
  
     Finestra di progettazione Windows Form genera il `mailStackButton_Click` gestore dell'evento.  
  
8. Rinominare il `mailStackButton_Click` gestore dell'evento a `stackButton_Click`.  
  
     Per altre informazioni, vedere [rinominare un simbolo di codice e refactoring](/visualstudio/ide/reference/rename).  
  
9. Inserire il codice seguente nel `stackButton_Click` gestore dell'evento.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. Nella finestra di progettazione Windows Form, selezionare il `calendarStackButton` controllo.  
  
11. Nel **delle proprietà** finestra, impostare l'evento Click il `stackButton_Click` gestore dell'evento.  
  
12. Ripetere i passaggi 10 e 11 per il `contactsStackButton` e `tasksStackButton` controlli.  
  
## <a name="defining-icons"></a>Definizione delle icone  
 Ogni `StackView` pulsante è associata un'icona. Per praticità, ogni icona è rappresentato come stringa con codifica Base64, che viene deserializzato prima un <xref:System.Drawing.Bitmap> viene creato da quest'ultimo. In un ambiente di produzione, si archiviano i dati di bitmap come una risorsa e le icone vengono visualizzate nella finestra di progettazione Windows Form. Per altre informazioni, vedere [Procedura: Aggiungere le immagini di sfondo a un Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).  
  
#### <a name="to-define-icons"></a>Per definire le icone  
  
1. Nell'Editor di codice, inserire il codice seguente nel `StackView` definizione di classe. Questo codice inizializza le bitmap di <xref:System.Windows.Forms.ToolStripButton> icone.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2. Aggiungere una chiamata ai `InitializeImages` nel metodo il `StackView` costruttore della classe.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a>Implementazione di un Renderer personalizzato  
 È possibile personalizzare la maggior parte degli elementi del `StackView` controllare l'implementazione di una classe che deriva dal <xref:System.Windows.Forms.ToolStripRenderer> classe. In questa procedura, si implementerà un <xref:System.Windows.Forms.ToolStripProfessionalRenderer> classe che consente di personalizzare il riquadro e disegna gli sfondi sfumatura per il <xref:System.Windows.Forms.ToolStripButton> controlli.  
  
#### <a name="to-implement-a-custom-renderer"></a>Per implementare un renderer personalizzato  
  
1. Inserire il codice seguente nel `StackView` controllare la definizione.  
  
     Si tratta della definizione per il `StackRenderer` classe, che esegue l'override di <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, e <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> metodi per produrre un aspetto personalizzato.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2. Nel `StackView` costruttore del controllo, creare una nuova istanza della `StackRenderer` classe e assegnare questa istanza con la `stackStrip` del controllo <xref:System.Windows.Forms.ToolStrip.Renderer%2A> proprietà.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a>Test del controllo StackView  
 Il `StackView` controllo deriva dal <xref:System.Windows.Forms.UserControl> classe. Pertanto, è possibile testare il controllo con il **UserControl Test Container**. Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### <a name="to-test-the-stackview-control"></a>Per testare il controllo StackView  
  
1. Premere F5 per compilare il progetto e avviare il **UserControl Test Container**.  
  
2. Spostare il puntatore del mouse sui pulsanti del `StackView` controllare e quindi fare clic su un pulsante per visualizzare l'aspetto del relativo stato selezionato.  
  
## <a name="next-steps"></a>Passaggi successivi  
 In questa procedura dettagliata, è stato creato un controllo riutilizzabile client personalizzata con l'aspetto di un controllo di Office XP professional. È possibile usare il <xref:System.Windows.Forms.ToolStrip> della famiglia di controlli per molte altre operazioni:  
  
-   Creare i menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>. Per altre informazioni, vedere [Cenni preliminari sul componente ContextMenu](contextmenu-component-overview-windows-forms.md).  
  
-   Creare un form con un menu standard popolato automaticamente. Per altre informazioni, vedere [Procedura dettagliata: Inserimento di voci di Menu Standard in un Form](walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Creare un form MDI (interfaccia) mediante l'ancoraggio <xref:System.Windows.Forms.ToolStrip> controlli. Per altre informazioni, vedere [Procedura: Creare un Form MDI con unione di Menu e controlli ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Controllo ToolStrip](toolstrip-control-windows-forms.md)
- [Procedura: Specificare voci di Menu Standard in un Form](how-to-provide-standard-menu-items-to-a-form.md)
