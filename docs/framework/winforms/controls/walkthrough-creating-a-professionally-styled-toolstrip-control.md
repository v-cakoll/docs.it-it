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
ms.openlocfilehash: 226e805d0240236899ee0cc290f1060a3b0aa391
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211762"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="f6abd-102">Procedura dettagliata: Creazione di un controllo ToolStrip professionale</span><span class="sxs-lookup"><span data-stu-id="f6abd-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>

<span data-ttu-id="f6abd-103">È possibile assegnare l'applicazione <xref:System.Windows.Forms.ToolStrip> controlla un aspetto professionale scrivendo una classe personalizzata derivata dal <xref:System.Windows.Forms.ToolStripProfessionalRenderer> tipo.</span><span class="sxs-lookup"><span data-stu-id="f6abd-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>

<span data-ttu-id="f6abd-104">Questa procedura dettagliata illustra come usare <xref:System.Windows.Forms.ToolStrip> controlli per creare un controllo composito che è simile al **riquadro di spostamento** fornito da Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="f6abd-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="f6abd-105">Nella procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6abd-105">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="f6abd-106">Creazione di un progetto libreria di controlli Windows.</span><span class="sxs-lookup"><span data-stu-id="f6abd-106">Creating a Windows Control Library project.</span></span>

- <span data-ttu-id="f6abd-107">Progettazione del controllo StackView.</span><span class="sxs-lookup"><span data-stu-id="f6abd-107">Designing the StackView Control.</span></span>

- <span data-ttu-id="f6abd-108">Implementazione di un Renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f6abd-108">Implementing a Custom Renderer.</span></span>

<span data-ttu-id="f6abd-109">Al termine, sarà necessario un controllo riutilizzabile client personalizzata con l'aspetto di un controllo di Microsoft Office® XP professional.</span><span class="sxs-lookup"><span data-stu-id="f6abd-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>

<span data-ttu-id="f6abd-110">Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Creare un controllo ToolStrip professionale](how-to-create-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="f6abd-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6abd-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f6abd-111">Prerequisites</span></span>

<span data-ttu-id="f6abd-112">È necessario Visual Studio per completare questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="f6abd-112">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="f6abd-113">Creare il progetto di libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="f6abd-113">Create the control library project</span></span>

1. <span data-ttu-id="f6abd-114">In Visual Studio, creare un nuovo progetto di libreria di controlli di Windows denominato `StackViewLibrary`.</span><span class="sxs-lookup"><span data-stu-id="f6abd-114">In Visual Studio, create a new Windows Control Library project named `StackViewLibrary`.</span></span>

2. <span data-ttu-id="f6abd-115">Nelle **Esplora soluzioni**, eliminare il controllo del progetto predefinita eliminando il file di origine denominato "UserControl1.cs" o "UserControl1", a seconda del linguaggio che preferisci.</span><span class="sxs-lookup"><span data-stu-id="f6abd-115">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

     <span data-ttu-id="f6abd-116">Per altre informazioni, vedere [Procedura: Rimuovere, eliminare ed escludere elementi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f6abd-116">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="f6abd-117">Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> di elemento per il **StackViewLibrary** progetto.</span><span class="sxs-lookup"><span data-stu-id="f6abd-117">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="f6abd-118">Assegnare al nuovo file di origine il nome di base `StackView`.</span><span class="sxs-lookup"><span data-stu-id="f6abd-118">Give the new source file a base name of `StackView`.</span></span>

## <a name="design-the-stackview-control"></a><span data-ttu-id="f6abd-119">Progettare il controllo StackView</span><span class="sxs-lookup"><span data-stu-id="f6abd-119">Design the StackView control</span></span>

<span data-ttu-id="f6abd-120">Il `StackView` è un controllo composito con un elemento figlio <xref:System.Windows.Forms.ToolStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="f6abd-120">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="f6abd-121">Per altre informazioni sui controlli compositi, vedere [tipi di controlli personalizzati](varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f6abd-121">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

1. <span data-ttu-id="f6abd-122">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.ToolStrip> controllo all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f6abd-122">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>

2. <span data-ttu-id="f6abd-123">Nel **delle proprietà** impostare nella finestra Proprietà la <xref:System.Windows.Forms.ToolStrip> proprietà del controllo in base alla tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="f6abd-123">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>

    |<span data-ttu-id="f6abd-124">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f6abd-124">Property</span></span>|<span data-ttu-id="f6abd-125">Value</span><span class="sxs-lookup"><span data-stu-id="f6abd-125">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="f6abd-126">Nome</span><span class="sxs-lookup"><span data-stu-id="f6abd-126">Name</span></span>|`stackStrip`|
    |<span data-ttu-id="f6abd-127">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="f6abd-127">CanOverflow</span></span>|`false`|
    |<span data-ttu-id="f6abd-128">Dock</span><span class="sxs-lookup"><span data-stu-id="f6abd-128">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |<span data-ttu-id="f6abd-129">Carattere</span><span class="sxs-lookup"><span data-stu-id="f6abd-129">Font</span></span>|`Tahoma, 10pt, style=Bold`|
    |<span data-ttu-id="f6abd-130">GripStyle</span><span class="sxs-lookup"><span data-stu-id="f6abd-130">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |<span data-ttu-id="f6abd-131">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="f6abd-131">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |<span data-ttu-id="f6abd-132">Spaziatura interna</span><span class="sxs-lookup"><span data-stu-id="f6abd-132">Padding</span></span>|`0, 7, 0, 0`|
    |<span data-ttu-id="f6abd-133">RenderMode</span><span class="sxs-lookup"><span data-stu-id="f6abd-133">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. <span data-ttu-id="f6abd-134">Nella finestra di progettazione Windows Form, fare clic sui <xref:System.Windows.Forms.ToolStrip> del controllo **Add** pulsante e aggiungere un <xref:System.Windows.Forms.ToolStripButton> per il `stackStrip` controllo.</span><span class="sxs-lookup"><span data-stu-id="f6abd-134">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>

4. <span data-ttu-id="f6abd-135">Nel **delle proprietà** impostare nella finestra Proprietà la <xref:System.Windows.Forms.ToolStripButton> proprietà del controllo in base alla tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="f6abd-135">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>

    |<span data-ttu-id="f6abd-136">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f6abd-136">Property</span></span>|<span data-ttu-id="f6abd-137">Value</span><span class="sxs-lookup"><span data-stu-id="f6abd-137">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="f6abd-138">Nome</span><span class="sxs-lookup"><span data-stu-id="f6abd-138">Name</span></span>|`mailStackButton`|
    |<span data-ttu-id="f6abd-139">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="f6abd-139">CheckOnClick</span></span>|<span data-ttu-id="f6abd-140">true</span><span class="sxs-lookup"><span data-stu-id="f6abd-140">true</span></span>|
    |<span data-ttu-id="f6abd-141">Oggetto CheckState</span><span class="sxs-lookup"><span data-stu-id="f6abd-141">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|
    |<span data-ttu-id="f6abd-142">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="f6abd-142">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |<span data-ttu-id="f6abd-143">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="f6abd-143">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |<span data-ttu-id="f6abd-144">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="f6abd-144">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |<span data-ttu-id="f6abd-145">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="f6abd-145">ImageTransparentColor</span></span>|`238, 238, 238`|
    |<span data-ttu-id="f6abd-146">Margini</span><span class="sxs-lookup"><span data-stu-id="f6abd-146">Margin</span></span>|`0, 0, 0, 0`|
    |<span data-ttu-id="f6abd-147">Spaziatura interna</span><span class="sxs-lookup"><span data-stu-id="f6abd-147">Padding</span></span>|`3, 3, 3, 3`|
    |<span data-ttu-id="f6abd-148">Testo</span><span class="sxs-lookup"><span data-stu-id="f6abd-148">Text</span></span>|<span data-ttu-id="f6abd-149">**Posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="f6abd-149">**Mail**</span></span>|
    |<span data-ttu-id="f6abd-150">TextAlign</span><span class="sxs-lookup"><span data-stu-id="f6abd-150">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. <span data-ttu-id="f6abd-151">Ripetere il passaggio 7 per altri tre <xref:System.Windows.Forms.ToolStripButton> controlli.</span><span class="sxs-lookup"><span data-stu-id="f6abd-151">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

     <span data-ttu-id="f6abd-152">Denominare i controlli `calendarStackButton`, `contactsStackButton`, e `tasksStackButton`.</span><span class="sxs-lookup"><span data-stu-id="f6abd-152">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="f6abd-153">Impostare il valore della <xref:System.Windows.Forms.Control.Text%2A> proprietà **calendario**, **contatti**, e **attività**, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="f6abd-153">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>

## <a name="handle-events"></a><span data-ttu-id="f6abd-154">Gestione degli eventi</span><span class="sxs-lookup"><span data-stu-id="f6abd-154">Handle events</span></span>

<span data-ttu-id="f6abd-155">Due eventi sono importanti per rendere il `StackView` controllo funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="f6abd-155">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="f6abd-156">Gestire il <xref:System.Windows.Forms.UserControl.Load> posizionare correttamente il controllo dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f6abd-156">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="f6abd-157">Gestire il <xref:System.Windows.Forms.ToolStripItem.Click> evento per ogni <xref:System.Windows.Forms.ToolStripButton> per concedere il `StackView` controllano il comportamento di stato simile al <xref:System.Windows.Forms.RadioButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="f6abd-157">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>

1. <span data-ttu-id="f6abd-158">Nella finestra di progettazione Windows Form, selezionare il `StackView` controllo.</span><span class="sxs-lookup"><span data-stu-id="f6abd-158">In the Windows Forms Designer, select the `StackView` control.</span></span>

2. <span data-ttu-id="f6abd-159">Nella finestra **Proprietà** fare clic su **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="f6abd-159">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="f6abd-160">Fare doppio clic per generare l'evento di caricamento di `StackView_Load` gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f6abd-160">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>

4. <span data-ttu-id="f6abd-161">Nel gestore di eventi `StackView_Load` copiare e incollare il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f6abd-161">In the `StackView_Load` event handler, copy and paste the following code.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. <span data-ttu-id="f6abd-162">Nella finestra di progettazione Windows Form, selezionare il `mailStackButton` controllo.</span><span class="sxs-lookup"><span data-stu-id="f6abd-162">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>

6. <span data-ttu-id="f6abd-163">Nella finestra **Proprietà** fare clic su **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="f6abd-163">In the **Properties** window, click **Events**.</span></span>

7. <span data-ttu-id="f6abd-164">Fare doppio clic dell'evento Click.</span><span class="sxs-lookup"><span data-stu-id="f6abd-164">Double-click the Click event.</span></span>

     <span data-ttu-id="f6abd-165">Finestra di progettazione Windows Form genera il `mailStackButton_Click` gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f6abd-165">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>

8. <span data-ttu-id="f6abd-166">Rinominare il `mailStackButton_Click` gestore dell'evento a `stackButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="f6abd-166">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>

     <span data-ttu-id="f6abd-167">Per altre informazioni, vedere [rinominare un simbolo di codice e refactoring](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="f6abd-167">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

9. <span data-ttu-id="f6abd-168">Inserire il codice seguente nel `stackButton_Click` gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f6abd-168">Insert the following code into the `stackButton_Click` event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. <span data-ttu-id="f6abd-169">Nella finestra di progettazione Windows Form, selezionare il `calendarStackButton` controllo.</span><span class="sxs-lookup"><span data-stu-id="f6abd-169">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>

11. <span data-ttu-id="f6abd-170">Nel **delle proprietà** finestra, impostare l'evento Click il `stackButton_Click` gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f6abd-170">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>

12. <span data-ttu-id="f6abd-171">Ripetere i passaggi 10 e 11 per il `contactsStackButton` e `tasksStackButton` controlli.</span><span class="sxs-lookup"><span data-stu-id="f6abd-171">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>

## <a name="define-icons"></a><span data-ttu-id="f6abd-172">Definire le icone</span><span class="sxs-lookup"><span data-stu-id="f6abd-172">Define icons</span></span>

<span data-ttu-id="f6abd-173">Ogni `StackView` pulsante è associata un'icona.</span><span class="sxs-lookup"><span data-stu-id="f6abd-173">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="f6abd-174">Per praticità, ogni icona è rappresentato come stringa con codifica Base64, che viene deserializzato prima un <xref:System.Drawing.Bitmap> viene creato da quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="f6abd-174">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="f6abd-175">In un ambiente di produzione, si archiviano i dati di bitmap come una risorsa e le icone vengono visualizzate nella finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f6abd-175">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="f6abd-176">Per altre informazioni, vedere [Procedura: Aggiungere le immagini di sfondo a un Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f6abd-176">For more information, see [How to: Add Background Images to Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>

1. <span data-ttu-id="f6abd-177">Nell'Editor di codice, inserire il codice seguente nel `StackView` definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="f6abd-177">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="f6abd-178">Questo codice inizializza le bitmap di <xref:System.Windows.Forms.ToolStripButton> icone.</span><span class="sxs-lookup"><span data-stu-id="f6abd-178">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. <span data-ttu-id="f6abd-179">Aggiungere una chiamata ai `InitializeImages` nel metodo il `StackView` costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="f6abd-179">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a><span data-ttu-id="f6abd-180">Implementare un renderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="f6abd-180">Implement a custom renderer</span></span>

<span data-ttu-id="f6abd-181">È possibile personalizzare la maggior parte degli elementi del `StackView` controllare l'implementazione di una classe che deriva dal <xref:System.Windows.Forms.ToolStripRenderer> classe.</span><span class="sxs-lookup"><span data-stu-id="f6abd-181">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="f6abd-182">In questa procedura, si implementerà un <xref:System.Windows.Forms.ToolStripProfessionalRenderer> classe che consente di personalizzare il riquadro e disegna gli sfondi sfumatura per il <xref:System.Windows.Forms.ToolStripButton> controlli.</span><span class="sxs-lookup"><span data-stu-id="f6abd-182">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

1. <span data-ttu-id="f6abd-183">Inserire il codice seguente nel `StackView` controllare la definizione.</span><span class="sxs-lookup"><span data-stu-id="f6abd-183">Insert the following code into the `StackView` control definition.</span></span>

     <span data-ttu-id="f6abd-184">Si tratta della definizione per il `StackRenderer` classe, che esegue l'override di <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, e <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> metodi per produrre un aspetto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f6abd-184">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. <span data-ttu-id="f6abd-185">Nel `StackView` costruttore del controllo, creare una nuova istanza della `StackRenderer` classe e assegnare questa istanza con la `stackStrip` del controllo <xref:System.Windows.Forms.ToolStrip.Renderer%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f6abd-185">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a><span data-ttu-id="f6abd-186">Testare il controllo StackView</span><span class="sxs-lookup"><span data-stu-id="f6abd-186">Test the StackView control</span></span>

<span data-ttu-id="f6abd-187">Il `StackView` controllo deriva dal <xref:System.Windows.Forms.UserControl> classe.</span><span class="sxs-lookup"><span data-stu-id="f6abd-187">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="f6abd-188">Pertanto, è possibile testare il controllo con il **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="f6abd-188">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="f6abd-189">Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="f6abd-189">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

1. <span data-ttu-id="f6abd-190">Premere **F5** per compilare il progetto e avviare la **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="f6abd-190">Press **F5** to build the project and start the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="f6abd-191">Spostare il puntatore del mouse sui pulsanti del `StackView` controllare e quindi fare clic su un pulsante per visualizzare l'aspetto del relativo stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="f6abd-191">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6abd-192">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f6abd-192">Next steps</span></span>

<span data-ttu-id="f6abd-193">In questa procedura dettagliata, è stato creato un controllo riutilizzabile client personalizzata con l'aspetto di un controllo di Office XP professional.</span><span class="sxs-lookup"><span data-stu-id="f6abd-193">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="f6abd-194">È possibile usare il <xref:System.Windows.Forms.ToolStrip> della famiglia di controlli per molte altre operazioni:</span><span class="sxs-lookup"><span data-stu-id="f6abd-194">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="f6abd-195">Creare i menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="f6abd-195">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="f6abd-196">Per altre informazioni, vedere [Cenni preliminari sul componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f6abd-196">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="f6abd-197">Creare un form con un menu standard popolato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f6abd-197">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="f6abd-198">Per altre informazioni, vedere [Procedura dettagliata: Inserimento di voci di Menu Standard in un Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="f6abd-198">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="f6abd-199">Creare un form MDI (interfaccia) mediante l'ancoraggio <xref:System.Windows.Forms.ToolStrip> controlli.</span><span class="sxs-lookup"><span data-stu-id="f6abd-199">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="f6abd-200">Per altre informazioni, vedere [Procedura: Creare un Form MDI con unione di Menu e controlli ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f6abd-200">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6abd-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6abd-201">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="f6abd-202">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="f6abd-202">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="f6abd-203">Procedura: Specificare voci di Menu Standard in un Form</span><span class="sxs-lookup"><span data-stu-id="f6abd-203">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
