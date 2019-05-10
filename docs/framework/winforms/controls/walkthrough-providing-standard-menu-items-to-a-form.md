---
title: 'Procedura dettagliata: Specifica di voci di menu standard per un modulo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ebfacadfee3ea069359a72ea0402751e9e6280d7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211510"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Procedura dettagliata: Specifica di voci di menu standard per un modulo

È possibile fornire un menu standard nei form tramite il controllo <xref:System.Windows.Forms.MenuStrip>.

Questa procedura dettagliata illustra come usare un <xref:System.Windows.Forms.MenuStrip> controllo per creare un menu standard. Il modulo risponde anche quando un utente seleziona una voce di menu. Nella procedura dettagliata vengono illustrate le attività seguenti:

- Creazione di un progetto Windows Form.

- Creazione di un menu standard.

- Creazione di un <xref:System.Windows.Forms.StatusStrip> controllo.

- Gestisce la selezione di elementi di menu.

Al termine, si avrà un modulo con un menu standard che vengono visualizzate le selezioni delle voci di menu in un <xref:System.Windows.Forms.StatusStrip> controllo.

Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Specificare voci di Menu Standard in un Form](how-to-provide-standard-menu-items-to-a-form.md).

## <a name="prerequisites"></a>Prerequisiti

È necessario Visual Studio per completare questa procedura dettagliata.

## <a name="create-the-project"></a>Creare il progetto

1. In Visual Studio, creare un progetto di applicazione Windows denominato **StandardMenuForm** (**File** > **nuovo** > **progetto**   >  **Visual C#**  oppure **Visual Basic** > **Desktop classico**  >  **Windows Forms Application**).

2. Nella finestra di progettazione Windows Form, selezionare il form.

## <a name="create-a-standard-menu"></a>Creare un menu standard

Finestra di progettazione Windows Form è possibile popolare automaticamente un <xref:System.Windows.Forms.MenuStrip> controllo con voci di menu standard.

1. Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.

2. Scegliere il <xref:System.Windows.Forms.MenuStrip> glifo smart tag del controllo (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e selezionare **Inserisci elementi Standard**.

     Il <xref:System.Windows.Forms.MenuStrip> controllo venga popolato con le voci di menu standard.

3. Scegliere il **File** voce di menu per visualizzare le relative voci di menu predefinito e le icone corrispondenti.

## <a name="create-a-statusstrip-control"></a>Creare un controllo StatusStrip

Usare il <xref:System.Windows.Forms.StatusStrip> controllo per visualizzare lo stato delle applicazioni Windows Form. Nell'esempio corrente vengono visualizzate le voci di menu selezionate dall'utente un <xref:System.Windows.Forms.StatusStrip> controllo.

1. Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.StatusStrip> controllo nel form.

     Il <xref:System.Windows.Forms.StatusStrip> controllo ancorato automaticamente nella parte inferiore del form.

2. Fare clic sui <xref:System.Windows.Forms.StatusStrip> del controllo pulsante a discesa e selezionare **StatusLabel** per aggiungere un <xref:System.Windows.Forms.ToolStripStatusLabel> controllo il <xref:System.Windows.Forms.StatusStrip> controllo.

## <a name="handle-item-selection"></a>Gestire la selezione di elementi

Gestire il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento a cui rispondere quando l'utente seleziona una voce di menu.

1. Scegliere il **File** voce di menu che è stato creato in creazione una sezione di Menu Standard.

2. Nella finestra **Proprietà** fare clic su **Eventi**.

3. Fare doppio clic il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.

     Finestra di progettazione Windows Form genera un gestore eventi per il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.

4. Inserire il codice seguente nel gestore eventi.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. Inserire il `UpdateStatus` definizione di metodo di utilità nel form.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a>Checkpoint-modulo di test

1. Premere **F5** per compilare ed eseguire il form.

2. Scegliere il **File** voce di menu per aprire il menu di scelta.

3. Nel **File** menu, fare clic su uno degli elementi per selezionarlo.

     Il <xref:System.Windows.Forms.StatusStrip> controllo Visualizza l'elemento selezionato.

## <a name="next-steps"></a>Passaggi successivi

In questa procedura dettagliata, è stato creato un form con un menu standard. È possibile usare il <xref:System.Windows.Forms.ToolStrip> della famiglia di controlli per molte altre operazioni:

- Creare i menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>. Per altre informazioni, vedere [Cenni preliminari sul componente ContextMenu](contextmenu-component-overview-windows-forms.md).

- Creare un form MDI (interfaccia) mediante l'ancoraggio <xref:System.Windows.Forms.ToolStrip> controlli. Per altre informazioni, vedere [Procedura dettagliata: Creazione di un Form MDI con unione di Menu e controlli ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

- Assegnare il <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale. Per altre informazioni, vedere [Procedura: Impostare il ToolStrip Renderer per un'applicazione](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Controllo MenuStrip](menustrip-control-windows-forms.md)
