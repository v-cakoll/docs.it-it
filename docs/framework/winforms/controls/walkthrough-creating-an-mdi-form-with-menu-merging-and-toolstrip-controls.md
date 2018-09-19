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
ms.openlocfilehash: 6236190340833e3f8810387e51ad53e1cb10d37b
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "46321114"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="6661b-102">Procedura dettagliata: creazione di un form MDI con unione di menu e controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6661b-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="6661b-103">Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu.</span><span class="sxs-lookup"><span data-stu-id="6661b-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="6661b-104">I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6661b-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="6661b-105">Questa procedura dettagliata illustra come usare <xref:System.Windows.Forms.ToolStripPanel> controlli con un form MDI.</span><span class="sxs-lookup"><span data-stu-id="6661b-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="6661b-106">Il form supporta anche l'unione dei menu con menu figlio.</span><span class="sxs-lookup"><span data-stu-id="6661b-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="6661b-107">Nella procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="6661b-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="6661b-108">Creazione di un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="6661b-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="6661b-109">Creazione del menu principale per il form.</span><span class="sxs-lookup"><span data-stu-id="6661b-109">Creating the main menu for your form.</span></span> <span data-ttu-id="6661b-110">Il nome effettivo del menu variano.</span><span class="sxs-lookup"><span data-stu-id="6661b-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="6661b-111">Aggiunta il <xref:System.Windows.Forms.ToolStripPanel> controllare per il **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="6661b-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="6661b-112">Creazione di un form figlio.</span><span class="sxs-lookup"><span data-stu-id="6661b-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="6661b-113">Disposizione <xref:System.Windows.Forms.ToolStripPanel> controlli l'ordine z.</span><span class="sxs-lookup"><span data-stu-id="6661b-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="6661b-114">Al termine, si avrà un form MDI che supporta l'unione di menu e movable <xref:System.Windows.Forms.ToolStrip> controlli.</span><span class="sxs-lookup"><span data-stu-id="6661b-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="6661b-115">Per copiare il codice in questo argomento come singolo listato, vedere [procedura: creare un Form MDI con unione di Menu e controlli ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="6661b-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6661b-116">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="6661b-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6661b-117">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="6661b-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6661b-118">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6661b-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6661b-119">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6661b-119">Prerequisites</span></span>  
 <span data-ttu-id="6661b-120">Per completare questa procedura dettagliata, è necessario:</span><span class="sxs-lookup"><span data-stu-id="6661b-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="6661b-121">Autorizzazioni sufficienti per essere in grado di creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6661b-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="6661b-122">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="6661b-122">Creating the Project</span></span>  
 <span data-ttu-id="6661b-123">Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.</span><span class="sxs-lookup"><span data-stu-id="6661b-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="6661b-124">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="6661b-124">To create the project</span></span>  
  
1.  <span data-ttu-id="6661b-125">Creare un progetto di applicazione Windows denominato **MDI** (**File** > **nuovo** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="6661b-125">Create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="6661b-126">Nella finestra di progettazione Windows Form, selezionare il form.</span><span class="sxs-lookup"><span data-stu-id="6661b-126">In the Windows Forms Designer, select the form.</span></span>  
  
3.  <span data-ttu-id="6661b-127">Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.Form.IsMdiContainer%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="6661b-127">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="6661b-128">Creazione del Menu principale</span><span class="sxs-lookup"><span data-stu-id="6661b-128">Creating the Main Menu</span></span>  
 <span data-ttu-id="6661b-129">Form padre MDI contiene il menu principale.</span><span class="sxs-lookup"><span data-stu-id="6661b-129">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="6661b-130">Nel menu principale contiene una voce **finestra**.</span><span class="sxs-lookup"><span data-stu-id="6661b-130">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="6661b-131">Con il **finestra** voce di menu, è possibile creare form figlio.</span><span class="sxs-lookup"><span data-stu-id="6661b-131">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="6661b-132">Voci di menu da form figlio vengono unite nel menu principale.</span><span class="sxs-lookup"><span data-stu-id="6661b-132">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="6661b-133">Per creare il menu principale</span><span class="sxs-lookup"><span data-stu-id="6661b-133">To create the Main menu</span></span>  
  
1.  <span data-ttu-id="6661b-134">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="6661b-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2.  <span data-ttu-id="6661b-135">Aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> per il <xref:System.Windows.Forms.MenuStrip> controllano e denominarlo **finestra**.</span><span class="sxs-lookup"><span data-stu-id="6661b-135">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3.  <span data-ttu-id="6661b-136">Selezionare il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="6661b-136">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4.  <span data-ttu-id="6661b-137">Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="6661b-137">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5.  <span data-ttu-id="6661b-138">Aggiungere un elemento secondario per il **finestra** voce di menu e quindi denominare l'elemento secondario **New**.</span><span class="sxs-lookup"><span data-stu-id="6661b-138">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6.  <span data-ttu-id="6661b-139">Nella finestra Proprietà, fare clic su **eventi**.</span><span class="sxs-lookup"><span data-stu-id="6661b-139">In the Properties window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="6661b-140">Fare doppio clic il <xref:System.Windows.Forms.ToolStripItem.Click> evento.</span><span class="sxs-lookup"><span data-stu-id="6661b-140">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="6661b-141">Finestra di progettazione Windows Form genera un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> evento.</span><span class="sxs-lookup"><span data-stu-id="6661b-141">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8.  <span data-ttu-id="6661b-142">Inserire il codice seguente nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="6661b-142">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="6661b-143">Aggiunta del controllo ToolStripPanel nella casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="6661b-143">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="6661b-144">Quando si usa <xref:System.Windows.Forms.MenuStrip> controlli con un form MDI, è necessario disporre di <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="6661b-144">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="6661b-145">È necessario aggiungere il <xref:System.Windows.Forms.ToolStripPanel> controllare per il **della casella degli strumenti** per compilare il form MDI in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="6661b-145">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="6661b-146">Per aggiungere il controllo ToolStripPanel nella casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="6661b-146">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="6661b-147">Aprire il **casella degli strumenti**e quindi fare clic sul **tutti i Windows Form** pressione di tab per visualizzare i controlli Windows Form disponibili.</span><span class="sxs-lookup"><span data-stu-id="6661b-147">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2.  <span data-ttu-id="6661b-148">Per aprire il menu di scelta rapida e scegliere **Scegli elementi**.</span><span class="sxs-lookup"><span data-stu-id="6661b-148">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3.  <span data-ttu-id="6661b-149">Nel **Scegli elementi della casella degli strumenti** finestra di dialogo, scorrere verso il basso il **Name** colonna fino a individuare **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="6661b-149">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4.  <span data-ttu-id="6661b-150">Selezionare la casella di controllo da **ToolStripPanel**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6661b-150">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6661b-151">Il <xref:System.Windows.Forms.ToolStripPanel> controllo viene visualizzato nei **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="6661b-151">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="6661b-152">Creazione di un Form figlio</span><span class="sxs-lookup"><span data-stu-id="6661b-152">Creating a Child Form</span></span>  
 <span data-ttu-id="6661b-153">In questa procedura, si definirà una classe di form figlio separata che dispone di una propria <xref:System.Windows.Forms.MenuStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="6661b-153">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="6661b-154">Le voci di menu per questo modulo vengono unite con quelle del form padre.</span><span class="sxs-lookup"><span data-stu-id="6661b-154">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="6661b-155">Per definire un form figlio</span><span class="sxs-lookup"><span data-stu-id="6661b-155">To define a child form</span></span>  
  
1.  <span data-ttu-id="6661b-156">Aggiungere un nuovo form denominato `ChildForm` al progetto.</span><span class="sxs-lookup"><span data-stu-id="6661b-156">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="6661b-157">Per altre informazioni, vedere [procedura: aggiungere Windows Form a un progetto](https://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="6661b-157">For more information, see [How to: Add Windows Forms to a Project](https://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
2.  <span data-ttu-id="6661b-158">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form figlio.</span><span class="sxs-lookup"><span data-stu-id="6661b-158">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3.  <span data-ttu-id="6661b-159">Scegliere il <xref:System.Windows.Forms.MenuStrip> glifo smart tag del controllo (![glifo Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e quindi selezionare **Modifica elementi**.</span><span class="sxs-lookup"><span data-stu-id="6661b-159">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4.  <span data-ttu-id="6661b-160">Nel **Editor della raccolta Items** finestra di dialogo, aggiungere un nuovo <xref:System.Windows.Forms.ToolStripMenuItem> denominato **ChildMenuItem** al menu figlio.</span><span class="sxs-lookup"><span data-stu-id="6661b-160">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="6661b-161">Per altre informazioni, vedere [Editor di raccolta Items di ToolStrip](https://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span><span class="sxs-lookup"><span data-stu-id="6661b-161">For more information, see [ToolStrip Items Collection Editor](https://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="6661b-162">Il modulo di test</span><span class="sxs-lookup"><span data-stu-id="6661b-162">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="6661b-163">Per testare il form</span><span class="sxs-lookup"><span data-stu-id="6661b-163">To test your form</span></span>  
  
1.  <span data-ttu-id="6661b-164">Premere F5 per compilare ed eseguire il form.</span><span class="sxs-lookup"><span data-stu-id="6661b-164">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="6661b-165">Scegliere il **finestra** voce di menu per aprire il menu di scelta e quindi fare clic su **New**.</span><span class="sxs-lookup"><span data-stu-id="6661b-165">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="6661b-166">Nell'area client MDI del form viene creato un nuovo form figlio.</span><span class="sxs-lookup"><span data-stu-id="6661b-166">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="6661b-167">Menu del form figlio verrà unito nel menu principale.</span><span class="sxs-lookup"><span data-stu-id="6661b-167">The child form's menu is merged with the main menu.</span></span>  
  
3.  <span data-ttu-id="6661b-168">Chiudere il form figlio.</span><span class="sxs-lookup"><span data-stu-id="6661b-168">Close the child form.</span></span>  
  
     <span data-ttu-id="6661b-169">Menu del form figlio viene rimosso dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="6661b-169">The child form's menu is removed from the main menu.</span></span>  
  
4.  <span data-ttu-id="6661b-170">Fare clic su **New** più volte.</span><span class="sxs-lookup"><span data-stu-id="6661b-170">Click **New** several times.</span></span>  
  
     <span data-ttu-id="6661b-171">I form figlio vengono automaticamente elencati sotto la **finestra** perché la voce del menu di <xref:System.Windows.Forms.MenuStrip> del controllo <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà viene assegnato.</span><span class="sxs-lookup"><span data-stu-id="6661b-171">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="6661b-172">Aggiunta del supporto di ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6661b-172">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="6661b-173">In questa procedura, si aggiungeranno quattro <xref:System.Windows.Forms.ToolStrip> controlli al form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="6661b-173">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="6661b-174">Ciascuna <xref:System.Windows.Forms.ToolStrip> controllo viene aggiunto all'interno di un <xref:System.Windows.Forms.ToolStripPanel> controllo, che viene ancorato al bordo del form.</span><span class="sxs-lookup"><span data-stu-id="6661b-174">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="6661b-175">Per aggiungere controlli ToolStrip al form padre MDI</span><span class="sxs-lookup"><span data-stu-id="6661b-175">To add ToolStrip controls to the MDI parent form</span></span>  
  
1.  <span data-ttu-id="6661b-176">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.ToolStripPanel> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="6661b-176">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2.  <span data-ttu-id="6661b-177">Con il <xref:System.Windows.Forms.ToolStripPanel> controllo è selezionata, fare doppio clic il <xref:System.Windows.Forms.ToolStrip> controllare nel **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="6661b-177">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="6661b-178">Oggetto <xref:System.Windows.Forms.ToolStrip> viene creato nel controllo di <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="6661b-178">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3.  <span data-ttu-id="6661b-179">Selezionare il controllo <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="6661b-179">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4.  <span data-ttu-id="6661b-180">Nella finestra Proprietà modificare il valore del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="6661b-180">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="6661b-181">Il <xref:System.Windows.Forms.ToolStripPanel> controllano il controllo viene ancorato al lato sinistro del modulo, di sotto del menu principale.</span><span class="sxs-lookup"><span data-stu-id="6661b-181">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="6661b-182">L'area client MDI viene adattata per accogliere il <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="6661b-182">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5.  <span data-ttu-id="6661b-183">Ripetere i passaggi da 1 a 4.</span><span class="sxs-lookup"><span data-stu-id="6661b-183">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="6661b-184">Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controllo nella parte superiore del form.</span><span class="sxs-lookup"><span data-stu-id="6661b-184">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="6661b-185">Il <xref:System.Windows.Forms.ToolStripPanel> controllo è ancorato di sotto del menu principale, ma a destra del primo <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="6661b-185">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="6661b-186">Questo passaggio dimostra l'importanza dell'ordine z il corretto posizionamento <xref:System.Windows.Forms.ToolStripPanel> controlli.</span><span class="sxs-lookup"><span data-stu-id="6661b-186">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6.  <span data-ttu-id="6661b-187">Ripetere i passaggi da 1 a 4 per due altre <xref:System.Windows.Forms.ToolStripPanel> controlli.</span><span class="sxs-lookup"><span data-stu-id="6661b-187">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="6661b-188">Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controlli a destra e inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="6661b-188">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="6661b-189">Disposizione dei controlli ToolStripPanel l'ordine Z</span><span class="sxs-lookup"><span data-stu-id="6661b-189">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="6661b-190">La posizione di un ancoraggio <xref:System.Windows.Forms.ToolStripPanel> controllo sul form MDI viene determinato in base alla posizione del controllo nell'ordine z.</span><span class="sxs-lookup"><span data-stu-id="6661b-190">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="6661b-191">È possibile definire facilmente l'ordine z dei controlli nella finestra Struttura documento.</span><span class="sxs-lookup"><span data-stu-id="6661b-191">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="6661b-192">Per disporre i controlli ToolStripPanel l'ordine Z</span><span class="sxs-lookup"><span data-stu-id="6661b-192">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1.  <span data-ttu-id="6661b-193">Nel **View** menu, fare clic su **Other Windows**e quindi fare clic su **struttura documento**.</span><span class="sxs-lookup"><span data-stu-id="6661b-193">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="6661b-194">La disposizione delle <xref:System.Windows.Forms.ToolStripPanel> controlli della procedura precedente è conforme allo standard.</span><span class="sxs-lookup"><span data-stu-id="6661b-194">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="6661b-195">Questo avviene perché l'ordine z non sia corretto.</span><span class="sxs-lookup"><span data-stu-id="6661b-195">This is because the z-order is not correct.</span></span> <span data-ttu-id="6661b-196">Utilizzare la finestra Struttura documento per modificare l'ordine z dei controlli.</span><span class="sxs-lookup"><span data-stu-id="6661b-196">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2.  <span data-ttu-id="6661b-197">Nella finestra Struttura documento, selezionare **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="6661b-197">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3.  <span data-ttu-id="6661b-198">Fare clic sul pulsante freccia in giù più volte, fino alla **ToolStripPanel4** è nella parte inferiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6661b-198">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="6661b-199">Il **ToolStripPanel4** controllo è ancorato alla parte inferiore del modulo, di sotto degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="6661b-199">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4.  <span data-ttu-id="6661b-200">Selezionare **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="6661b-200">Select **ToolStripPanel2**.</span></span>  
  
5.  <span data-ttu-id="6661b-201">Fare clic sul pulsante freccia in giù una sola volta per posizionare il controllo in terzo luogo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6661b-201">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="6661b-202">Il **ToolStripPanel2** controllo è ancorato alla parte superiore del form, sotto il menu principale e di sopra degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="6661b-202">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6.  <span data-ttu-id="6661b-203">Selezionare diversi controlli del **struttura documento** finestra e spostarli in posizioni diverse nell'ordine z.</span><span class="sxs-lookup"><span data-stu-id="6661b-203">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="6661b-204">Notare l'effetto dello z-order nel posizionamento di controlli ancorati.</span><span class="sxs-lookup"><span data-stu-id="6661b-204">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="6661b-205">Usare CTRL-Z o **Undo** nel **modificare** menu annullare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6661b-205">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="6661b-206">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="6661b-206">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="6661b-207">Per testare il form</span><span class="sxs-lookup"><span data-stu-id="6661b-207">To test your form</span></span>  
  
1.  <span data-ttu-id="6661b-208">Premere F5 per compilare ed eseguire il form.</span><span class="sxs-lookup"><span data-stu-id="6661b-208">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="6661b-209">Scegliere il triangolo di ridimensionamento di un <xref:System.Windows.Forms.ToolStrip> controllo e trascinare il controllo in diverse posizioni nel form.</span><span class="sxs-lookup"><span data-stu-id="6661b-209">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="6661b-210">È possibile trascinare un <xref:System.Windows.Forms.ToolStrip> controllo da una <xref:System.Windows.Forms.ToolStripPanel> controllo a altro.</span><span class="sxs-lookup"><span data-stu-id="6661b-210">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6661b-211">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6661b-211">Next Steps</span></span>  
 <span data-ttu-id="6661b-212">In questa procedura dettagliata, si have creato un form padre MDI con <xref:System.Windows.Forms.ToolStrip> controlli e unione di menu.</span><span class="sxs-lookup"><span data-stu-id="6661b-212">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="6661b-213">È possibile usare il <xref:System.Windows.Forms.ToolStrip> della famiglia di controlli per molte altre operazioni:</span><span class="sxs-lookup"><span data-stu-id="6661b-213">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="6661b-214">Creare i menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="6661b-214">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="6661b-215">Per altre informazioni, vedere [Cenni preliminari sul componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6661b-215">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="6661b-216">Creato un form con un menu standard popolato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6661b-216">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="6661b-217">Per altre informazioni, vedere [procedura dettagliata: inserimento di voci di Menu Standard in un Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="6661b-217">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="6661b-218">Assegnare il <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale.</span><span class="sxs-lookup"><span data-stu-id="6661b-218">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="6661b-219">Per altre informazioni, vedere [procedura: impostare il ToolStrip Renderer per un'applicazione](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="6661b-219">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6661b-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6661b-220">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="6661b-221">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="6661b-221">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="6661b-222">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="6661b-222">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="6661b-223">Procedura: Inserire un MenuStrip in un menu a discesa MDI</span><span class="sxs-lookup"><span data-stu-id="6661b-223">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [<span data-ttu-id="6661b-224">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6661b-224">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
