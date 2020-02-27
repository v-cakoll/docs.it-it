---
title: 'Procedura dettagliata: inserimento di voci di menu standard in un form'
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
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628774"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="c184a-102">Procedura dettagliata: inserimento di voci di menu standard in un form</span><span class="sxs-lookup"><span data-stu-id="c184a-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="c184a-103">È possibile fornire un menu standard nei form tramite il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="c184a-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="c184a-104">In questa procedura dettagliata viene illustrato come utilizzare un controllo <xref:System.Windows.Forms.MenuStrip> per creare un menu standard.</span><span class="sxs-lookup"><span data-stu-id="c184a-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="c184a-105">Il modulo risponde anche quando un utente seleziona una voce di menu.</span><span class="sxs-lookup"><span data-stu-id="c184a-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="c184a-106">In questa procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="c184a-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="c184a-107">Creazione di un progetto Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c184a-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="c184a-108">Creazione di un menu standard.</span><span class="sxs-lookup"><span data-stu-id="c184a-108">Creating a standard menu.</span></span>

- <span data-ttu-id="c184a-109">Creazione di un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="c184a-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="c184a-110">Gestione della selezione delle voci di menu.</span><span class="sxs-lookup"><span data-stu-id="c184a-110">Handling menu item selection.</span></span>

<span data-ttu-id="c184a-111">Al termine, sarà presente un modulo con un menu standard che visualizza le selezioni delle voci di menu in un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="c184a-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="c184a-112">Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: specificare voci di menu standard in un modulo](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="c184a-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c184a-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c184a-113">Prerequisites</span></span>

<span data-ttu-id="c184a-114">Per completare questa procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c184a-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="c184a-115">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="c184a-115">Create the project</span></span>

1. <span data-ttu-id="c184a-116">In Visual Studio creare un progetto di applicazione Windows denominato **StandardMenuForm** (**file** > **nuovo** > **progetto** > **Visual C#**  o **Visual Basic** > **desktop classico** > **Windows Forms applicazione**).</span><span class="sxs-lookup"><span data-stu-id="c184a-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="c184a-117">Nella Progettazione Windows Form selezionare il modulo.</span><span class="sxs-lookup"><span data-stu-id="c184a-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="c184a-118">Creare un menu standard</span><span class="sxs-lookup"><span data-stu-id="c184a-118">Create a standard menu</span></span>

<span data-ttu-id="c184a-119">Il Progettazione Windows Form può popolare automaticamente un controllo <xref:System.Windows.Forms.MenuStrip> con voci di menu standard.</span><span class="sxs-lookup"><span data-stu-id="c184a-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="c184a-120">Dalla **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.MenuStrip> nel form.</span><span class="sxs-lookup"><span data-stu-id="c184a-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="c184a-121">Fare clic sul glifo delle azioni della finestra di progettazione del controllo <xref:System.Windows.Forms.MenuStrip> (![Small Black Arrow](./media/designer-actions-glyph.gif)) e selezionare **Inserisci elementi standard**.</span><span class="sxs-lookup"><span data-stu-id="c184a-121">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="c184a-122">Il controllo <xref:System.Windows.Forms.MenuStrip> viene popolato con le voci di menu standard.</span><span class="sxs-lookup"><span data-stu-id="c184a-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="c184a-123">Fare clic sulla voce di menu **file** per visualizzare le voci di menu predefinite e le icone corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c184a-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="c184a-124">Creare un controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="c184a-124">Create a StatusStrip control</span></span>

<span data-ttu-id="c184a-125">Usare il controllo <xref:System.Windows.Forms.StatusStrip> per visualizzare lo stato per le applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c184a-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="c184a-126">Nell'esempio corrente, le voci di menu selezionate dall'utente vengono visualizzate in un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="c184a-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="c184a-127">Dalla **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.StatusStrip> nel form.</span><span class="sxs-lookup"><span data-stu-id="c184a-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="c184a-128">Il controllo <xref:System.Windows.Forms.StatusStrip> viene ancorato automaticamente alla fine del form.</span><span class="sxs-lookup"><span data-stu-id="c184a-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="c184a-129">Fare clic sul pulsante a discesa del controllo <xref:System.Windows.Forms.StatusStrip> e selezionare **StatusLabel** per aggiungere un controllo <xref:System.Windows.Forms.ToolStripStatusLabel> al controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="c184a-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="c184a-130">Gestisci selezione elemento</span><span class="sxs-lookup"><span data-stu-id="c184a-130">Handle item selection</span></span>

<span data-ttu-id="c184a-131">Consente di gestire l'evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> per rispondere quando l'utente seleziona una voce di menu.</span><span class="sxs-lookup"><span data-stu-id="c184a-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="c184a-132">Fare clic sulla voce di menu **file** creata nella sezione Creazione di un menu standard.</span><span class="sxs-lookup"><span data-stu-id="c184a-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="c184a-133">Nella finestra **Proprietà** fare clic su **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="c184a-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="c184a-134">Fare doppio clic sull'evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.</span><span class="sxs-lookup"><span data-stu-id="c184a-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="c184a-135">Il Progettazione Windows Form genera un gestore eventi per l'evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.</span><span class="sxs-lookup"><span data-stu-id="c184a-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="c184a-136">Inserire il codice seguente nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="c184a-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="c184a-137">Inserire la definizione del metodo di utilità `UpdateStatus` nel form.</span><span class="sxs-lookup"><span data-stu-id="c184a-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="c184a-138">Checkpoint-testare il modulo</span><span class="sxs-lookup"><span data-stu-id="c184a-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="c184a-139">Premere **F5** per compilare ed eseguire il modulo.</span><span class="sxs-lookup"><span data-stu-id="c184a-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="c184a-140">Fare clic sulla voce di menu **file** per aprire il menu.</span><span class="sxs-lookup"><span data-stu-id="c184a-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="c184a-141">Nel menu **file** fare clic su uno degli elementi per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="c184a-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="c184a-142">Il controllo <xref:System.Windows.Forms.StatusStrip> Visualizza l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="c184a-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c184a-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c184a-143">Next steps</span></span>

<span data-ttu-id="c184a-144">In questa procedura dettagliata è stato creato un modulo con un menu standard.</span><span class="sxs-lookup"><span data-stu-id="c184a-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="c184a-145">È possibile usare la famiglia di controlli <xref:System.Windows.Forms.ToolStrip> per molti altri scopi:</span><span class="sxs-lookup"><span data-stu-id="c184a-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="c184a-146">Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="c184a-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="c184a-147">Per altre informazioni, vedere [Cenni preliminari sui componenti ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c184a-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="c184a-148">Creare un form con interfaccia a documenti multipli (MDI) con i controlli di ancoraggio <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="c184a-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="c184a-149">Per altre informazioni, vedere [procedura dettagliata: creazione di un form MDI con Unione di menu e controlli ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="c184a-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="c184a-150">Dare ai <xref:System.Windows.Forms.ToolStrip> controlli un aspetto professionale.</span><span class="sxs-lookup"><span data-stu-id="c184a-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="c184a-151">Per altre informazioni, vedere [procedura: impostare il renderer ToolStrip per un'applicazione](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="c184a-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c184a-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c184a-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="c184a-153">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="c184a-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
