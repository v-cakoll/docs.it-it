---
title: 'Procedura dettagliata: creazione di un form MDI con unione di menu e controlli ToolStrip'
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
ms.openlocfilehash: e0343b98cb71521b35418e70550a93e0bfe20fa8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628787"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="f9e46-102">Procedura dettagliata: creazione di un form MDI con unione di menu e controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="f9e46-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="f9e46-103">Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu.</span><span class="sxs-lookup"><span data-stu-id="f9e46-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="f9e46-104">I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="f9e46-105">In questa procedura dettagliata viene illustrato come utilizzare i controlli di <xref:System.Windows.Forms.ToolStripPanel> con un form MDI.</span><span class="sxs-lookup"><span data-stu-id="f9e46-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="f9e46-106">Il form supporta anche l'unione dei menu con menu figlio.</span><span class="sxs-lookup"><span data-stu-id="f9e46-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="f9e46-107">In questa procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9e46-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="f9e46-108">Creazione di un progetto Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f9e46-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="f9e46-109">Creazione del menu principale per il form.</span><span class="sxs-lookup"><span data-stu-id="f9e46-109">Creating the main menu for your form.</span></span> <span data-ttu-id="f9e46-110">Il nome effettivo del menu varierà.</span><span class="sxs-lookup"><span data-stu-id="f9e46-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="f9e46-111">Aggiunta del controllo <xref:System.Windows.Forms.ToolStripPanel> alla **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="f9e46-112">Creazione di un form figlio.</span><span class="sxs-lookup"><span data-stu-id="f9e46-112">Creating a child form.</span></span>

- <span data-ttu-id="f9e46-113">Disposizione dei controlli <xref:System.Windows.Forms.ToolStripPanel> in base all'ordine z.</span><span class="sxs-lookup"><span data-stu-id="f9e46-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="f9e46-114">Al termine, si disporrà di un form MDI che supporta l'Unione di menu e i controlli mobili <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="f9e46-115">Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: creare un form MDI con Unione di menu e controlli ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f9e46-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f9e46-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f9e46-116">Prerequisites</span></span>

<span data-ttu-id="f9e46-117">Per completare questa procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f9e46-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="f9e46-118">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="f9e46-118">Create the project</span></span>

1. <span data-ttu-id="f9e46-119">In Visual Studio creare un progetto di applicazione Windows denominato **MDIForm** (**file** > **nuovo** > **progetto** > **Visual C#**  o **Visual Basic** > **desktop classico** > **Windows Forms applicazione**).</span><span class="sxs-lookup"><span data-stu-id="f9e46-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="f9e46-120">Nella Progettazione Windows Form selezionare il modulo.</span><span class="sxs-lookup"><span data-stu-id="f9e46-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="f9e46-121">Nella Finestra Proprietà impostare il valore della <xref:System.Windows.Forms.Form.IsMdiContainer%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="f9e46-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="f9e46-122">Creare il menu principale</span><span class="sxs-lookup"><span data-stu-id="f9e46-122">Create the main menu</span></span>

<span data-ttu-id="f9e46-123">Il form padre MDI contiene il menu principale.</span><span class="sxs-lookup"><span data-stu-id="f9e46-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="f9e46-124">Nel menu principale è presente una voce di menu denominata **Window**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="f9e46-125">Con la voce di menu **finestra** è possibile creare form figlio.</span><span class="sxs-lookup"><span data-stu-id="f9e46-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="f9e46-126">Le voci di menu dei form figlio vengono unite nel menu principale.</span><span class="sxs-lookup"><span data-stu-id="f9e46-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="f9e46-127">Dalla **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.MenuStrip> nel form.</span><span class="sxs-lookup"><span data-stu-id="f9e46-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="f9e46-128">Aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> al controllo <xref:System.Windows.Forms.MenuStrip> e denominarlo **Window**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="f9e46-129">Selezionare il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="f9e46-130">Nella Finestra Proprietà impostare il valore della proprietà <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> su `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="f9e46-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="f9e46-131">Aggiungere un elemento secondario alla voce di menu **finestra** , quindi denominare il **nuovo**elemento secondario.</span><span class="sxs-lookup"><span data-stu-id="f9e46-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="f9e46-132">Nella Finestra Proprietà fare clic su **eventi**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="f9e46-133">Fare doppio clic sull'evento <xref:System.Windows.Forms.ToolStripItem.Click>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="f9e46-134">Il Progettazione Windows Form genera un gestore eventi per l'evento <xref:System.Windows.Forms.ToolStripItem.Click>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="f9e46-135">Inserire il codice seguente nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f9e46-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="f9e46-136">Aggiungere il controllo ToolStripPanel alla casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="f9e46-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="f9e46-137">Quando si usano <xref:System.Windows.Forms.MenuStrip> controlli con un form MDI, è necessario avere il controllo <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="f9e46-138">È necessario aggiungere il controllo <xref:System.Windows.Forms.ToolStripPanel> alla **casella degli strumenti** per compilare il form MDI nel Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f9e46-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="f9e46-139">Aprire la **casella degli strumenti**, quindi fare clic sulla scheda **tutti Windows Forms** per visualizzare i controlli Windows Forms disponibili.</span><span class="sxs-lookup"><span data-stu-id="f9e46-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="f9e46-140">Fare clic con il pulsante destro del mouse per aprire il menu di scelta rapida e **scegliere Scegli elementi**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="f9e46-141">Nella finestra di dialogo **Scegli elementi della casella degli strumenti** scorrere verso il basso la colonna **nome** fino a quando non si trova **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="f9e46-142">Selezionare la casella di controllo in base a **ToolStripPanel**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="f9e46-143">Il controllo <xref:System.Windows.Forms.ToolStripPanel> viene visualizzato nella **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="f9e46-144">Creare un form figlio</span><span class="sxs-lookup"><span data-stu-id="f9e46-144">Create a child form</span></span>

<span data-ttu-id="f9e46-145">In questa procedura si definirà una classe di form figlio separata che dispone di un proprio <xref:System.Windows.Forms.MenuStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="f9e46-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="f9e46-146">Le voci di menu per questo form sono unite a quelle del form padre.</span><span class="sxs-lookup"><span data-stu-id="f9e46-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="f9e46-147">Aggiungere un nuovo form denominato `ChildForm` al progetto.</span><span class="sxs-lookup"><span data-stu-id="f9e46-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="f9e46-148">Per altre informazioni, vedere [procedura: aggiungere Windows Forms a un progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f9e46-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="f9e46-149">Dalla **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.MenuStrip> nel form figlio.</span><span class="sxs-lookup"><span data-stu-id="f9e46-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="f9e46-150">Fare clic sul glifo delle azioni della finestra di progettazione del controllo <xref:System.Windows.Forms.MenuStrip> (![Small Black Arrow](./media/designer-actions-glyph.gif)), quindi selezionare **modifica elementi**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-150">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="f9e46-151">Nella finestra di dialogo **Editor della raccolta Items** aggiungere un nuovo <xref:System.Windows.Forms.ToolStripMenuItem> denominato **ChildMenuItem** al menu figlio.</span><span class="sxs-lookup"><span data-stu-id="f9e46-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="f9e46-152">Per altre informazioni, vedere [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f9e46-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="f9e46-153">Testare il modulo</span><span class="sxs-lookup"><span data-stu-id="f9e46-153">Test the form</span></span>

1. <span data-ttu-id="f9e46-154">Premere **F5** per compilare ed eseguire il modulo.</span><span class="sxs-lookup"><span data-stu-id="f9e46-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="f9e46-155">Fare clic sulla voce di menu **finestra** per aprire il menu, quindi fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="f9e46-156">Un nuovo form figlio viene creato nell'area client MDI del form.</span><span class="sxs-lookup"><span data-stu-id="f9e46-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="f9e46-157">Il menu del form figlio viene unito al menu principale.</span><span class="sxs-lookup"><span data-stu-id="f9e46-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="f9e46-158">Chiudere il form figlio.</span><span class="sxs-lookup"><span data-stu-id="f9e46-158">Close the child form.</span></span>

     <span data-ttu-id="f9e46-159">Il menu del form figlio viene rimosso dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="f9e46-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="f9e46-160">Fare clic su **nuovo** più volte.</span><span class="sxs-lookup"><span data-stu-id="f9e46-160">Click **New** several times.</span></span>

     <span data-ttu-id="f9e46-161">I form figlio vengono elencati automaticamente sotto la voce di menu **finestra** perché viene assegnata la proprietà <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> del controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="f9e46-162">Aggiungi supporto ToolStrip</span><span class="sxs-lookup"><span data-stu-id="f9e46-162">Add ToolStrip support</span></span>

<span data-ttu-id="f9e46-163">In questa procedura vengono aggiunti quattro controlli <xref:System.Windows.Forms.ToolStrip> al form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="f9e46-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="f9e46-164">Ogni controllo <xref:System.Windows.Forms.ToolStrip> viene aggiunto all'interno di un controllo <xref:System.Windows.Forms.ToolStripPanel>, che è ancorato al bordo del form.</span><span class="sxs-lookup"><span data-stu-id="f9e46-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="f9e46-165">Dalla **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.ToolStripPanel> nel form.</span><span class="sxs-lookup"><span data-stu-id="f9e46-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="f9e46-166">Con il controllo <xref:System.Windows.Forms.ToolStripPanel> selezionato, fare doppio clic sul controllo <xref:System.Windows.Forms.ToolStrip> nella **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="f9e46-167">Nel controllo <xref:System.Windows.Forms.ToolStripPanel> viene creato un controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="f9e46-168">Selezionare il controllo <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="f9e46-169">Nella Finestra Proprietà modificare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> del controllo in <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="f9e46-170">Il controllo <xref:System.Windows.Forms.ToolStripPanel> ancorato al lato sinistro del form, sotto il menu principale.</span><span class="sxs-lookup"><span data-stu-id="f9e46-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="f9e46-171">L'area client MDI viene ridimensionata per adattarsi al controllo <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="f9e46-172">Ripetere i passaggi da 1 a 4.</span><span class="sxs-lookup"><span data-stu-id="f9e46-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="f9e46-173">Ancorare il nuovo controllo <xref:System.Windows.Forms.ToolStripPanel> alla parte superiore del form.</span><span class="sxs-lookup"><span data-stu-id="f9e46-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="f9e46-174">Il controllo <xref:System.Windows.Forms.ToolStripPanel> è ancorato al di sotto del menu principale, ma a destra del primo controllo <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="f9e46-175">In questo passaggio viene illustrata l'importanza dell'ordine z nel posizionamento corretto dei controlli <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="f9e46-176">Ripetere i passaggi da 1 a 4 per altri due controlli <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="f9e46-177">Ancorare i nuovi controlli <xref:System.Windows.Forms.ToolStripPanel> a destra e in basso nel form.</span><span class="sxs-lookup"><span data-stu-id="f9e46-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="f9e46-178">Disporre i controlli ToolStripPanel in base all'ordine Z</span><span class="sxs-lookup"><span data-stu-id="f9e46-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="f9e46-179">La posizione di un controllo <xref:System.Windows.Forms.ToolStripPanel> ancorato nel form MDI è determinata dalla posizione del controllo nell'ordine z.</span><span class="sxs-lookup"><span data-stu-id="f9e46-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="f9e46-180">È possibile organizzare facilmente l'ordine z dei controlli nella finestra Struttura documento.</span><span class="sxs-lookup"><span data-stu-id="f9e46-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="f9e46-181">Scegliere **altre finestre**dal menu **Visualizza** , quindi fare clic su **struttura documento**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="f9e46-182">La disposizione dei controlli <xref:System.Windows.Forms.ToolStripPanel> dalla procedura precedente non è standard.</span><span class="sxs-lookup"><span data-stu-id="f9e46-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="f9e46-183">Questo è dovuto al fatto che l'ordine z non è corretto.</span><span class="sxs-lookup"><span data-stu-id="f9e46-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="f9e46-184">Utilizzare la finestra Struttura documento per modificare l'ordine z dei controlli.</span><span class="sxs-lookup"><span data-stu-id="f9e46-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="f9e46-185">Nella finestra Struttura documento selezionare **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="f9e46-186">Fare clic ripetutamente sul pulsante freccia giù, fino a quando **ToolStripPanel4** non si trova nella parte inferiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f9e46-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="f9e46-187">Il controllo **ToolStripPanel4** è ancorato alla parte inferiore del form, sotto gli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="f9e46-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="f9e46-188">Selezionare **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="f9e46-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="f9e46-189">Fare clic sul pulsante freccia giù una volta per posizionare il terzo controllo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f9e46-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="f9e46-190">Il controllo **ToolStripPanel2** è ancorato alla parte superiore del form, sotto il menu principale e sopra gli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="f9e46-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="f9e46-191">Selezionare vari controlli nella finestra **struttura documento** e spostarli in posizioni diverse nell'ordine z.</span><span class="sxs-lookup"><span data-stu-id="f9e46-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="f9e46-192">Si noti l'effetto dell'ordine z sul posizionamento dei controlli ancorati.</span><span class="sxs-lookup"><span data-stu-id="f9e46-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="f9e46-193">Usare CTRL + Z o **Annulla** nel menu **modifica** per annullare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="f9e46-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="f9e46-194">Checkpoint-testare il modulo</span><span class="sxs-lookup"><span data-stu-id="f9e46-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="f9e46-195">Premere **F5** per compilare ed eseguire il modulo.</span><span class="sxs-lookup"><span data-stu-id="f9e46-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="f9e46-196">Fare clic sul riquadro di un controllo <xref:System.Windows.Forms.ToolStrip> e trascinare il controllo in posizioni diverse sul form.</span><span class="sxs-lookup"><span data-stu-id="f9e46-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="f9e46-197">È possibile trascinare un controllo <xref:System.Windows.Forms.ToolStrip> da un controllo <xref:System.Windows.Forms.ToolStripPanel> a un altro.</span><span class="sxs-lookup"><span data-stu-id="f9e46-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f9e46-198">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f9e46-198">Next steps</span></span>

<span data-ttu-id="f9e46-199">In questa procedura dettagliata è stato creato un form padre MDI con controlli di <xref:System.Windows.Forms.ToolStrip> e Unione di menu.</span><span class="sxs-lookup"><span data-stu-id="f9e46-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="f9e46-200">È possibile usare la famiglia di controlli <xref:System.Windows.Forms.ToolStrip> per molti altri scopi:</span><span class="sxs-lookup"><span data-stu-id="f9e46-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="f9e46-201">Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="f9e46-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="f9e46-202">Per altre informazioni, vedere [Cenni preliminari sui componenti ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f9e46-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="f9e46-203">Creazione di un form con un menu standard popolato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f9e46-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="f9e46-204">Per ulteriori informazioni, vedere [procedura dettagliata: fornire voci di menu standard a un modulo](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="f9e46-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="f9e46-205">Dare ai <xref:System.Windows.Forms.ToolStrip> controlli un aspetto professionale.</span><span class="sxs-lookup"><span data-stu-id="f9e46-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="f9e46-206">Per altre informazioni, vedere [procedura: impostare il renderer ToolStrip per un'applicazione](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="f9e46-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9e46-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9e46-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="f9e46-208">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="f9e46-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="f9e46-209">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="f9e46-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="f9e46-210">Procedura: Inserire un MenuStrip in un menu a discesa MDI</span><span class="sxs-lookup"><span data-stu-id="f9e46-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="f9e46-211">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="f9e46-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
