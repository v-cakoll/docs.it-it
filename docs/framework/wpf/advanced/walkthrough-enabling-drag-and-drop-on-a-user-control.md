---
title: 'Procedura dettagliata: Abilitare il trascinamento della selezione in un controllo utente'
description: Informazioni su come creare un controllo utente personalizzato che possa partecipare al trasferimento dei dati con trascinamento della selezione in Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 12ad47035a09995094014841b083062743fc2574
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168281"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="f4793-103">Procedura dettagliata: Abilitare il trascinamento della selezione in un controllo utente</span><span class="sxs-lookup"><span data-stu-id="f4793-103">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="f4793-104">Questa procedura dettagliata illustra come creare un controllo utente personalizzato che possa partecipare al trasferimento di dati tramite trascinamento in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4793-104">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="f4793-105">In questa procedura dettagliata verrà creato un oggetto WPF personalizzato <xref:System.Windows.Controls.UserControl> che rappresenta una forma circolare.</span><span class="sxs-lookup"><span data-stu-id="f4793-105">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="f4793-106">Si implementeranno funzionalità nel controllo per consentire il trasferimento di dati tramite trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f4793-106">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="f4793-107">Ad esempio, se si trascina da un controllo Circle a un altro, i dati del colore di riempimento vengono copiati dal controllo Circle di origine a quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f4793-107">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="f4793-108">Se si trascina da un controllo Circle a un oggetto <xref:System.Windows.Controls.TextBox> , la rappresentazione di stringa del colore di riempimento viene copiata in <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-108">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f4793-109">Si creerà anche una piccola applicazione che contiene due controlli Panel e un oggetto <xref:System.Windows.Controls.TextBox> per testare la funzionalità di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="f4793-109">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="f4793-110">Si scriverà codice che consente ai pannelli di elaborare i dati Circle rilasciati per permettere di spostare o copiare cerchi dalla raccolta Children di un pannello all'altro.</span><span class="sxs-lookup"><span data-stu-id="f4793-110">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="f4793-111">Vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4793-111">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="f4793-112">Creare un controllo utente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f4793-112">Create a custom user control.</span></span>

- <span data-ttu-id="f4793-113">Consentire al controllo utente di essere un'origine di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f4793-113">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="f4793-114">Consentire al controllo utente di essere un obiettivo di rilascio.</span><span class="sxs-lookup"><span data-stu-id="f4793-114">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="f4793-115">Consentire a un pannello di ricevere dati rilasciati dal controllo utente.</span><span class="sxs-lookup"><span data-stu-id="f4793-115">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4793-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f4793-116">Prerequisites</span></span>

<span data-ttu-id="f4793-117">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f4793-117">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="f4793-118">Creare il progetto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="f4793-118">Create the Application Project</span></span>
 <span data-ttu-id="f4793-119">In questa sezione verrà creata l'infrastruttura dell'applicazione, che include una pagina principale con due pannelli e un oggetto <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="f4793-120">Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="f4793-120">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="f4793-121">Per altre informazioni, vedere [Procedura dettagliata: La prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="f4793-121">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="f4793-122">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4793-122">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="f4793-123">Aggiungere il markup seguente tra i tag di apertura e di chiusura <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="f4793-123">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="f4793-124">Questo markup crea l'interfaccia utente per l'applicazione di prova.</span><span class="sxs-lookup"><span data-stu-id="f4793-124">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="f4793-125">Aggiungere un nuovo controllo utente al progetto</span><span class="sxs-lookup"><span data-stu-id="f4793-125">Add a New User Control to the Project</span></span>
 <span data-ttu-id="f4793-126">In questa sezione si aggiungerà un nuovo controllo utente al progetto.</span><span class="sxs-lookup"><span data-stu-id="f4793-126">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="f4793-127">Scegliere **Aggiungi controllo utente** dal menu Progetto.</span><span class="sxs-lookup"><span data-stu-id="f4793-127">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="f4793-128">Nella finestra di dialogo **Aggiungi nuovo elemento** modificare il nome in `Circle.xaml` , quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f4793-128">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="f4793-129">Circle.xaml e il relativo code-behind vengono aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="f4793-129">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="f4793-130">Aprire Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4793-130">Open Circle.xaml.</span></span>

     <span data-ttu-id="f4793-131">Questo file conterrà gli elementi dell'interfaccia utente del controllo utente.</span><span class="sxs-lookup"><span data-stu-id="f4793-131">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="f4793-132">Aggiungere il markup seguente alla radice <xref:System.Windows.Controls.Grid> per creare un controllo utente semplice con un cerchio blu come interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="f4793-132">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="f4793-133">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f4793-133">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="f4793-134">In C# aggiungere il codice seguente dopo il costruttore senza parametri per creare un costruttore di copia.</span><span class="sxs-lookup"><span data-stu-id="f4793-134">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="f4793-135">In Visual Basic aggiungere il codice seguente per creare un costruttore senza parametri e un costruttore di copia.</span><span class="sxs-lookup"><span data-stu-id="f4793-135">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="f4793-136">Per consentire la copia del controllo utente, aggiungere un metodo di costruttore di copia nel file code-behind.</span><span class="sxs-lookup"><span data-stu-id="f4793-136">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="f4793-137">Nel controllo utente Circle semplificato si copieranno solo il riempimento e le dimensioni del controllo utente.</span><span class="sxs-lookup"><span data-stu-id="f4793-137">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="f4793-138">Aggiungere il controllo utente alla finestra principale</span><span class="sxs-lookup"><span data-stu-id="f4793-138">Add the user control to the main window</span></span>

1. <span data-ttu-id="f4793-139">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4793-139">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="f4793-140">Aggiungere il codice XAML seguente al <xref:System.Windows.Window> tag di apertura per creare un riferimento allo spazio dei nomi XML all'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="f4793-140">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="f4793-141">Nel primo <xref:System.Windows.Controls.StackPanel> , aggiungere il codice XAML seguente per creare due istanze del controllo utente Circle nel primo pannello.</span><span class="sxs-lookup"><span data-stu-id="f4793-141">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="f4793-142">Il codice XAML completo per il pannello è analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="f4793-142">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="f4793-143">Implementare gli eventi di origine del trascinamento nel controllo utente</span><span class="sxs-lookup"><span data-stu-id="f4793-143">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="f4793-144">In questa sezione verrà eseguito l'override del <xref:System.Windows.UIElement.OnMouseMove%2A> metodo e verrà avviata l'operazione di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="f4793-144">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="f4793-145">Se viene avviato un trascinamento (viene premuto un pulsante del mouse e il mouse viene spostato), i dati verranno inseriti in un pacchetto da trasferire in un oggetto <xref:System.Windows.DataObject> .</span><span class="sxs-lookup"><span data-stu-id="f4793-145">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="f4793-146">In questo caso, il controllo Circle assemblerà tre elementi di dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.</span><span class="sxs-lookup"><span data-stu-id="f4793-146">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="f4793-147">Per avviare un'operazione di riempimento</span><span class="sxs-lookup"><span data-stu-id="f4793-147">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="f4793-148">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f4793-148">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="f4793-149">Aggiungere la seguente <xref:System.Windows.UIElement.OnMouseMove%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.MouseMove> evento.</span><span class="sxs-lookup"><span data-stu-id="f4793-149">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="f4793-150">Questo <xref:System.Windows.UIElement.OnMouseMove%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4793-150">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f4793-151">Controlla se il pulsante sinistro del mouse viene premuto mentre il mouse è in movimento.</span><span class="sxs-lookup"><span data-stu-id="f4793-151">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="f4793-152">Inserisce i dati Circle in un oggetto <xref:System.Windows.DataObject> .</span><span class="sxs-lookup"><span data-stu-id="f4793-152">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="f4793-153">In questo caso, il controllo Circle assembla tre elementi dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.</span><span class="sxs-lookup"><span data-stu-id="f4793-153">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="f4793-154">Chiama il <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> metodo statico per avviare l'operazione di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="f4793-154">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="f4793-155">Passare i tre parametri seguenti al <xref:System.Windows.DragDrop.DoDragDrop%2A> Metodo:</span><span class="sxs-lookup"><span data-stu-id="f4793-155">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="f4793-156">`dragSource` - Un riferimento a questo controllo.</span><span class="sxs-lookup"><span data-stu-id="f4793-156">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="f4793-157">`data`: Oggetto <xref:System.Windows.DataObject> creato nel codice precedente.</span><span class="sxs-lookup"><span data-stu-id="f4793-157">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="f4793-158">`allowedEffects`: Le operazioni di trascinamento della selezione consentite, ovvero <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move> .</span><span class="sxs-lookup"><span data-stu-id="f4793-158">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="f4793-159">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f4793-159">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="f4793-160">Fare clic su uno dei controlli Circle e trascinarlo sui pannelli, sull'altro cerchio e su <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-160">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f4793-161">Quando si trascina su <xref:System.Windows.Controls.TextBox> , il cursore cambia per indicare uno spostamento.</span><span class="sxs-lookup"><span data-stu-id="f4793-161">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="f4793-162">Quando si trascina un cerchio sul controllo <xref:System.Windows.Controls.TextBox> , premere il tasto **CTRL** .</span><span class="sxs-lookup"><span data-stu-id="f4793-162">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="f4793-163">Notare come il cursore cambia aspetto per indicare una copia.</span><span class="sxs-lookup"><span data-stu-id="f4793-163">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="f4793-164">Trascinare e rilasciare un cerchio nell'oggetto <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-164">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f4793-165">La rappresentazione di stringa del colore di riempimento del cerchio viene aggiunta all'oggetto <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-165">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="f4793-166">![Rappresentazione del colore di riempimento del cerchio](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="f4793-166">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="f4793-167">Per impostazione predefinita, il cursore cambierà aspetto durante un'operazione di trascinamento per indicare l'effetto che avrà il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="f4793-167">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="f4793-168">È possibile personalizzare il feedback fornito all'utente gestendo l' <xref:System.Windows.UIElement.GiveFeedback> evento e impostando un cursore diverso.</span><span class="sxs-lookup"><span data-stu-id="f4793-168">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="f4793-169">Inviare commenti e suggerimenti all'utente</span><span class="sxs-lookup"><span data-stu-id="f4793-169">Give feedback to the user</span></span>

1. <span data-ttu-id="f4793-170">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f4793-170">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="f4793-171">Aggiungere la seguente <xref:System.Windows.UIElement.OnGiveFeedback%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.GiveFeedback> evento.</span><span class="sxs-lookup"><span data-stu-id="f4793-171">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="f4793-172">Questo <xref:System.Windows.UIElement.OnGiveFeedback%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4793-172">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f4793-173">Verifica i <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valori impostati nel gestore eventi dell'obiettivo di rilascio <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="f4793-173">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="f4793-174">Imposta un cursore personalizzato in base al <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="f4793-174">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="f4793-175">Il cursore ha lo scopo di fornire un feedback visivo all'utente sull'effetto che avrà il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="f4793-175">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="f4793-176">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f4793-176">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="f4793-177">Trascinare uno dei controlli Circle sui pannelli, sull'altro cerchio e sull'oggetto <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-177">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f4793-178">Si noti che i cursori sono ora i cursori personalizzati specificati nella <xref:System.Windows.UIElement.OnGiveFeedback%2A> sostituzione.</span><span class="sxs-lookup"><span data-stu-id="f4793-178">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="f4793-179">![Trascina selezione con cursori personalizzati](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="f4793-179">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="f4793-180">Selezionare il testo `green` da <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-180">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="f4793-181">Trascinare il testo `green` su un controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="f4793-181">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="f4793-182">Notare che vengono visualizzati i cursori predefiniti per indicare gli effetti dell'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f4793-182">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="f4793-183">Il cursore di feedback viene sempre impostato dall'origine di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f4793-183">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="f4793-184">Implementare eventi di destinazione di rilascio nel controllo utente</span><span class="sxs-lookup"><span data-stu-id="f4793-184">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="f4793-185">In questa sezione si specificherà che il controllo utente è un obiettivo di rilascio, si eseguirà l'override dei metodi che consentono al controllo utente di essere un obiettivo di rilascio e si elaboreranno i dati rilasciati sul controllo.</span><span class="sxs-lookup"><span data-stu-id="f4793-185">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="f4793-186">Per consentire al controllo utente di essere un obiettivo di rilascio</span><span class="sxs-lookup"><span data-stu-id="f4793-186">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="f4793-187">Aprire Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4793-187">Open Circle.xaml.</span></span>

2. <span data-ttu-id="f4793-188">Nel tag di apertura <xref:System.Windows.Controls.UserControl> aggiungere la <xref:System.Windows.UIElement.AllowDrop%2A> proprietà e impostarla su `true` .</span><span class="sxs-lookup"><span data-stu-id="f4793-188">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="f4793-189">Il <xref:System.Windows.UIElement.OnDrop%2A> metodo viene chiamato quando la <xref:System.Windows.UIElement.AllowDrop%2A> proprietà è impostata su `true` e i dati dell'origine di trascinamento vengono rilasciati sul controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="f4793-189">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="f4793-190">In questo metodo si elaboreranno i dati rilasciati e li si applicheranno al controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="f4793-190">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="f4793-191">Per elaborare i dati rilasciati</span><span class="sxs-lookup"><span data-stu-id="f4793-191">To process the dropped data</span></span>

1. <span data-ttu-id="f4793-192">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f4793-192">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="f4793-193">Aggiungere la seguente <xref:System.Windows.UIElement.OnDrop%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.Drop> evento.</span><span class="sxs-lookup"><span data-stu-id="f4793-193">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="f4793-194">Questo <xref:System.Windows.UIElement.OnDrop%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4793-194">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f4793-195">Usa il <xref:System.Windows.DataObject.GetDataPresent%2A> metodo per verificare se i dati trascinati contengono un oggetto String.</span><span class="sxs-lookup"><span data-stu-id="f4793-195">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="f4793-196">Usa il <xref:System.Windows.DataObject.GetData%2A> metodo per estrarre i dati di stringa, se presenti.</span><span class="sxs-lookup"><span data-stu-id="f4793-196">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="f4793-197">Usa un oggetto <xref:System.Windows.Media.BrushConverter> per tentare di convertire la stringa in un oggetto <xref:System.Windows.Media.Brush> .</span><span class="sxs-lookup"><span data-stu-id="f4793-197">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="f4793-198">Se la conversione ha esito positivo, applica il pennello all'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> dell'oggetto <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="f4793-198">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="f4793-199">Contrassegna l' <xref:System.Windows.UIElement.Drop> evento come gestito.</span><span class="sxs-lookup"><span data-stu-id="f4793-199">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="f4793-200">È necessario contrassegnare l'evento di trascinamento come gestito per segnalare agli altri elementi che ricevono l'evento che questo è stato gestito dal controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="f4793-200">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="f4793-201">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f4793-201">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="f4793-202">Selezionare il testo `green` in <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-202">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="f4793-203">Trascinare il testo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="f4793-203">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="f4793-204">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="f4793-204">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="f4793-205">![Converti stringa in pennello](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="f4793-205">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="f4793-206">Digitare il testo `green` in <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-206">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="f4793-207">Selezionare il testo `gre` in <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-207">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="f4793-208">Trascinarlo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="f4793-208">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="f4793-209">Notare che il cursore cambia aspetto per indicare che è consentito il trascinamento ma il colore del controllo Circle non cambia poiché `gre` non è un colore valido.</span><span class="sxs-lookup"><span data-stu-id="f4793-209">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="f4793-210">Trascinare dal controllo Circle verde e rilasciare sul controllo Circle blu.</span><span class="sxs-lookup"><span data-stu-id="f4793-210">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="f4793-211">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="f4793-211">The Circle changes from blue to green.</span></span> <span data-ttu-id="f4793-212">Si noti che il cursore viene visualizzato a seconda che il <xref:System.Windows.Controls.TextBox> o il cerchio sia l'origine del trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f4793-212">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="f4793-213">L'impostazione della <xref:System.Windows.UIElement.AllowDrop%2A> proprietà su `true` e l'elaborazione dei dati eliminati è tutto ciò che è necessario per consentire a un elemento di essere un obiettivo di rilascio.</span><span class="sxs-lookup"><span data-stu-id="f4793-213">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="f4793-214">Tuttavia, per offrire un'esperienza utente migliore, è necessario gestire anche gli <xref:System.Windows.UIElement.DragEnter> <xref:System.Windows.UIElement.DragLeave> eventi, e <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="f4793-214">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="f4793-215">In questi eventi, è possibile eseguire controlli e offrire feedback all'utente prima che i dati vengono rilasciati.</span><span class="sxs-lookup"><span data-stu-id="f4793-215">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="f4793-216">Quando i dati vengono rilasciati sul controllo utente Circle, il controllo deve notificare all'origine di trascinamento se può elaborare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="f4793-216">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="f4793-217">Se il controllo non è in grado di elaborare i dati, deve rifiutare il rilascio.</span><span class="sxs-lookup"><span data-stu-id="f4793-217">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="f4793-218">A tale scopo, si gestirà l' <xref:System.Windows.UIElement.DragOver> evento e si imposterà la <xref:System.Windows.DragEventArgs.Effects%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="f4793-218">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="f4793-219">Per verificare se il rilascio dei dati è consentito</span><span class="sxs-lookup"><span data-stu-id="f4793-219">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="f4793-220">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f4793-220">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="f4793-221">Aggiungere la seguente <xref:System.Windows.UIElement.OnDragOver%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.DragOver> evento.</span><span class="sxs-lookup"><span data-stu-id="f4793-221">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="f4793-222">Questo <xref:System.Windows.UIElement.OnDragOver%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4793-222">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f4793-223">Imposta la proprietà <xref:System.Windows.DragEventArgs.Effects%2A> su <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="f4793-223">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="f4793-224">Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se il controllo utente Circle può elaborare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="f4793-224">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="f4793-225">Se il controllo utente può elaborare i dati, imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà su <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move> .</span><span class="sxs-lookup"><span data-stu-id="f4793-225">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="f4793-226">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f4793-226">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="f4793-227">Selezionare il testo `gre` in <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-227">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="f4793-228">Trascinare il testo su un controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="f4793-228">Drag the text to a Circle control.</span></span> <span data-ttu-id="f4793-229">Notare che ora il cursore cambia aspetto per indicare che il trascinamento non è consentito poiché `gre` non è un colore valido.</span><span class="sxs-lookup"><span data-stu-id="f4793-229">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="f4793-230">È possibile migliorare ulteriormente l'esperienza utente applicando un'anteprima dell'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f4793-230">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="f4793-231">Per il controllo utente Circle, si eseguirà l'override dei <xref:System.Windows.UIElement.OnDragEnter%2A> <xref:System.Windows.UIElement.OnDragLeave%2A> metodi e.</span><span class="sxs-lookup"><span data-stu-id="f4793-231">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="f4793-232">Quando i dati vengono trascinati sul controllo, lo sfondo corrente <xref:System.Windows.Shapes.Shape.Fill%2A> viene salvato in una variabile segnaposto.</span><span class="sxs-lookup"><span data-stu-id="f4793-232">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="f4793-233">La stringa viene quindi convertita in un pennello e applicata all'oggetto <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del cerchio.</span><span class="sxs-lookup"><span data-stu-id="f4793-233">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="f4793-234">Se i dati vengono trascinati fuori dal cerchio senza essere eliminati, il <xref:System.Windows.Shapes.Shape.Fill%2A> valore originale viene nuovamente applicato al cerchio.</span><span class="sxs-lookup"><span data-stu-id="f4793-234">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="f4793-235">Per visualizzare in anteprima gli effetti dell'operazione di trascinamento</span><span class="sxs-lookup"><span data-stu-id="f4793-235">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="f4793-236">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f4793-236">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="f4793-237">Nella classe Circle dichiarare una <xref:System.Windows.Media.Brush> variabile privata denominata `_previousFill` e inizializzarla su `null` .</span><span class="sxs-lookup"><span data-stu-id="f4793-237">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="f4793-238">Aggiungere la seguente <xref:System.Windows.UIElement.OnDragEnter%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.DragEnter> evento.</span><span class="sxs-lookup"><span data-stu-id="f4793-238">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="f4793-239">Questo <xref:System.Windows.UIElement.OnDragEnter%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4793-239">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f4793-240">Salva la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà dell'oggetto <xref:System.Windows.Shapes.Ellipse> nella `_previousFill` variabile.</span><span class="sxs-lookup"><span data-stu-id="f4793-240">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="f4793-241">Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se i dati possono essere convertiti in un oggetto <xref:System.Windows.Media.Brush> .</span><span class="sxs-lookup"><span data-stu-id="f4793-241">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="f4793-242">Se i dati vengono convertiti in un oggetto valido <xref:System.Windows.Media.Brush> , lo applica a <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="f4793-242">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="f4793-243">Aggiungere la seguente <xref:System.Windows.UIElement.OnDragLeave%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.DragLeave> evento.</span><span class="sxs-lookup"><span data-stu-id="f4793-243">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="f4793-244">Questo <xref:System.Windows.UIElement.OnDragLeave%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4793-244">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f4793-245">Applica l'oggetto <xref:System.Windows.Media.Brush> salvato nella `_previousFill` variabile all'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> dell'oggetto <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="f4793-245">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="f4793-246">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f4793-246">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="f4793-247">Selezionare il testo `green` in <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-247">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="f4793-248">Trascinare il testo su un controllo Circle senza rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="f4793-248">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="f4793-249">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="f4793-249">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="f4793-250">![Visualizzare in anteprima gli effetti di un'operazione di trascinamento&#45;e&#45;drop](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="f4793-250">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="f4793-251">Trascinare il testo dal controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="f4793-251">Drag the text away from the Circle control.</span></span> <span data-ttu-id="f4793-252">Il controllo Circle passa da verde a blu.</span><span class="sxs-lookup"><span data-stu-id="f4793-252">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="f4793-253">Abilitare un pannello per la ricezione dei dati eliminati</span><span class="sxs-lookup"><span data-stu-id="f4793-253">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="f4793-254">In questa sezione si abilitano i pannelli che ospitano i controlli utente Circle in modo che fungano da destinazioni di rilascio per i dati del cerchio trascinato.</span><span class="sxs-lookup"><span data-stu-id="f4793-254">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="f4793-255">Si implementerà il codice che consente di spostare un cerchio da un pannello a un altro o di creare una copia di un controllo Circle tenendo premuto il tasto **CTRL** mentre si trascina e si elimina un cerchio.</span><span class="sxs-lookup"><span data-stu-id="f4793-255">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="f4793-256">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4793-256">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="f4793-257">Come illustrato nel codice XAML seguente, in ognuno dei <xref:System.Windows.Controls.StackPanel> controlli aggiungere i gestori per gli <xref:System.Windows.UIElement.DragOver> <xref:System.Windows.UIElement.Drop> eventi e.</span><span class="sxs-lookup"><span data-stu-id="f4793-257">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="f4793-258">Assegnare un nome al <xref:System.Windows.UIElement.DragOver> gestore eventi, `panel_DragOver` , e denominare il <xref:System.Windows.UIElement.Drop> gestore dell'evento, `panel_Drop` .</span><span class="sxs-lookup"><span data-stu-id="f4793-258">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="f4793-259">Aprire MainWindows.xaml.cs o MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f4793-259">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="f4793-260">Aggiungere il codice seguente per il <xref:System.Windows.UIElement.DragOver> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f4793-260">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="f4793-261">Questo <xref:System.Windows.UIElement.DragOver> gestore eventi esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4793-261">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="f4793-262">Verifica che i dati trascinati contengano i dati "Object" inclusi nel pacchetto <xref:System.Windows.DataObject> dal controllo utente Circle e passati nella chiamata a <xref:System.Windows.DragDrop.DoDragDrop%2A> .</span><span class="sxs-lookup"><span data-stu-id="f4793-262">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="f4793-263">Se i dati dell'oggetto sono presenti, controlla se il tasto **CTRL** è premuto.</span><span class="sxs-lookup"><span data-stu-id="f4793-263">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="f4793-264">Se viene premuto il tasto **CTRL** , imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà su <xref:System.Windows.DragDropEffects.Copy> .</span><span class="sxs-lookup"><span data-stu-id="f4793-264">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="f4793-265">In caso contrario, impostare la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà su <xref:System.Windows.DragDropEffects.Move> .</span><span class="sxs-lookup"><span data-stu-id="f4793-265">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="f4793-266">Aggiungere il codice seguente per il <xref:System.Windows.UIElement.Drop> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f4793-266">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="f4793-267">Questo <xref:System.Windows.UIElement.Drop> gestore eventi esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4793-267">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="f4793-268">Verifica se l' <xref:System.Windows.UIElement.Drop> evento è già stato gestito.</span><span class="sxs-lookup"><span data-stu-id="f4793-268">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="f4793-269">Ad esempio, se un cerchio viene rilasciato in un altro cerchio che gestisce l' <xref:System.Windows.UIElement.Drop> evento, non si vuole che il pannello che contiene il cerchio lo gestisca anche.</span><span class="sxs-lookup"><span data-stu-id="f4793-269">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="f4793-270">Se l' <xref:System.Windows.UIElement.Drop> evento non viene gestito, controlla se il tasto **CTRL** è premuto.</span><span class="sxs-lookup"><span data-stu-id="f4793-270">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="f4793-271">Se si preme il tasto **CTRL** quando si <xref:System.Windows.UIElement.Drop> verifica l'evento, crea una copia del controllo Circle e la aggiunge alla <xref:System.Windows.Controls.Panel.Children%2A> raccolta di <xref:System.Windows.Controls.StackPanel> .</span><span class="sxs-lookup"><span data-stu-id="f4793-271">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="f4793-272">Se il tasto **CTRL** non è premuto, sposta il cerchio dalla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del relativo pannello padre alla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello su cui è stata rilasciata.</span><span class="sxs-lookup"><span data-stu-id="f4793-272">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="f4793-273">Imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà per notificare al <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo se è stata eseguita un'operazione di spostamento o copia.</span><span class="sxs-lookup"><span data-stu-id="f4793-273">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="f4793-274">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f4793-274">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="f4793-275">Selezionare il testo `green` da <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="f4793-275">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="f4793-276">Trascinare il testo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="f4793-276">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="f4793-277">Trascinare un controllo Circle dal pannello di sinistra al pannello di destra e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="f4793-277">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="f4793-278">Il cerchio viene rimosso dalla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello sinistro e aggiunto alla raccolta Children del pannello di destra.</span><span class="sxs-lookup"><span data-stu-id="f4793-278">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="f4793-279">Trascinare un controllo Circle dal pannello in cui si trova nell'altro pannello e rilasciarlo mentre si preme il tasto **CTRL** .</span><span class="sxs-lookup"><span data-stu-id="f4793-279">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="f4793-280">Il cerchio viene copiato e la copia viene aggiunta alla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f4793-280">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="f4793-281">![Trascinamento di un cerchio premendo CTRL](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="f4793-281">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="f4793-282">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4793-282">See also</span></span>

- [<span data-ttu-id="f4793-283">Cenni preliminari sul trascinamento della selezione</span><span class="sxs-lookup"><span data-stu-id="f4793-283">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
