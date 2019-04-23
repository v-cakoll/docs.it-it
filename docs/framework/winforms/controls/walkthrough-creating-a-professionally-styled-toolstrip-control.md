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
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="ce467-102">Procedura dettagliata: Creazione di un controllo ToolStrip professionale</span><span class="sxs-lookup"><span data-stu-id="ce467-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="ce467-103">È possibile assegnare l'applicazione <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale scrivendo una classe personalizzata derivata dal <xref:System.Windows.Forms.ToolStripProfessionalRenderer> tipo.</span><span class="sxs-lookup"><span data-stu-id="ce467-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="ce467-104">Questa procedura dettagliata illustra come usare <xref:System.Windows.Forms.ToolStrip> controlli per creare un controllo composito che è simile al **riquadro di spostamento** fornito da Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="ce467-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="ce467-105">Nella procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce467-105">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="ce467-106">Creazione di un progetto libreria di controlli Windows.</span><span class="sxs-lookup"><span data-stu-id="ce467-106">Creating a Windows Control Library project.</span></span>  
  
-   <span data-ttu-id="ce467-107">Progettazione del controllo StackView.</span><span class="sxs-lookup"><span data-stu-id="ce467-107">Designing the StackView Control.</span></span>  
  
-   <span data-ttu-id="ce467-108">Implementazione di un Renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ce467-108">Implementing a Custom Renderer.</span></span>  
  
 <span data-ttu-id="ce467-109">Al termine, sarà necessario un controllo riutilizzabile client personalizzata con l'aspetto di un controllo di Microsoft Office® XP professional.</span><span class="sxs-lookup"><span data-stu-id="ce467-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>  
  
 <span data-ttu-id="ce467-110">Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Creare un controllo ToolStrip professionale](how-to-create-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="ce467-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce467-111">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="ce467-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ce467-112">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="ce467-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ce467-113">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="ce467-113">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ce467-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ce467-114">Prerequisites</span></span>  
 <span data-ttu-id="ce467-115">Per completare questa procedura dettagliata, è necessario:</span><span class="sxs-lookup"><span data-stu-id="ce467-115">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="ce467-116">Autorizzazioni sufficienti per essere in grado di creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce467-116">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-windows-control-library-project"></a><span data-ttu-id="ce467-117">Creazione di un progetto di libreria di controlli Windows</span><span class="sxs-lookup"><span data-stu-id="ce467-117">Creating a Windows Control Library Project</span></span>  
 <span data-ttu-id="ce467-118">Il primo passaggio consiste nel creare il progetto di libreria di controlli.</span><span class="sxs-lookup"><span data-stu-id="ce467-118">The first step is to create the control library project.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="ce467-119">Per creare il progetto di libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="ce467-119">To create the control library project</span></span>  
  
1. <span data-ttu-id="ce467-120">Creare un nuovo progetto di libreria di controlli di Windows denominato `StackViewLibrary`.</span><span class="sxs-lookup"><span data-stu-id="ce467-120">Create a new Windows Control Library project named `StackViewLibrary`.</span></span>  
  
2. <span data-ttu-id="ce467-121">Nelle **Esplora soluzioni**, eliminare il controllo del progetto predefinita eliminando il file di origine denominato "UserControl1.cs" o "UserControl1", a seconda del linguaggio che preferisci.</span><span class="sxs-lookup"><span data-stu-id="ce467-121">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>  
  
     <span data-ttu-id="ce467-122">Per altre informazioni, vedere [Procedura: Rimuovere, eliminare ed escludere elementi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ce467-122">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="ce467-123">Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> di elemento per il **StackViewLibrary** progetto.</span><span class="sxs-lookup"><span data-stu-id="ce467-123">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="ce467-124">Assegnare al nuovo file di origine il nome di base `StackView`.</span><span class="sxs-lookup"><span data-stu-id="ce467-124">Give the new source file a base name of `StackView`.</span></span>  
  
## <a name="designing-the-stackview-control"></a><span data-ttu-id="ce467-125">Progettazione del controllo StackView</span><span class="sxs-lookup"><span data-stu-id="ce467-125">Designing the StackView Control</span></span>  
 <span data-ttu-id="ce467-126">Il `StackView` è un controllo composito con un elemento figlio <xref:System.Windows.Forms.ToolStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="ce467-126">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="ce467-127">Per altre informazioni sui controlli compositi, vedere [tipi di controlli personalizzati](varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ce467-127">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>  
  
#### <a name="to-design-the-stackview-control"></a><span data-ttu-id="ce467-128">Per progettare il controllo StackView</span><span class="sxs-lookup"><span data-stu-id="ce467-128">To design the StackView control</span></span>  
  
1. <span data-ttu-id="ce467-129">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.ToolStrip> controllo all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ce467-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>  
  
2. <span data-ttu-id="ce467-130">Nel **delle proprietà** impostare nella finestra Proprietà la <xref:System.Windows.Forms.ToolStrip> proprietà del controllo in base alla tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="ce467-130">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="ce467-131">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ce467-131">Property</span></span>|<span data-ttu-id="ce467-132">Value</span><span class="sxs-lookup"><span data-stu-id="ce467-132">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="ce467-133">Nome</span><span class="sxs-lookup"><span data-stu-id="ce467-133">Name</span></span>|`stackStrip`|  
    |<span data-ttu-id="ce467-134">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="ce467-134">CanOverflow</span></span>|`false`|  
    |<span data-ttu-id="ce467-135">Dock</span><span class="sxs-lookup"><span data-stu-id="ce467-135">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |<span data-ttu-id="ce467-136">Carattere</span><span class="sxs-lookup"><span data-stu-id="ce467-136">Font</span></span>|`Tahoma, 10pt, style=Bold`|  
    |<span data-ttu-id="ce467-137">GripStyle</span><span class="sxs-lookup"><span data-stu-id="ce467-137">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |<span data-ttu-id="ce467-138">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="ce467-138">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |<span data-ttu-id="ce467-139">Spaziatura interna</span><span class="sxs-lookup"><span data-stu-id="ce467-139">Padding</span></span>|`0, 7, 0, 0`|  
    |<span data-ttu-id="ce467-140">RenderMode</span><span class="sxs-lookup"><span data-stu-id="ce467-140">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3. <span data-ttu-id="ce467-141">Nella finestra di progettazione Windows Form, fare clic sui <xref:System.Windows.Forms.ToolStrip> del controllo **Add** pulsante e aggiungere un <xref:System.Windows.Forms.ToolStripButton> per il `stackStrip` controllo.</span><span class="sxs-lookup"><span data-stu-id="ce467-141">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>  
  
4. <span data-ttu-id="ce467-142">Nel **delle proprietà** impostare nella finestra Proprietà la <xref:System.Windows.Forms.ToolStripButton> proprietà del controllo in base alla tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="ce467-142">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="ce467-143">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ce467-143">Property</span></span>|<span data-ttu-id="ce467-144">Value</span><span class="sxs-lookup"><span data-stu-id="ce467-144">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="ce467-145">Nome</span><span class="sxs-lookup"><span data-stu-id="ce467-145">Name</span></span>|`mailStackButton`|  
    |<span data-ttu-id="ce467-146">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="ce467-146">CheckOnClick</span></span>|<span data-ttu-id="ce467-147">true</span><span class="sxs-lookup"><span data-stu-id="ce467-147">true</span></span>|  
    |<span data-ttu-id="ce467-148">Oggetto CheckState</span><span class="sxs-lookup"><span data-stu-id="ce467-148">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|  
    |<span data-ttu-id="ce467-149">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="ce467-149">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |<span data-ttu-id="ce467-150">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="ce467-150">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |<span data-ttu-id="ce467-151">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="ce467-151">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |<span data-ttu-id="ce467-152">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="ce467-152">ImageTransparentColor</span></span>|`238, 238, 238`|  
    |<span data-ttu-id="ce467-153">Margini</span><span class="sxs-lookup"><span data-stu-id="ce467-153">Margin</span></span>|`0, 0, 0, 0`|  
    |<span data-ttu-id="ce467-154">Spaziatura interna</span><span class="sxs-lookup"><span data-stu-id="ce467-154">Padding</span></span>|`3, 3, 3, 3`|  
    |<span data-ttu-id="ce467-155">Testo</span><span class="sxs-lookup"><span data-stu-id="ce467-155">Text</span></span>|<span data-ttu-id="ce467-156">**Posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="ce467-156">**Mail**</span></span>|  
    |<span data-ttu-id="ce467-157">TextAlign</span><span class="sxs-lookup"><span data-stu-id="ce467-157">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5. <span data-ttu-id="ce467-158">Ripetere il passaggio 7 per altri tre <xref:System.Windows.Forms.ToolStripButton> controlli.</span><span class="sxs-lookup"><span data-stu-id="ce467-158">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
     <span data-ttu-id="ce467-159">Denominare i controlli `calendarStackButton`, `contactsStackButton`, e `tasksStackButton`.</span><span class="sxs-lookup"><span data-stu-id="ce467-159">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="ce467-160">Impostare il valore della <xref:System.Windows.Forms.Control.Text%2A> proprietà **calendario**, **contatti**, e **attività**, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="ce467-160">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>  
  
## <a name="handling-events"></a><span data-ttu-id="ce467-161">Gestione degli eventi</span><span class="sxs-lookup"><span data-stu-id="ce467-161">Handling Events</span></span>  
 <span data-ttu-id="ce467-162">Due eventi sono importanti per rendere il `StackView` controllo funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="ce467-162">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="ce467-163">Gestire il <xref:System.Windows.Forms.UserControl.Load> posizionare correttamente il controllo dell'evento.</span><span class="sxs-lookup"><span data-stu-id="ce467-163">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="ce467-164">Gestire il <xref:System.Windows.Forms.ToolStripItem.Click> evento per ogni <xref:System.Windows.Forms.ToolStripButton> per concedere il `StackView` controllano il comportamento di stato simile al <xref:System.Windows.Forms.RadioButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="ce467-164">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>  
  
#### <a name="to-handle-events"></a><span data-ttu-id="ce467-165">Per gestire gli eventi</span><span class="sxs-lookup"><span data-stu-id="ce467-165">To handle events</span></span>  
  
1. <span data-ttu-id="ce467-166">Nella finestra di progettazione Windows Form, selezionare il `StackView` controllo.</span><span class="sxs-lookup"><span data-stu-id="ce467-166">In the Windows Forms Designer, select the `StackView` control.</span></span>  
  
2. <span data-ttu-id="ce467-167">Nella finestra **Proprietà** fare clic su **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="ce467-167">In the **Properties** window, click **Events**.</span></span>  
  
3. <span data-ttu-id="ce467-168">Fare doppio clic per generare l'evento di caricamento di `StackView_Load` gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="ce467-168">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>  
  
4. <span data-ttu-id="ce467-169">Nel gestore di eventi `StackView_Load` copiare e incollare il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ce467-169">In the `StackView_Load` event handler, copy and paste the following code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5. <span data-ttu-id="ce467-170">Nella finestra di progettazione Windows Form, selezionare il `mailStackButton` controllo.</span><span class="sxs-lookup"><span data-stu-id="ce467-170">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>  
  
6. <span data-ttu-id="ce467-171">Nella finestra **Proprietà** fare clic su **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="ce467-171">In the **Properties** window, click **Events**.</span></span>  
  
7. <span data-ttu-id="ce467-172">Fare doppio clic dell'evento Click.</span><span class="sxs-lookup"><span data-stu-id="ce467-172">Double-click the Click event.</span></span>  
  
     <span data-ttu-id="ce467-173">Finestra di progettazione Windows Form genera il `mailStackButton_Click` gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="ce467-173">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>  
  
8. <span data-ttu-id="ce467-174">Rinominare il `mailStackButton_Click` gestore dell'evento a `stackButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="ce467-174">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>  
  
     <span data-ttu-id="ce467-175">Per altre informazioni, vedere [rinominare un simbolo di codice e refactoring](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="ce467-175">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>  
  
9. <span data-ttu-id="ce467-176">Inserire il codice seguente nel `stackButton_Click` gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="ce467-176">Insert the following code into the `stackButton_Click` event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. <span data-ttu-id="ce467-177">Nella finestra di progettazione Windows Form, selezionare il `calendarStackButton` controllo.</span><span class="sxs-lookup"><span data-stu-id="ce467-177">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>  
  
11. <span data-ttu-id="ce467-178">Nel **delle proprietà** finestra, impostare l'evento Click il `stackButton_Click` gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="ce467-178">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>  
  
12. <span data-ttu-id="ce467-179">Ripetere i passaggi 10 e 11 per il `contactsStackButton` e `tasksStackButton` controlli.</span><span class="sxs-lookup"><span data-stu-id="ce467-179">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>  
  
## <a name="defining-icons"></a><span data-ttu-id="ce467-180">Definizione delle icone</span><span class="sxs-lookup"><span data-stu-id="ce467-180">Defining Icons</span></span>  
 <span data-ttu-id="ce467-181">Ogni `StackView` pulsante è associata un'icona.</span><span class="sxs-lookup"><span data-stu-id="ce467-181">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="ce467-182">Per praticità, ogni icona è rappresentato come stringa con codifica Base64, che viene deserializzato prima un <xref:System.Drawing.Bitmap> viene creato da quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="ce467-182">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="ce467-183">In un ambiente di produzione, si archiviano i dati di bitmap come una risorsa e le icone vengono visualizzate nella finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ce467-183">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="ce467-184">Per altre informazioni, vedere [Procedura: Aggiungere le immagini di sfondo a un Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ce467-184">For more information, see [How to: Add Background Images to Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>  
  
#### <a name="to-define-icons"></a><span data-ttu-id="ce467-185">Per definire le icone</span><span class="sxs-lookup"><span data-stu-id="ce467-185">To define icons</span></span>  
  
1. <span data-ttu-id="ce467-186">Nell'Editor di codice, inserire il codice seguente nel `StackView` definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="ce467-186">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="ce467-187">Questo codice inizializza le bitmap di <xref:System.Windows.Forms.ToolStripButton> icone.</span><span class="sxs-lookup"><span data-stu-id="ce467-187">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2. <span data-ttu-id="ce467-188">Aggiungere una chiamata ai `InitializeImages` nel metodo il `StackView` costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="ce467-188">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a><span data-ttu-id="ce467-189">Implementazione di un Renderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="ce467-189">Implementing a Custom Renderer</span></span>  
 <span data-ttu-id="ce467-190">È possibile personalizzare la maggior parte degli elementi del `StackView` controllare l'implementazione di una classe che deriva dal <xref:System.Windows.Forms.ToolStripRenderer> classe.</span><span class="sxs-lookup"><span data-stu-id="ce467-190">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="ce467-191">In questa procedura, si implementerà un <xref:System.Windows.Forms.ToolStripProfessionalRenderer> classe che consente di personalizzare il riquadro e disegna gli sfondi sfumatura per il <xref:System.Windows.Forms.ToolStripButton> controlli.</span><span class="sxs-lookup"><span data-stu-id="ce467-191">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
#### <a name="to-implement-a-custom-renderer"></a><span data-ttu-id="ce467-192">Per implementare un renderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="ce467-192">To implement a custom renderer</span></span>  
  
1. <span data-ttu-id="ce467-193">Inserire il codice seguente nel `StackView` controllare la definizione.</span><span class="sxs-lookup"><span data-stu-id="ce467-193">Insert the following code into the `StackView` control definition.</span></span>  
  
     <span data-ttu-id="ce467-194">Si tratta della definizione per il `StackRenderer` classe, che esegue l'override di <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, e <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> metodi per produrre un aspetto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ce467-194">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2. <span data-ttu-id="ce467-195">Nel `StackView` costruttore del controllo, creare una nuova istanza della `StackRenderer` classe e assegnare questa istanza con la `stackStrip` del controllo <xref:System.Windows.Forms.ToolStrip.Renderer%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ce467-195">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a><span data-ttu-id="ce467-196">Test del controllo StackView</span><span class="sxs-lookup"><span data-stu-id="ce467-196">Testing the StackView Control</span></span>  
 <span data-ttu-id="ce467-197">Il `StackView` controllo deriva dal <xref:System.Windows.Forms.UserControl> classe.</span><span class="sxs-lookup"><span data-stu-id="ce467-197">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="ce467-198">Pertanto, è possibile testare il controllo con il **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="ce467-198">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="ce467-199">Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="ce467-199">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-the-stackview-control"></a><span data-ttu-id="ce467-200">Per testare il controllo StackView</span><span class="sxs-lookup"><span data-stu-id="ce467-200">To test the StackView control</span></span>  
  
1. <span data-ttu-id="ce467-201">Premere F5 per compilare il progetto e avviare il **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="ce467-201">Press F5 to build the project and start the **UserControl Test Container**.</span></span>  
  
2. <span data-ttu-id="ce467-202">Spostare il puntatore del mouse sui pulsanti del `StackView` controllare e quindi fare clic su un pulsante per visualizzare l'aspetto del relativo stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="ce467-202">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ce467-203">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ce467-203">Next Steps</span></span>  
 <span data-ttu-id="ce467-204">In questa procedura dettagliata, è stato creato un controllo riutilizzabile client personalizzata con l'aspetto di un controllo di Office XP professional.</span><span class="sxs-lookup"><span data-stu-id="ce467-204">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="ce467-205">È possibile usare il <xref:System.Windows.Forms.ToolStrip> della famiglia di controlli per molte altre operazioni:</span><span class="sxs-lookup"><span data-stu-id="ce467-205">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="ce467-206">Creare i menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="ce467-206">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="ce467-207">Per altre informazioni, vedere [Cenni preliminari sul componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ce467-207">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="ce467-208">Creare un form con un menu standard popolato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ce467-208">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="ce467-209">Per altre informazioni, vedere [Procedura dettagliata: Inserimento di voci di Menu Standard in un Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="ce467-209">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="ce467-210">Creare un form MDI (interfaccia) mediante l'ancoraggio <xref:System.Windows.Forms.ToolStrip> controlli.</span><span class="sxs-lookup"><span data-stu-id="ce467-210">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="ce467-211">Per altre informazioni, vedere [Procedura: Creare un Form MDI con unione di Menu e controlli ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ce467-211">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce467-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce467-212">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="ce467-213">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ce467-213">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="ce467-214">Procedura: Specificare voci di Menu Standard in un Form</span><span class="sxs-lookup"><span data-stu-id="ce467-214">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
