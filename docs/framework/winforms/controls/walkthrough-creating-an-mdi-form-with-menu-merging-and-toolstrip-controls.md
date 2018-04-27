---
title: 'Procedura dettagliata: creazione di un form MDI con unione di menu e controlli ToolStrip'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc8214815beb0eac6fe3811ba198207a06ee1a9a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="c77b0-102">Procedura dettagliata: creazione di un form MDI con unione di menu e controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c77b0-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="c77b0-103">Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu.</span><span class="sxs-lookup"><span data-stu-id="c77b0-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="c77b0-104">I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="c77b0-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="c77b0-105">Questa procedura dettagliata viene illustrato come utilizzare <xref:System.Windows.Forms.ToolStripPanel> controlli con un form MDI.</span><span class="sxs-lookup"><span data-stu-id="c77b0-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="c77b0-106">Il form supporta anche l'unione dei menu con menu figlio.</span><span class="sxs-lookup"><span data-stu-id="c77b0-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="c77b0-107">Nella procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="c77b0-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="c77b0-108">Creazione di un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c77b0-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="c77b0-109">Creazione del menu principale per il modulo.</span><span class="sxs-lookup"><span data-stu-id="c77b0-109">Creating the main menu for your form.</span></span> <span data-ttu-id="c77b0-110">Il nome effettivo del menu variano.</span><span class="sxs-lookup"><span data-stu-id="c77b0-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="c77b0-111">Aggiunta di <xref:System.Windows.Forms.ToolStripPanel> controllo il **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="c77b0-112">Creazione di un form figlio.</span><span class="sxs-lookup"><span data-stu-id="c77b0-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="c77b0-113">Disposizione <xref:System.Windows.Forms.ToolStripPanel> controlli in base all'ordine z.</span><span class="sxs-lookup"><span data-stu-id="c77b0-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="c77b0-114">Al termine, sarà necessario un form MDI che supporta l'unione di menu e mobili <xref:System.Windows.Forms.ToolStrip> controlli.</span><span class="sxs-lookup"><span data-stu-id="c77b0-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="c77b0-115">Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: creare un Form MDI con unione di Menu e controlli ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="c77b0-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c77b0-116">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="c77b0-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c77b0-117">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c77b0-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c77b0-118">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="c77b0-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c77b0-119">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c77b0-119">Prerequisites</span></span>  
 <span data-ttu-id="c77b0-120">Per completare questa procedura dettagliata, è necessario:</span><span class="sxs-lookup"><span data-stu-id="c77b0-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="c77b0-121">Disporre di autorizzazioni sufficienti creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c77b0-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="c77b0-122">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="c77b0-122">Creating the Project</span></span>  
 <span data-ttu-id="c77b0-123">Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.</span><span class="sxs-lookup"><span data-stu-id="c77b0-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="c77b0-124">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="c77b0-124">To create the project</span></span>  
  
1.  <span data-ttu-id="c77b0-125">Creare un progetto applicazione Windows denominato **MDI**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-125">Create a Windows Application project called **MdiForm**.</span></span>  
  
     <span data-ttu-id="c77b0-126">Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione Windows Form](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="c77b0-126">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="c77b0-127">In Progettazione Windows Form, selezionare il form.</span><span class="sxs-lookup"><span data-stu-id="c77b0-127">In the Windows Forms Designer, select the form.</span></span>  
  
3.  <span data-ttu-id="c77b0-128">Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.Form.IsMdiContainer%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="c77b0-128">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="c77b0-129">Creazione del Menu principale</span><span class="sxs-lookup"><span data-stu-id="c77b0-129">Creating the Main Menu</span></span>  
 <span data-ttu-id="c77b0-130">Form padre MDI contiene il menu principale.</span><span class="sxs-lookup"><span data-stu-id="c77b0-130">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="c77b0-131">Nel menu principale contiene una voce **finestra**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-131">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="c77b0-132">Con il **finestra** voce di menu, è possibile creare form figlio.</span><span class="sxs-lookup"><span data-stu-id="c77b0-132">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="c77b0-133">Voci di menu da form figlio vengono unite nel menu principale.</span><span class="sxs-lookup"><span data-stu-id="c77b0-133">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="c77b0-134">Per creare menu principale</span><span class="sxs-lookup"><span data-stu-id="c77b0-134">To create the Main menu</span></span>  
  
1.  <span data-ttu-id="c77b0-135">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="c77b0-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2.  <span data-ttu-id="c77b0-136">Aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> per il <xref:System.Windows.Forms.MenuStrip> controllare e denominarlo **finestra**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-136">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3.  <span data-ttu-id="c77b0-137">Selezionare il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="c77b0-137">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4.  <span data-ttu-id="c77b0-138">Nella finestra Proprietà impostare il valore della <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="c77b0-138">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5.  <span data-ttu-id="c77b0-139">Aggiungere un elemento secondario per il **finestra** voce di menu e quindi nome dell'elemento secondario **New**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-139">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6.  <span data-ttu-id="c77b0-140">Nella finestra Proprietà fare clic su **eventi**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-140">In the Properties window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="c77b0-141">Fare doppio clic su di <xref:System.Windows.Forms.ToolStripItem.Click> evento.</span><span class="sxs-lookup"><span data-stu-id="c77b0-141">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="c77b0-142">Progettazione Windows Form genera un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> evento.</span><span class="sxs-lookup"><span data-stu-id="c77b0-142">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8.  <span data-ttu-id="c77b0-143">Inserire il codice seguente nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="c77b0-143">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="c77b0-144">Aggiunta del controllo ToolStripPanel alla casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="c77b0-144">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="c77b0-145">Quando si utilizza <xref:System.Windows.Forms.MenuStrip> controlli con un form MDI è necessario disporre di <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="c77b0-145">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="c77b0-146">È necessario aggiungere il <xref:System.Windows.Forms.ToolStripPanel> controllo il **della casella degli strumenti** per compilare il form MDI in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c77b0-146">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="c77b0-147">Per aggiungere il controllo ToolStripPanel alla casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="c77b0-147">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="c77b0-148">Aprire il **della casella degli strumenti**e quindi fare clic su di **tutti i Windows Form** scheda per visualizzare i controlli Windows Form disponibili.</span><span class="sxs-lookup"><span data-stu-id="c77b0-148">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2.  <span data-ttu-id="c77b0-149">Per aprire il menu di scelta rapida e scegliere **Scegli elementi**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-149">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3.  <span data-ttu-id="c77b0-150">Nel **Scegli elementi della casella degli strumenti** la finestra di dialogo, scorrere verso il basso il **nome** colonna fino a individuare **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-150">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4.  <span data-ttu-id="c77b0-151">Selezionare la casella di controllo da **ToolStripPanel**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-151">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c77b0-152">Il <xref:System.Windows.Forms.ToolStripPanel> verrà visualizzato un controllo di **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-152">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="c77b0-153">Creazione di un Form figlio</span><span class="sxs-lookup"><span data-stu-id="c77b0-153">Creating a Child Form</span></span>  
 <span data-ttu-id="c77b0-154">In questa procedura, definire una classe di form figlio separata che dispone di una propria <xref:System.Windows.Forms.MenuStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="c77b0-154">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="c77b0-155">Le voci di menu per questo form vengono unite con quelle del form padre.</span><span class="sxs-lookup"><span data-stu-id="c77b0-155">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="c77b0-156">Per definire un form figlio</span><span class="sxs-lookup"><span data-stu-id="c77b0-156">To define a child form</span></span>  
  
1.  <span data-ttu-id="c77b0-157">Aggiungere un nuovo form denominato `ChildForm` al progetto.</span><span class="sxs-lookup"><span data-stu-id="c77b0-157">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="c77b0-158">Per ulteriori informazioni, vedere [procedura: aggiungere Windows Form a un progetto](http://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="c77b0-158">For more information, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
2.  <span data-ttu-id="c77b0-159">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form figlio.</span><span class="sxs-lookup"><span data-stu-id="c77b0-159">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3.  <span data-ttu-id="c77b0-160">Fare clic sul <xref:System.Windows.Forms.MenuStrip> glifo dello smart tag del controllo (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), quindi selezionare **Modifica elementi**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-160">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4.  <span data-ttu-id="c77b0-161">Nel **Editor della raccolta Items** finestra di dialogo, aggiungere un nuovo <xref:System.Windows.Forms.ToolStripMenuItem> denominato **ChildMenuItem** al menu figlio.</span><span class="sxs-lookup"><span data-stu-id="c77b0-161">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="c77b0-162">Per ulteriori informazioni, vedere [Editor raccolta Items di ToolStrip](http://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span><span class="sxs-lookup"><span data-stu-id="c77b0-162">For more information, see [ToolStrip Items Collection Editor](http://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="c77b0-163">Il modulo di test</span><span class="sxs-lookup"><span data-stu-id="c77b0-163">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="c77b0-164">Per verificare il modulo</span><span class="sxs-lookup"><span data-stu-id="c77b0-164">To test your form</span></span>  
  
1.  <span data-ttu-id="c77b0-165">Premere F5 per compilare ed eseguire il modulo.</span><span class="sxs-lookup"><span data-stu-id="c77b0-165">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="c77b0-166">Fare clic su di **finestra** voce di menu per aprire il menu e quindi fare clic su **New**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-166">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="c77b0-167">Nell'area di client MDI del form, viene creato un nuovo form figlio.</span><span class="sxs-lookup"><span data-stu-id="c77b0-167">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="c77b0-168">Menu del form figlio verrà unito nel menu principale.</span><span class="sxs-lookup"><span data-stu-id="c77b0-168">The child form's menu is merged with the main menu.</span></span>  
  
3.  <span data-ttu-id="c77b0-169">Chiudere il form figlio.</span><span class="sxs-lookup"><span data-stu-id="c77b0-169">Close the child form.</span></span>  
  
     <span data-ttu-id="c77b0-170">Menu del form figlio viene rimosso dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="c77b0-170">The child form's menu is removed from the main menu.</span></span>  
  
4.  <span data-ttu-id="c77b0-171">Fare clic su **New** più volte.</span><span class="sxs-lookup"><span data-stu-id="c77b0-171">Click **New** several times.</span></span>  
  
     <span data-ttu-id="c77b0-172">I form figlio automaticamente sono elencati sotto la W**finestra** perché la voce del menu di <xref:System.Windows.Forms.MenuStrip> del controllo <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà viene assegnato.</span><span class="sxs-lookup"><span data-stu-id="c77b0-172">The child forms are automatically listed under the W**indow** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="c77b0-173">Aggiunta del supporto di ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c77b0-173">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="c77b0-174">In questa procedura, si aggiungeranno quattro <xref:System.Windows.Forms.ToolStrip> controlli al form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="c77b0-174">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="c77b0-175">Ogni <xref:System.Windows.Forms.ToolStrip> controllo viene aggiunto all'interno di un <xref:System.Windows.Forms.ToolStripPanel> controllo viene ancorato al bordo del form.</span><span class="sxs-lookup"><span data-stu-id="c77b0-175">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="c77b0-176">Per aggiungere controlli ToolStrip al form padre MDI</span><span class="sxs-lookup"><span data-stu-id="c77b0-176">To add ToolStrip controls to the MDI parent form</span></span>  
  
1.  <span data-ttu-id="c77b0-177">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.ToolStripPanel> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="c77b0-177">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2.  <span data-ttu-id="c77b0-178">Con il <xref:System.Windows.Forms.ToolStripPanel> controllo selezionato, fare doppio clic sul <xref:System.Windows.Forms.ToolStrip> controllo il **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-178">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="c77b0-179">Oggetto <xref:System.Windows.Forms.ToolStrip> controllo viene creato nel <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="c77b0-179">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3.  <span data-ttu-id="c77b0-180">Selezionare il controllo <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="c77b0-180">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4.  <span data-ttu-id="c77b0-181">Nella finestra Proprietà modificare il valore del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="c77b0-181">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="c77b0-182">Il <xref:System.Windows.Forms.ToolStripPanel> controllare il controllo viene ancorato al lato sinistro del form, di sotto del menu principale.</span><span class="sxs-lookup"><span data-stu-id="c77b0-182">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="c77b0-183">L'area client MDI viene ridimensionato il <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="c77b0-183">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5.  <span data-ttu-id="c77b0-184">Ripetere i passaggi da 1 a 4.</span><span class="sxs-lookup"><span data-stu-id="c77b0-184">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="c77b0-185">Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controllo nella parte superiore del form.</span><span class="sxs-lookup"><span data-stu-id="c77b0-185">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="c77b0-186">Il <xref:System.Windows.Forms.ToolStripPanel> controllo viene ancorato di sotto del menu principale, ma a destra del primo <xref:System.Windows.Forms.ToolStripPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="c77b0-186">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="c77b0-187">Questo passaggio viene illustrata l'importanza dell'ordine z per il corretto posizionamento <xref:System.Windows.Forms.ToolStripPanel> controlli.</span><span class="sxs-lookup"><span data-stu-id="c77b0-187">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6.  <span data-ttu-id="c77b0-188">Ripetere i passaggi da 1 a 4 per altre due <xref:System.Windows.Forms.ToolStripPanel> controlli.</span><span class="sxs-lookup"><span data-stu-id="c77b0-188">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="c77b0-189">Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controlli a destra e inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="c77b0-189">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="c77b0-190">Disposizione dei controlli ToolStripPanel dall'ordine Z</span><span class="sxs-lookup"><span data-stu-id="c77b0-190">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="c77b0-191">La posizione di un ancorato <xref:System.Windows.Forms.ToolStripPanel> controllo sul form MDI è determinato dalla posizione del controllo nell'ordine z.</span><span class="sxs-lookup"><span data-stu-id="c77b0-191">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="c77b0-192">È possibile disporre facilmente l'ordine z dei controlli nella finestra Struttura documento.</span><span class="sxs-lookup"><span data-stu-id="c77b0-192">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="c77b0-193">Per disporre i controlli ToolStripPanel dall'ordine Z</span><span class="sxs-lookup"><span data-stu-id="c77b0-193">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1.  <span data-ttu-id="c77b0-194">Nel **vista** menu, fare clic su **altre finestre**, quindi fare clic su **struttura documento**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-194">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="c77b0-195">La disposizione del <xref:System.Windows.Forms.ToolStripPanel> controlli della procedura precedente è conforme allo standard.</span><span class="sxs-lookup"><span data-stu-id="c77b0-195">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="c77b0-196">In questo modo l'ordine z non è corretto.</span><span class="sxs-lookup"><span data-stu-id="c77b0-196">This is because the z-order is not correct.</span></span> <span data-ttu-id="c77b0-197">Utilizzare la finestra Struttura documento per modificare l'ordine z dei controlli.</span><span class="sxs-lookup"><span data-stu-id="c77b0-197">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2.  <span data-ttu-id="c77b0-198">Nella finestra Struttura documento selezionare **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-198">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3.  <span data-ttu-id="c77b0-199">Fare clic sul pulsante freccia in giù più volte, fino a **ToolStripPanel4** nella parte inferiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c77b0-199">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="c77b0-200">Il **ToolStripPanel4** controllo è ancorato alla parte inferiore del form, di sotto degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="c77b0-200">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4.  <span data-ttu-id="c77b0-201">Selezionare **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="c77b0-201">Select **ToolStripPanel2**.</span></span>  
  
5.  <span data-ttu-id="c77b0-202">Fare clic sul pulsante freccia in giù una volta per posizionare il controllo terzo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c77b0-202">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="c77b0-203">Il **ToolStripPanel2** controllo viene ancorato alla parte superiore del modulo, di sotto del menu principale e di sopra degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="c77b0-203">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6.  <span data-ttu-id="c77b0-204">Selezionare vari controlli di **struttura documento** finestra e spostarli in posizioni diverse nell'ordine z.</span><span class="sxs-lookup"><span data-stu-id="c77b0-204">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="c77b0-205">Notare l'effetto dello z-order sul posizionamento dei controlli ancorati.</span><span class="sxs-lookup"><span data-stu-id="c77b0-205">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="c77b0-206">Utilizzare CTRL-Z o **Annulla** sul **modifica** menu per annullare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="c77b0-206">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="c77b0-207">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="c77b0-207">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="c77b0-208">Per verificare il modulo</span><span class="sxs-lookup"><span data-stu-id="c77b0-208">To test your form</span></span>  
  
1.  <span data-ttu-id="c77b0-209">Premere F5 per compilare ed eseguire il modulo.</span><span class="sxs-lookup"><span data-stu-id="c77b0-209">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="c77b0-210">Fare clic su riquadro di ridimensionamento di un <xref:System.Windows.Forms.ToolStrip> controllo e trascinare il controllo in diverse posizioni nel form.</span><span class="sxs-lookup"><span data-stu-id="c77b0-210">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="c77b0-211">È possibile trascinare un <xref:System.Windows.Forms.ToolStrip> controllo da uno <xref:System.Windows.Forms.ToolStripPanel> controllo a un altro.</span><span class="sxs-lookup"><span data-stu-id="c77b0-211">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c77b0-212">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c77b0-212">Next Steps</span></span>  
 <span data-ttu-id="c77b0-213">In questa procedura dettagliata creato un form padre MDI con <xref:System.Windows.Forms.ToolStrip> unione dei menu e controlli.</span><span class="sxs-lookup"><span data-stu-id="c77b0-213">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="c77b0-214">È possibile utilizzare il <xref:System.Windows.Forms.ToolStrip> famiglia di controlli per molte altre operazioni:</span><span class="sxs-lookup"><span data-stu-id="c77b0-214">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="c77b0-215">Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="c77b0-215">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="c77b0-216">Per ulteriori informazioni, vedere [Cenni preliminari sul componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c77b0-216">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="c77b0-217">Creare un form con un menu standard popolato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c77b0-217">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="c77b0-218">Per ulteriori informazioni, vedere [procedura dettagliata: fornire le voci di Menu Standard a un Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="c77b0-218">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="c77b0-219">Assegnare il <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale.</span><span class="sxs-lookup"><span data-stu-id="c77b0-219">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="c77b0-220">Per ulteriori informazioni, vedere [procedura: impostare il ToolStrip Renderer per un'applicazione](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="c77b0-220">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c77b0-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c77b0-221">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="c77b0-222">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="c77b0-222">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="c77b0-223">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="c77b0-223">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="c77b0-224">Procedura: Inserire un MenuStrip in un menu a discesa MDI</span><span class="sxs-lookup"><span data-stu-id="c77b0-224">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [<span data-ttu-id="c77b0-225">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c77b0-225">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
