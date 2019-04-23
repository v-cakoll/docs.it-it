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
ms.openlocfilehash: b4957a3f2efcb31594806a188e3d3bb10c2dac09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296394"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="16666-102">Procedura dettagliata: Specifica di voci di menu standard per un modulo</span><span class="sxs-lookup"><span data-stu-id="16666-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="16666-103">È possibile fornire un menu standard nei form tramite il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="16666-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="16666-104">Questa procedura dettagliata illustra come usare un <xref:System.Windows.Forms.MenuStrip> controllo per creare un menu standard.</span><span class="sxs-lookup"><span data-stu-id="16666-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="16666-105">Il modulo risponde anche quando un utente seleziona una voce di menu.</span><span class="sxs-lookup"><span data-stu-id="16666-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="16666-106">Nella procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="16666-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="16666-107">Creazione di un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="16666-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="16666-108">Creazione di un menu standard.</span><span class="sxs-lookup"><span data-stu-id="16666-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="16666-109">Creazione di un <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="16666-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="16666-110">Gestisce la selezione di elementi di menu.</span><span class="sxs-lookup"><span data-stu-id="16666-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="16666-111">Al termine, si avrà un modulo con un menu standard che vengono visualizzate le selezioni delle voci di menu in un <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="16666-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="16666-112">Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Specificare voci di Menu Standard in un Form](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="16666-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16666-113">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="16666-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="16666-114">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="16666-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="16666-115">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="16666-115">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="16666-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="16666-116">Prerequisites</span></span>  
 <span data-ttu-id="16666-117">Per completare questa procedura dettagliata, è necessario:</span><span class="sxs-lookup"><span data-stu-id="16666-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="16666-118">Autorizzazioni sufficienti per essere in grado di creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="16666-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="16666-119">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="16666-119">Creating the Project</span></span>  
 <span data-ttu-id="16666-120">Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.</span><span class="sxs-lookup"><span data-stu-id="16666-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="16666-121">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="16666-121">To create the project</span></span>  
  
1. <span data-ttu-id="16666-122">Creare un progetto di applicazione Windows denominato **StandardMenuForm** (**File** > **nuovo** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Form Applicazione**).</span><span class="sxs-lookup"><span data-stu-id="16666-122">Create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="16666-123">Nella finestra di progettazione Windows Form, selezionare il form.</span><span class="sxs-lookup"><span data-stu-id="16666-123">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="16666-124">Creazione di un Menu Standard</span><span class="sxs-lookup"><span data-stu-id="16666-124">Creating a Standard Menu</span></span>  
 <span data-ttu-id="16666-125">Finestra di progettazione Windows Form è possibile popolare automaticamente un <xref:System.Windows.Forms.MenuStrip> controllo con voci di menu standard.</span><span class="sxs-lookup"><span data-stu-id="16666-125">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="16666-126">Per creare un menu standard</span><span class="sxs-lookup"><span data-stu-id="16666-126">To create a standard menu</span></span>  
  
1. <span data-ttu-id="16666-127">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="16666-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2. <span data-ttu-id="16666-128">Scegliere il <xref:System.Windows.Forms.MenuStrip> glifo smart tag del controllo (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e selezionare **Inserisci elementi Standard**.</span><span class="sxs-lookup"><span data-stu-id="16666-128">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="16666-129">Il <xref:System.Windows.Forms.MenuStrip> controllo venga popolato con le voci di menu standard.</span><span class="sxs-lookup"><span data-stu-id="16666-129">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3. <span data-ttu-id="16666-130">Scegliere il **File** voce di menu per visualizzare le relative voci di menu predefinito e le icone corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="16666-130">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="16666-131">Creazione di un controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="16666-131">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="16666-132">Usare il <xref:System.Windows.Forms.StatusStrip> controllo per visualizzare lo stato delle applicazioni Windows Form.</span><span class="sxs-lookup"><span data-stu-id="16666-132">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="16666-133">Nell'esempio corrente vengono visualizzate le voci di menu selezionate dall'utente un <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="16666-133">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="16666-134">Per creare un controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="16666-134">To create a StatusStrip control</span></span>  
  
1. <span data-ttu-id="16666-135">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.StatusStrip> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="16666-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="16666-136">Il <xref:System.Windows.Forms.StatusStrip> controllo ancorato automaticamente nella parte inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="16666-136">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2. <span data-ttu-id="16666-137">Fare clic sui <xref:System.Windows.Forms.StatusStrip> del controllo pulsante a discesa e selezionare **StatusLabel** per aggiungere un <xref:System.Windows.Forms.ToolStripStatusLabel> controllo il <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="16666-137">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="16666-138">Selezione di elementi di gestione</span><span class="sxs-lookup"><span data-stu-id="16666-138">Handling Item Selection</span></span>  
 <span data-ttu-id="16666-139">Gestire il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento a cui rispondere quando l'utente seleziona una voce di menu.</span><span class="sxs-lookup"><span data-stu-id="16666-139">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="16666-140">Per gestire la selezione di elementi</span><span class="sxs-lookup"><span data-stu-id="16666-140">To handle item selection</span></span>  
  
1. <span data-ttu-id="16666-141">Scegliere il **File** voce di menu che è stato creato in creazione una sezione di Menu Standard.</span><span class="sxs-lookup"><span data-stu-id="16666-141">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2. <span data-ttu-id="16666-142">Nella finestra **Proprietà** fare clic su **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="16666-142">In the **Properties** window, click **Events**.</span></span>  
  
3. <span data-ttu-id="16666-143">Fare doppio clic il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.</span><span class="sxs-lookup"><span data-stu-id="16666-143">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="16666-144">Finestra di progettazione Windows Form genera un gestore eventi per il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.</span><span class="sxs-lookup"><span data-stu-id="16666-144">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4. <span data-ttu-id="16666-145">Inserire il codice seguente nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="16666-145">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5. <span data-ttu-id="16666-146">Inserire il `UpdateStatus` definizione di metodo di utilità nel form.</span><span class="sxs-lookup"><span data-stu-id="16666-146">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="16666-147">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="16666-147">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="16666-148">Per testare il form</span><span class="sxs-lookup"><span data-stu-id="16666-148">To test your form</span></span>  
  
1. <span data-ttu-id="16666-149">Premere F5 per compilare ed eseguire il form.</span><span class="sxs-lookup"><span data-stu-id="16666-149">Press F5 to compile and run your form.</span></span>  
  
2. <span data-ttu-id="16666-150">Scegliere il **File** voce di menu per aprire il menu di scelta.</span><span class="sxs-lookup"><span data-stu-id="16666-150">Click the **File** menu item to open the menu.</span></span>  
  
3. <span data-ttu-id="16666-151">Nel **File** menu, fare clic su uno degli elementi per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="16666-151">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="16666-152">Il <xref:System.Windows.Forms.StatusStrip> controllo Visualizza l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="16666-152">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="16666-153">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="16666-153">Next Steps</span></span>  
 <span data-ttu-id="16666-154">In questa procedura dettagliata, è stato creato un form con un menu standard.</span><span class="sxs-lookup"><span data-stu-id="16666-154">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="16666-155">È possibile usare il <xref:System.Windows.Forms.ToolStrip> della famiglia di controlli per molte altre operazioni:</span><span class="sxs-lookup"><span data-stu-id="16666-155">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="16666-156">Creare i menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="16666-156">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="16666-157">Per altre informazioni, vedere [Cenni preliminari sul componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="16666-157">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="16666-158">Creare un form MDI (interfaccia) mediante l'ancoraggio <xref:System.Windows.Forms.ToolStrip> controlli.</span><span class="sxs-lookup"><span data-stu-id="16666-158">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="16666-159">Per altre informazioni, vedere [Procedura dettagliata: Creazione di un Form MDI con unione di Menu e controlli ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="16666-159">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="16666-160">Assegnare il <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale.</span><span class="sxs-lookup"><span data-stu-id="16666-160">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="16666-161">Per altre informazioni, vedere [Procedura: Impostare il ToolStrip Renderer per un'applicazione](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="16666-161">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16666-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16666-162">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="16666-163">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="16666-163">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
