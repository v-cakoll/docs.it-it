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
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="889a0-102">Procedura dettagliata: Specifica di voci di menu standard per un modulo</span><span class="sxs-lookup"><span data-stu-id="889a0-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="889a0-103">È possibile fornire un menu standard nei form tramite il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="889a0-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="889a0-104">Questa procedura dettagliata illustra come usare un <xref:System.Windows.Forms.MenuStrip> controllo per creare un menu standard.</span><span class="sxs-lookup"><span data-stu-id="889a0-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="889a0-105">Il modulo risponde anche quando un utente seleziona una voce di menu.</span><span class="sxs-lookup"><span data-stu-id="889a0-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="889a0-106">Nella procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="889a0-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="889a0-107">Creazione di un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="889a0-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="889a0-108">Creazione di un menu standard.</span><span class="sxs-lookup"><span data-stu-id="889a0-108">Creating a standard menu.</span></span>

- <span data-ttu-id="889a0-109">Creazione di un <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="889a0-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="889a0-110">Gestisce la selezione di elementi di menu.</span><span class="sxs-lookup"><span data-stu-id="889a0-110">Handling menu item selection.</span></span>

<span data-ttu-id="889a0-111">Al termine, si avrà un modulo con un menu standard che vengono visualizzate le selezioni delle voci di menu in un <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="889a0-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="889a0-112">Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Specificare voci di Menu Standard in un Form](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="889a0-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="889a0-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="889a0-113">Prerequisites</span></span>

<span data-ttu-id="889a0-114">È necessario Visual Studio per completare questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="889a0-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="889a0-115">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="889a0-115">Create the project</span></span>

1. <span data-ttu-id="889a0-116">In Visual Studio, creare un progetto di applicazione Windows denominato **StandardMenuForm** (**File** > **nuovo** > **progetto**   >  **Visual C#**  oppure **Visual Basic** > **Desktop classico**  >  **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="889a0-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="889a0-117">Nella finestra di progettazione Windows Form, selezionare il form.</span><span class="sxs-lookup"><span data-stu-id="889a0-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="889a0-118">Creare un menu standard</span><span class="sxs-lookup"><span data-stu-id="889a0-118">Create a standard menu</span></span>

<span data-ttu-id="889a0-119">Finestra di progettazione Windows Form è possibile popolare automaticamente un <xref:System.Windows.Forms.MenuStrip> controllo con voci di menu standard.</span><span class="sxs-lookup"><span data-stu-id="889a0-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="889a0-120">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="889a0-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="889a0-121">Scegliere il <xref:System.Windows.Forms.MenuStrip> glifo smart tag del controllo (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e selezionare **Inserisci elementi Standard**.</span><span class="sxs-lookup"><span data-stu-id="889a0-121">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="889a0-122">Il <xref:System.Windows.Forms.MenuStrip> controllo venga popolato con le voci di menu standard.</span><span class="sxs-lookup"><span data-stu-id="889a0-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="889a0-123">Scegliere il **File** voce di menu per visualizzare le relative voci di menu predefinito e le icone corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="889a0-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="889a0-124">Creare un controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="889a0-124">Create a StatusStrip control</span></span>

<span data-ttu-id="889a0-125">Usare il <xref:System.Windows.Forms.StatusStrip> controllo per visualizzare lo stato delle applicazioni Windows Form.</span><span class="sxs-lookup"><span data-stu-id="889a0-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="889a0-126">Nell'esempio corrente vengono visualizzate le voci di menu selezionate dall'utente un <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="889a0-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="889a0-127">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.StatusStrip> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="889a0-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="889a0-128">Il <xref:System.Windows.Forms.StatusStrip> controllo ancorato automaticamente nella parte inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="889a0-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="889a0-129">Fare clic sui <xref:System.Windows.Forms.StatusStrip> del controllo pulsante a discesa e selezionare **StatusLabel** per aggiungere un <xref:System.Windows.Forms.ToolStripStatusLabel> controllo il <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="889a0-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="889a0-130">Gestire la selezione di elementi</span><span class="sxs-lookup"><span data-stu-id="889a0-130">Handle item selection</span></span>

<span data-ttu-id="889a0-131">Gestire il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento a cui rispondere quando l'utente seleziona una voce di menu.</span><span class="sxs-lookup"><span data-stu-id="889a0-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="889a0-132">Scegliere il **File** voce di menu che è stato creato in creazione una sezione di Menu Standard.</span><span class="sxs-lookup"><span data-stu-id="889a0-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="889a0-133">Nella finestra **Proprietà** fare clic su **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="889a0-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="889a0-134">Fare doppio clic il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.</span><span class="sxs-lookup"><span data-stu-id="889a0-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="889a0-135">Finestra di progettazione Windows Form genera un gestore eventi per il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.</span><span class="sxs-lookup"><span data-stu-id="889a0-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="889a0-136">Inserire il codice seguente nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="889a0-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="889a0-137">Inserire il `UpdateStatus` definizione di metodo di utilità nel form.</span><span class="sxs-lookup"><span data-stu-id="889a0-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="889a0-138">Checkpoint-modulo di test</span><span class="sxs-lookup"><span data-stu-id="889a0-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="889a0-139">Premere **F5** per compilare ed eseguire il form.</span><span class="sxs-lookup"><span data-stu-id="889a0-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="889a0-140">Scegliere il **File** voce di menu per aprire il menu di scelta.</span><span class="sxs-lookup"><span data-stu-id="889a0-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="889a0-141">Nel **File** menu, fare clic su uno degli elementi per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="889a0-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="889a0-142">Il <xref:System.Windows.Forms.StatusStrip> controllo Visualizza l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="889a0-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="889a0-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="889a0-143">Next steps</span></span>

<span data-ttu-id="889a0-144">In questa procedura dettagliata, è stato creato un form con un menu standard.</span><span class="sxs-lookup"><span data-stu-id="889a0-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="889a0-145">È possibile usare il <xref:System.Windows.Forms.ToolStrip> della famiglia di controlli per molte altre operazioni:</span><span class="sxs-lookup"><span data-stu-id="889a0-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="889a0-146">Creare i menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="889a0-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="889a0-147">Per altre informazioni, vedere [Cenni preliminari sul componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="889a0-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="889a0-148">Creare un form MDI (interfaccia) mediante l'ancoraggio <xref:System.Windows.Forms.ToolStrip> controlli.</span><span class="sxs-lookup"><span data-stu-id="889a0-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="889a0-149">Per altre informazioni, vedere [Procedura dettagliata: Creazione di un Form MDI con unione di Menu e controlli ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="889a0-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="889a0-150">Assegnare il <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale.</span><span class="sxs-lookup"><span data-stu-id="889a0-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="889a0-151">Per altre informazioni, vedere [Procedura: Impostare il ToolStrip Renderer per un'applicazione](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="889a0-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="889a0-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="889a0-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="889a0-153">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="889a0-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
