---
title: 'Procedura dettagliata: Creazione di un modulo con interfaccia a documenti multipli con unione di menu e controlli ToolStrip'
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
ms.openlocfilehash: 5853760231cbece27805923c009d83e16c9b0a5e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211565"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="34e7d-102">Procedura dettagliata: Creazione di un modulo con interfaccia a documenti multipli con unione di menu e controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="34e7d-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="34e7d-103">Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu.</span><span class="sxs-lookup"><span data-stu-id="34e7d-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="34e7d-104">I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="34e7d-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="34e7d-105">Questa procedura dettagliata illustra come usare <xref:System.Windows.Forms.ToolStripPanel> controlli con un form MDI.</span><span class="sxs-lookup"><span data-stu-id="34e7d-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="34e7d-106">Il form supporta anche l'unione dei menu con menu figlio.</span><span class="sxs-lookup"><span data-stu-id="34e7d-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="34e7d-107">Nella procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="34e7d-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="34e7d-108">Creazione di un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="34e7d-109">Creazione del menu principale per il form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-109">Creating the main menu for your form.</span></span> <span data-ttu-id="34e7d-110">Il nome effettivo del menu variano.</span><span class="sxs-lookup"><span data-stu-id="34e7d-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="34e7d-111">Aggiunta il <xref:System.Windows.Forms.ToolStripPanel> controllare per il **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="34e7d-112">Creazione di un form figlio.</span><span class="sxs-lookup"><span data-stu-id="34e7d-112">Creating a child form.</span></span>

- <span data-ttu-id="34e7d-113">Disposizione <xref:System.Windows.Forms.ToolStripPanel> controlli l'ordine z.</span><span class="sxs-lookup"><span data-stu-id="34e7d-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="34e7d-114">Al termine, si avrà un form MDI che supporta l'unione di menu e movable <xref:System.Windows.Forms.ToolStrip> controlli.</span><span class="sxs-lookup"><span data-stu-id="34e7d-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="34e7d-115">Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Creare un Form MDI con unione di Menu e controlli ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="34e7d-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34e7d-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="34e7d-116">Prerequisites</span></span>

<span data-ttu-id="34e7d-117">È necessario Visual Studio per completare questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="34e7d-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="34e7d-118">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="34e7d-118">Create the project</span></span>

1. <span data-ttu-id="34e7d-119">In Visual Studio, creare un progetto applicazione Windows denominato **MDI** (**File** > **nuovo** > **progetto**  >  **Visual C#**  oppure **Visual Basic** > **Desktop classico**  >   **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="34e7d-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="34e7d-120">Nella finestra di progettazione Windows Form, selezionare il form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="34e7d-121">Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.Form.IsMdiContainer%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="34e7d-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="34e7d-122">Creare menu principale</span><span class="sxs-lookup"><span data-stu-id="34e7d-122">Create the main menu</span></span>

<span data-ttu-id="34e7d-123">Form padre MDI contiene il menu principale.</span><span class="sxs-lookup"><span data-stu-id="34e7d-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="34e7d-124">Nel menu principale contiene una voce **finestra**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="34e7d-125">Con il **finestra** voce di menu, è possibile creare form figlio.</span><span class="sxs-lookup"><span data-stu-id="34e7d-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="34e7d-126">Voci di menu da form figlio vengono unite nel menu principale.</span><span class="sxs-lookup"><span data-stu-id="34e7d-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="34e7d-127">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="34e7d-128">Aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> per il <xref:System.Windows.Forms.MenuStrip> controllano e denominarlo **finestra**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="34e7d-129">Selezionare il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="34e7d-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="34e7d-130">Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="34e7d-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="34e7d-131">Aggiungere un elemento secondario per il **finestra** voce di menu e quindi denominare l'elemento secondario **New**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="34e7d-132">Nella finestra Proprietà, fare clic su **eventi**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="34e7d-133">Fare doppio clic il <xref:System.Windows.Forms.ToolStripItem.Click> evento.</span><span class="sxs-lookup"><span data-stu-id="34e7d-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="34e7d-134">Finestra di progettazione Windows Form genera un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> evento.</span><span class="sxs-lookup"><span data-stu-id="34e7d-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="34e7d-135">Inserire il codice seguente nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="34e7d-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="34e7d-136">Aggiungere il controllo ToolStripPanel nella casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="34e7d-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="34e7d-137">Quando si usa <xref:System.Windows.Forms.MenuStrip> controlli con un form MDI, è necessario disporre di <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="34e7d-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="34e7d-138">È necessario aggiungere il <xref:System.Windows.Forms.ToolStripPanel> controllare per il **della casella degli strumenti** per compilare il form MDI in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="34e7d-139">Aprire il **casella degli strumenti**e quindi fare clic sul **tutti i Windows Form** pressione di tab per visualizzare i controlli Windows Form disponibili.</span><span class="sxs-lookup"><span data-stu-id="34e7d-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="34e7d-140">Per aprire il menu di scelta rapida e scegliere **Scegli elementi**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="34e7d-141">Nel **Scegli elementi della casella degli strumenti** finestra di dialogo, scorrere verso il basso il **Name** colonna fino a individuare **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="34e7d-142">Selezionare la casella di controllo da **ToolStripPanel**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="34e7d-143">Il <xref:System.Windows.Forms.ToolStripPanel> controllo viene visualizzato nei **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="34e7d-144">Creare un form figlio</span><span class="sxs-lookup"><span data-stu-id="34e7d-144">Create a child form</span></span>

<span data-ttu-id="34e7d-145">In questa procedura, si definirà una classe di form figlio separata che dispone di una propria <xref:System.Windows.Forms.MenuStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="34e7d-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="34e7d-146">Le voci di menu per questo modulo vengono unite con quelle del form padre.</span><span class="sxs-lookup"><span data-stu-id="34e7d-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="34e7d-147">Aggiungere un nuovo form denominato `ChildForm` al progetto.</span><span class="sxs-lookup"><span data-stu-id="34e7d-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="34e7d-148">Per altre informazioni, vedere [Procedura: Aggiungi Windows Form a un progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="34e7d-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="34e7d-149">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form figlio.</span><span class="sxs-lookup"><span data-stu-id="34e7d-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="34e7d-150">Scegliere il <xref:System.Windows.Forms.MenuStrip> glifo smart tag del controllo (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e quindi selezionare **Modifica elementi**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-150">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="34e7d-151">Nel **Editor della raccolta Items** finestra di dialogo, aggiungere un nuovo <xref:System.Windows.Forms.ToolStripMenuItem> denominato **ChildMenuItem** al menu figlio.</span><span class="sxs-lookup"><span data-stu-id="34e7d-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="34e7d-152">Per altre informazioni, vedere [Editor di raccolta Items di ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="34e7d-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="34e7d-153">Verificare il modulo</span><span class="sxs-lookup"><span data-stu-id="34e7d-153">Test the form</span></span>

1. <span data-ttu-id="34e7d-154">Premere **F5** per compilare ed eseguire il form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="34e7d-155">Scegliere il **finestra** voce di menu per aprire il menu di scelta e quindi fare clic su **New**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="34e7d-156">Nell'area client MDI del form viene creato un nuovo form figlio.</span><span class="sxs-lookup"><span data-stu-id="34e7d-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="34e7d-157">Menu del form figlio verrà unito nel menu principale.</span><span class="sxs-lookup"><span data-stu-id="34e7d-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="34e7d-158">Chiudere il form figlio.</span><span class="sxs-lookup"><span data-stu-id="34e7d-158">Close the child form.</span></span>

     <span data-ttu-id="34e7d-159">Menu del form figlio viene rimosso dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="34e7d-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="34e7d-160">Fare clic su **New** più volte.</span><span class="sxs-lookup"><span data-stu-id="34e7d-160">Click **New** several times.</span></span>

     <span data-ttu-id="34e7d-161">I form figlio vengono automaticamente elencati sotto la **finestra** perché la voce del menu di <xref:System.Windows.Forms.MenuStrip> del controllo <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà viene assegnato.</span><span class="sxs-lookup"><span data-stu-id="34e7d-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="34e7d-162">Aggiungere il supporto di ToolStrip</span><span class="sxs-lookup"><span data-stu-id="34e7d-162">Add ToolStrip support</span></span>

<span data-ttu-id="34e7d-163">In questa procedura, si aggiungeranno quattro <xref:System.Windows.Forms.ToolStrip> controlli al form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="34e7d-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="34e7d-164">Ciascuna <xref:System.Windows.Forms.ToolStrip> controllo viene aggiunto all'interno di un <xref:System.Windows.Forms.ToolStripPanel> controllo, che viene ancorato al bordo del form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="34e7d-165">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.ToolStripPanel> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="34e7d-166">Con il <xref:System.Windows.Forms.ToolStripPanel> controllo è selezionata, fare doppio clic il <xref:System.Windows.Forms.ToolStrip> controllare nel **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="34e7d-167">Oggetto <xref:System.Windows.Forms.ToolStrip> viene creato nel controllo di <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="34e7d-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="34e7d-168">Selezionare il controllo <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="34e7d-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="34e7d-169">Nella finestra Proprietà modificare il valore del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="34e7d-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="34e7d-170">Il <xref:System.Windows.Forms.ToolStripPanel> controllano il controllo viene ancorato al lato sinistro del modulo, di sotto del menu principale.</span><span class="sxs-lookup"><span data-stu-id="34e7d-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="34e7d-171">L'area client MDI viene adattata per accogliere il <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="34e7d-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="34e7d-172">Ripetere i passaggi da 1 a 4.</span><span class="sxs-lookup"><span data-stu-id="34e7d-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="34e7d-173">Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controllo nella parte superiore del form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="34e7d-174">Il <xref:System.Windows.Forms.ToolStripPanel> controllo è ancorato di sotto del menu principale, ma a destra del primo <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="34e7d-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="34e7d-175">Questo passaggio dimostra l'importanza dell'ordine z il corretto posizionamento <xref:System.Windows.Forms.ToolStripPanel> controlli.</span><span class="sxs-lookup"><span data-stu-id="34e7d-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="34e7d-176">Ripetere i passaggi da 1 a 4 per due altre <xref:System.Windows.Forms.ToolStripPanel> controlli.</span><span class="sxs-lookup"><span data-stu-id="34e7d-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="34e7d-177">Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controlli a destra e inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="34e7d-178">Disporre i controlli ToolStripPanel l'ordine Z</span><span class="sxs-lookup"><span data-stu-id="34e7d-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="34e7d-179">La posizione di un ancoraggio <xref:System.Windows.Forms.ToolStripPanel> controllo sul form MDI viene determinato in base alla posizione del controllo nell'ordine z.</span><span class="sxs-lookup"><span data-stu-id="34e7d-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="34e7d-180">È possibile definire facilmente l'ordine z dei controlli nella finestra Struttura documento.</span><span class="sxs-lookup"><span data-stu-id="34e7d-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="34e7d-181">Nel **View** menu, fare clic su **Other Windows**e quindi fare clic su **struttura documento**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="34e7d-182">La disposizione delle <xref:System.Windows.Forms.ToolStripPanel> controlli della procedura precedente è conforme allo standard.</span><span class="sxs-lookup"><span data-stu-id="34e7d-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="34e7d-183">Questo avviene perché l'ordine z non sia corretto.</span><span class="sxs-lookup"><span data-stu-id="34e7d-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="34e7d-184">Utilizzare la finestra Struttura documento per modificare l'ordine z dei controlli.</span><span class="sxs-lookup"><span data-stu-id="34e7d-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="34e7d-185">Nella finestra Struttura documento, selezionare **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="34e7d-186">Fare clic sul pulsante freccia in giù più volte, fino alla **ToolStripPanel4** è nella parte inferiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="34e7d-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="34e7d-187">Il **ToolStripPanel4** controllo è ancorato alla parte inferiore del modulo, di sotto degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="34e7d-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="34e7d-188">Selezionare **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="34e7d-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="34e7d-189">Fare clic sul pulsante freccia in giù una sola volta per posizionare il controllo in terzo luogo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="34e7d-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="34e7d-190">Il **ToolStripPanel2** controllo è ancorato alla parte superiore del form, sotto il menu principale e di sopra degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="34e7d-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="34e7d-191">Selezionare diversi controlli del **struttura documento** finestra e spostarli in posizioni diverse nell'ordine z.</span><span class="sxs-lookup"><span data-stu-id="34e7d-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="34e7d-192">Notare l'effetto dello z-order nel posizionamento di controlli ancorati.</span><span class="sxs-lookup"><span data-stu-id="34e7d-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="34e7d-193">Usare CTRL-Z o **Undo** nel **modificare** menu annullare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="34e7d-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="34e7d-194">Checkpoint - modulo di test</span><span class="sxs-lookup"><span data-stu-id="34e7d-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="34e7d-195">Premere **F5** per compilare ed eseguire il form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="34e7d-196">Scegliere il triangolo di ridimensionamento di un <xref:System.Windows.Forms.ToolStrip> controllo e trascinare il controllo in diverse posizioni nel form.</span><span class="sxs-lookup"><span data-stu-id="34e7d-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="34e7d-197">È possibile trascinare un <xref:System.Windows.Forms.ToolStrip> controllo da una <xref:System.Windows.Forms.ToolStripPanel> controllo a altro.</span><span class="sxs-lookup"><span data-stu-id="34e7d-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="34e7d-198">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="34e7d-198">Next steps</span></span>

<span data-ttu-id="34e7d-199">In questa procedura dettagliata, si have creato un form padre MDI con <xref:System.Windows.Forms.ToolStrip> controlli e unione di menu.</span><span class="sxs-lookup"><span data-stu-id="34e7d-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="34e7d-200">È possibile usare il <xref:System.Windows.Forms.ToolStrip> della famiglia di controlli per molte altre operazioni:</span><span class="sxs-lookup"><span data-stu-id="34e7d-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="34e7d-201">Creare i menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="34e7d-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="34e7d-202">Per altre informazioni, vedere [Cenni preliminari sul componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="34e7d-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="34e7d-203">Creato un form con un menu standard popolato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="34e7d-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="34e7d-204">Per altre informazioni, vedere [Procedura dettagliata: Inserimento di voci di Menu Standard in un Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="34e7d-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="34e7d-205">Assegnare il <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale.</span><span class="sxs-lookup"><span data-stu-id="34e7d-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="34e7d-206">Per altre informazioni, vedere [Procedura: Impostare il ToolStrip Renderer per un'applicazione](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="34e7d-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="34e7d-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34e7d-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="34e7d-208">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="34e7d-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="34e7d-209">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="34e7d-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="34e7d-210">Procedura: Inserire un MenuStrip in un Menu a discesa MDI</span><span class="sxs-lookup"><span data-stu-id="34e7d-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="34e7d-211">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="34e7d-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
