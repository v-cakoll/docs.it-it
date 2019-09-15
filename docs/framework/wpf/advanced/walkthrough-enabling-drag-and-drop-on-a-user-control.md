---
title: 'Procedura dettagliata: Abilitare il trascinamento della selezione in un controllo utente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 172e49c2c255db4d24d2180f919b1305326b5e82
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991802"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="40b01-102">Procedura dettagliata: Abilitare il trascinamento della selezione in un controllo utente</span><span class="sxs-lookup"><span data-stu-id="40b01-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="40b01-103">Questa procedura dettagliata illustra come creare un controllo utente personalizzato che possa partecipare al trasferimento di dati tramite trascinamento in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40b01-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="40b01-104">In questa procedura dettagliata verrà creato un oggetto WPF <xref:System.Windows.Controls.UserControl> personalizzato che rappresenta una forma circolare.</span><span class="sxs-lookup"><span data-stu-id="40b01-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="40b01-105">Si implementeranno funzionalità nel controllo per consentire il trasferimento di dati tramite trascinamento.</span><span class="sxs-lookup"><span data-stu-id="40b01-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="40b01-106">Ad esempio, se si trascina da un controllo Circle a un altro, i dati del colore di riempimento vengono copiati dal controllo Circle di origine a quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="40b01-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="40b01-107">Se si trascina da un controllo Circle a un <xref:System.Windows.Controls.TextBox>oggetto, la rappresentazione di stringa del colore di riempimento viene copiata <xref:System.Windows.Controls.TextBox>in.</span><span class="sxs-lookup"><span data-stu-id="40b01-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="40b01-108">Si creerà anche una piccola applicazione che contiene due controlli Panel e un oggetto <xref:System.Windows.Controls.TextBox> per testare la funzionalità di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="40b01-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="40b01-109">Si scriverà codice che consente ai pannelli di elaborare i dati Circle rilasciati per permettere di spostare o copiare cerchi dalla raccolta Children di un pannello all'altro.</span><span class="sxs-lookup"><span data-stu-id="40b01-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="40b01-110">Questa procedura dettagliata illustra le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b01-110">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="40b01-111">Creare un controllo utente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="40b01-111">Create a custom user control.</span></span>

- <span data-ttu-id="40b01-112">Consentire al controllo utente di essere un'origine di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="40b01-112">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="40b01-113">Consentire al controllo utente di essere un obiettivo di rilascio.</span><span class="sxs-lookup"><span data-stu-id="40b01-113">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="40b01-114">Consentire a un pannello di ricevere dati rilasciati dal controllo utente.</span><span class="sxs-lookup"><span data-stu-id="40b01-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="40b01-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="40b01-115">Prerequisites</span></span>

<span data-ttu-id="40b01-116">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="40b01-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="40b01-117">Creare il progetto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="40b01-117">Create the Application Project</span></span>
 <span data-ttu-id="40b01-118">In questa sezione verrà creata l'infrastruttura dell'applicazione, che include una pagina principale con due pannelli e un oggetto <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="40b01-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="40b01-119">Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="40b01-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="40b01-120">Per altre informazioni, vedere [Procedura dettagliata: Prima applicazione](../getting-started/walkthrough-my-first-wpf-desktop-application.md)desktop WPF.</span><span class="sxs-lookup"><span data-stu-id="40b01-120">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="40b01-121">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="40b01-121">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="40b01-122">Aggiungere il markup seguente tra i tag di apertura <xref:System.Windows.Controls.Grid> e di chiusura.</span><span class="sxs-lookup"><span data-stu-id="40b01-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="40b01-123">Questo markup crea l'interfaccia utente per l'applicazione di prova.</span><span class="sxs-lookup"><span data-stu-id="40b01-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="40b01-124">Aggiungere un nuovo controllo utente al progetto</span><span class="sxs-lookup"><span data-stu-id="40b01-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="40b01-125">In questa sezione si aggiungerà un nuovo controllo utente al progetto.</span><span class="sxs-lookup"><span data-stu-id="40b01-125">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="40b01-126">Scegliere **Aggiungi controllo utente** dal menu Progetto.</span><span class="sxs-lookup"><span data-stu-id="40b01-126">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="40b01-127">Nella finestra di dialogo **Aggiungi nuovo elemento** modificare il nome in `Circle.xaml`, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="40b01-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="40b01-128">Circle.xaml e il relativo code-behind vengono aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="40b01-128">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="40b01-129">Aprire Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="40b01-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="40b01-130">Questo file conterrà gli elementi dell'interfaccia utente del controllo utente.</span><span class="sxs-lookup"><span data-stu-id="40b01-130">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="40b01-131">Aggiungere il markup seguente alla radice <xref:System.Windows.Controls.Grid> per creare un controllo utente semplice con un cerchio blu come interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="40b01-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="40b01-132">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="40b01-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="40b01-133">In C#aggiungere il codice seguente dopo il costruttore senza parametri per creare un costruttore di copia.</span><span class="sxs-lookup"><span data-stu-id="40b01-133">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="40b01-134">In Visual Basic aggiungere il codice seguente per creare un costruttore senza parametri e un costruttore di copia.</span><span class="sxs-lookup"><span data-stu-id="40b01-134">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="40b01-135">Per consentire la copia del controllo utente, aggiungere un metodo di costruttore di copia nel file code-behind.</span><span class="sxs-lookup"><span data-stu-id="40b01-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="40b01-136">Nel controllo utente Circle semplificato si copieranno solo il riempimento e le dimensioni del controllo utente.</span><span class="sxs-lookup"><span data-stu-id="40b01-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="40b01-137">Aggiungere il controllo utente alla finestra principale</span><span class="sxs-lookup"><span data-stu-id="40b01-137">Add the user control to the main window</span></span>

1. <span data-ttu-id="40b01-138">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="40b01-138">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="40b01-139">Aggiungere il codice XAML seguente al tag <xref:System.Windows.Window> di apertura per creare un riferimento allo spazio dei nomi XML all'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="40b01-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="40b01-140">Nel primo <xref:System.Windows.Controls.StackPanel>, aggiungere il codice XAML seguente per creare due istanze del controllo utente Circle nel primo pannello.</span><span class="sxs-lookup"><span data-stu-id="40b01-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="40b01-141">Il codice XAML completo per il pannello è analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="40b01-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="40b01-142">Implementare gli eventi di origine del trascinamento nel controllo utente</span><span class="sxs-lookup"><span data-stu-id="40b01-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="40b01-143">In questa sezione verrà eseguito l'override del <xref:System.Windows.UIElement.OnMouseMove%2A> metodo e verrà avviata l'operazione di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="40b01-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="40b01-144">Se viene avviato un trascinamento (viene premuto un pulsante del mouse e il mouse viene spostato), i dati verranno inseriti in un pacchetto <xref:System.Windows.DataObject>da trasferire in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="40b01-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="40b01-145">In questo caso, il controllo Circle assemblerà tre elementi di dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.</span><span class="sxs-lookup"><span data-stu-id="40b01-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="40b01-146">Per avviare un'operazione di riempimento</span><span class="sxs-lookup"><span data-stu-id="40b01-146">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="40b01-147">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="40b01-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="40b01-148">Aggiungere la seguente <xref:System.Windows.UIElement.OnMouseMove%2A> sostituzione per fornire la gestione delle classi <xref:System.Windows.UIElement.MouseMove> per l'evento.</span><span class="sxs-lookup"><span data-stu-id="40b01-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="40b01-149">Questo <xref:System.Windows.UIElement.OnMouseMove%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b01-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="40b01-150">Controlla se il pulsante sinistro del mouse viene premuto mentre il mouse è in movimento.</span><span class="sxs-lookup"><span data-stu-id="40b01-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="40b01-151">Inserisce i dati Circle in un <xref:System.Windows.DataObject>oggetto.</span><span class="sxs-lookup"><span data-stu-id="40b01-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="40b01-152">In questo caso, il controllo Circle assembla tre elementi dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.</span><span class="sxs-lookup"><span data-stu-id="40b01-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="40b01-153">Chiama il metodo <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> statico per avviare l'operazione di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="40b01-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="40b01-154">Passare i tre parametri seguenti al <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo:</span><span class="sxs-lookup"><span data-stu-id="40b01-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="40b01-155">`dragSource` - Un riferimento a questo controllo.</span><span class="sxs-lookup"><span data-stu-id="40b01-155">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="40b01-156">`data`: Oggetto <xref:System.Windows.DataObject> creato nel codice precedente.</span><span class="sxs-lookup"><span data-stu-id="40b01-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="40b01-157">`allowedEffects`: Le operazioni di trascinamento della selezione consentite <xref:System.Windows.DragDropEffects.Copy> , <xref:System.Windows.DragDropEffects.Move>ovvero o.</span><span class="sxs-lookup"><span data-stu-id="40b01-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="40b01-158">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="40b01-158">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="40b01-159">Fare clic su uno dei controlli Circle e trascinarlo sui pannelli, sull'altro cerchio e <xref:System.Windows.Controls.TextBox>su.</span><span class="sxs-lookup"><span data-stu-id="40b01-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="40b01-160">Quando si trascina su <xref:System.Windows.Controls.TextBox>, il cursore cambia per indicare uno spostamento.</span><span class="sxs-lookup"><span data-stu-id="40b01-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="40b01-161">Quando si trascina un cerchio sul controllo <xref:System.Windows.Controls.TextBox>, premere il tasto **CTRL** .</span><span class="sxs-lookup"><span data-stu-id="40b01-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="40b01-162">Notare come il cursore cambia aspetto per indicare una copia.</span><span class="sxs-lookup"><span data-stu-id="40b01-162">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="40b01-163">Trascinare e rilasciare un cerchio nell'oggetto <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="40b01-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="40b01-164">La rappresentazione di stringa del colore di riempimento del cerchio viene aggiunta all'oggetto <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="40b01-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="40b01-165">![Rappresentazione di stringa del colore di riempimento del controllo Circle](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="40b01-165">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="40b01-166">Per impostazione predefinita, il cursore cambierà aspetto durante un'operazione di trascinamento per indicare l'effetto che avrà il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="40b01-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="40b01-167">È possibile personalizzare il feedback fornito all'utente gestendo l' <xref:System.Windows.UIElement.GiveFeedback> evento e impostando un cursore diverso.</span><span class="sxs-lookup"><span data-stu-id="40b01-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="40b01-168">Inviare commenti e suggerimenti all'utente</span><span class="sxs-lookup"><span data-stu-id="40b01-168">Give feedback to the user</span></span>

1. <span data-ttu-id="40b01-169">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="40b01-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="40b01-170">Aggiungere la seguente <xref:System.Windows.UIElement.OnGiveFeedback%2A> sostituzione per fornire la gestione delle classi <xref:System.Windows.UIElement.GiveFeedback> per l'evento.</span><span class="sxs-lookup"><span data-stu-id="40b01-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="40b01-171">Questo <xref:System.Windows.UIElement.OnGiveFeedback%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b01-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="40b01-172">Verifica i <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valori impostati nel gestore eventi dell'obiettivo di <xref:System.Windows.UIElement.DragOver> rilascio.</span><span class="sxs-lookup"><span data-stu-id="40b01-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="40b01-173">Imposta un cursore personalizzato in base al <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="40b01-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="40b01-174">Il cursore ha lo scopo di fornire un feedback visivo all'utente sull'effetto che avrà il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="40b01-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="40b01-175">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="40b01-175">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="40b01-176">Trascinare uno dei controlli Circle sui pannelli, sull'altro cerchio e sull'oggetto <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="40b01-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="40b01-177">Si noti che i cursori sono ora i cursori personalizzati specificati nella <xref:System.Windows.UIElement.OnGiveFeedback%2A> sostituzione.</span><span class="sxs-lookup"><span data-stu-id="40b01-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="40b01-178">![Trascinamento con cursori personalizzati](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="40b01-178">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="40b01-179">Selezionare il testo `green` <xref:System.Windows.Controls.TextBox>da.</span><span class="sxs-lookup"><span data-stu-id="40b01-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="40b01-180">Trascinare il testo `green` su un controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="40b01-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="40b01-181">Notare che vengono visualizzati i cursori predefiniti per indicare gli effetti dell'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="40b01-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="40b01-182">Il cursore di feedback viene sempre impostato dall'origine di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="40b01-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="40b01-183">Implementare eventi di destinazione di rilascio nel controllo utente</span><span class="sxs-lookup"><span data-stu-id="40b01-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="40b01-184">In questa sezione si specificherà che il controllo utente è un obiettivo di rilascio, si eseguirà l'override dei metodi che consentono al controllo utente di essere un obiettivo di rilascio e si elaboreranno i dati rilasciati sul controllo.</span><span class="sxs-lookup"><span data-stu-id="40b01-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="40b01-185">Per consentire al controllo utente di essere un obiettivo di rilascio</span><span class="sxs-lookup"><span data-stu-id="40b01-185">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="40b01-186">Aprire Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="40b01-186">Open Circle.xaml.</span></span>

2. <span data-ttu-id="40b01-187">Nel tag di <xref:System.Windows.Controls.UserControl> apertura aggiungere la <xref:System.Windows.UIElement.AllowDrop%2A> proprietà e impostarla su `true`.</span><span class="sxs-lookup"><span data-stu-id="40b01-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="40b01-188">Il <xref:System.Windows.UIElement.OnDrop%2A> metodo viene chiamato quando la <xref:System.Windows.UIElement.AllowDrop%2A> proprietà è impostata `true` su e i dati dell'origine di trascinamento vengono rilasciati sul controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="40b01-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="40b01-189">In questo metodo si elaboreranno i dati rilasciati e li si applicheranno al controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="40b01-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="40b01-190">Per elaborare i dati rilasciati</span><span class="sxs-lookup"><span data-stu-id="40b01-190">To process the dropped data</span></span>

1. <span data-ttu-id="40b01-191">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="40b01-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="40b01-192">Aggiungere la seguente <xref:System.Windows.UIElement.OnDrop%2A> sostituzione per fornire la gestione delle classi <xref:System.Windows.UIElement.Drop> per l'evento.</span><span class="sxs-lookup"><span data-stu-id="40b01-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="40b01-193">Questo <xref:System.Windows.UIElement.OnDrop%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b01-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="40b01-194">Usa il <xref:System.Windows.DataObject.GetDataPresent%2A> metodo per verificare se i dati trascinati contengono un oggetto String.</span><span class="sxs-lookup"><span data-stu-id="40b01-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="40b01-195">Usa il <xref:System.Windows.DataObject.GetData%2A> metodo per estrarre i dati di stringa, se presenti.</span><span class="sxs-lookup"><span data-stu-id="40b01-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="40b01-196">Usa un <xref:System.Windows.Media.BrushConverter> oggetto per tentare di convertire la stringa in <xref:System.Windows.Media.Brush>un oggetto.</span><span class="sxs-lookup"><span data-stu-id="40b01-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="40b01-197">Se la conversione ha esito positivo, applica il pennello <xref:System.Windows.Shapes.Shape.Fill%2A> all'oggetto <xref:System.Windows.Shapes.Ellipse> dell'oggetto che fornisce l'interfaccia utente del controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="40b01-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="40b01-198">Contrassegna l' <xref:System.Windows.UIElement.Drop> evento come gestito.</span><span class="sxs-lookup"><span data-stu-id="40b01-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="40b01-199">È necessario contrassegnare l'evento di trascinamento come gestito per segnalare agli altri elementi che ricevono l'evento che questo è stato gestito dal controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="40b01-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="40b01-200">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="40b01-200">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="40b01-201">Selezionare il testo `green` <xref:System.Windows.Controls.TextBox>in.</span><span class="sxs-lookup"><span data-stu-id="40b01-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="40b01-202">Trascinare il testo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="40b01-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="40b01-203">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="40b01-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="40b01-204">![Convertire una stringa in pennello](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="40b01-204">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="40b01-205">Digitare il testo `green` <xref:System.Windows.Controls.TextBox>in.</span><span class="sxs-lookup"><span data-stu-id="40b01-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="40b01-206">Selezionare il testo `gre` <xref:System.Windows.Controls.TextBox>in.</span><span class="sxs-lookup"><span data-stu-id="40b01-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="40b01-207">Trascinarlo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="40b01-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="40b01-208">Notare che il cursore cambia aspetto per indicare che è consentito il trascinamento ma il colore del controllo Circle non cambia poiché `gre` non è un colore valido.</span><span class="sxs-lookup"><span data-stu-id="40b01-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="40b01-209">Trascinare dal controllo Circle verde e rilasciare sul controllo Circle blu.</span><span class="sxs-lookup"><span data-stu-id="40b01-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="40b01-210">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="40b01-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="40b01-211">Si noti che il cursore viene visualizzato a seconda che il <xref:System.Windows.Controls.TextBox> o il cerchio sia l'origine del trascinamento.</span><span class="sxs-lookup"><span data-stu-id="40b01-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="40b01-212">L'impostazione <xref:System.Windows.UIElement.AllowDrop%2A> della proprietà `true` su e l'elaborazione dei dati eliminati è tutto ciò che è necessario per consentire a un elemento di essere un obiettivo di rilascio.</span><span class="sxs-lookup"><span data-stu-id="40b01-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="40b01-213">Tuttavia, per offrire un'esperienza utente migliore, è necessario gestire anche gli <xref:System.Windows.UIElement.DragEnter>eventi <xref:System.Windows.UIElement.DragLeave>, e <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="40b01-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="40b01-214">In questi eventi, è possibile eseguire controlli e offrire feedback all'utente prima che i dati vengono rilasciati.</span><span class="sxs-lookup"><span data-stu-id="40b01-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="40b01-215">Quando i dati vengono rilasciati sul controllo utente Circle, il controllo deve notificare all'origine di trascinamento se può elaborare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="40b01-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="40b01-216">Se il controllo non è in grado di elaborare i dati, deve rifiutare il rilascio.</span><span class="sxs-lookup"><span data-stu-id="40b01-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="40b01-217">A tale scopo, si gestirà l' <xref:System.Windows.UIElement.DragOver> evento e si imposterà la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="40b01-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="40b01-218">Per verificare se il rilascio dei dati è consentito</span><span class="sxs-lookup"><span data-stu-id="40b01-218">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="40b01-219">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="40b01-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="40b01-220">Aggiungere la seguente <xref:System.Windows.UIElement.OnDragOver%2A> sostituzione per fornire la gestione delle classi <xref:System.Windows.UIElement.DragOver> per l'evento.</span><span class="sxs-lookup"><span data-stu-id="40b01-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="40b01-221">Questo <xref:System.Windows.UIElement.OnDragOver%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b01-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="40b01-222">Imposta la proprietà <xref:System.Windows.DragEventArgs.Effects%2A> su <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="40b01-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="40b01-223">Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se il controllo utente Circle può elaborare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="40b01-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="40b01-224">Se il controllo utente può elaborare i dati, imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà su <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="40b01-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="40b01-225">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="40b01-225">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="40b01-226">Selezionare il testo `gre` <xref:System.Windows.Controls.TextBox>in.</span><span class="sxs-lookup"><span data-stu-id="40b01-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="40b01-227">Trascinare il testo su un controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="40b01-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="40b01-228">Notare che ora il cursore cambia aspetto per indicare che il trascinamento non è consentito poiché `gre` non è un colore valido.</span><span class="sxs-lookup"><span data-stu-id="40b01-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="40b01-229">È possibile migliorare ulteriormente l'esperienza utente applicando un'anteprima dell'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="40b01-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="40b01-230">Per il controllo utente Circle, si eseguirà l' <xref:System.Windows.UIElement.OnDragEnter%2A> override <xref:System.Windows.UIElement.OnDragLeave%2A> dei metodi e.</span><span class="sxs-lookup"><span data-stu-id="40b01-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="40b01-231">Quando i dati vengono trascinati sul controllo, lo sfondo <xref:System.Windows.Shapes.Shape.Fill%2A> corrente viene salvato in una variabile segnaposto.</span><span class="sxs-lookup"><span data-stu-id="40b01-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="40b01-232">La stringa viene quindi convertita in un pennello e applicata all' <xref:System.Windows.Shapes.Ellipse> oggetto che fornisce l'interfaccia utente del cerchio.</span><span class="sxs-lookup"><span data-stu-id="40b01-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="40b01-233">Se i dati vengono trascinati fuori dal cerchio senza essere eliminati, il valore <xref:System.Windows.Shapes.Shape.Fill%2A> originale viene nuovamente applicato al cerchio.</span><span class="sxs-lookup"><span data-stu-id="40b01-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="40b01-234">Per visualizzare in anteprima gli effetti dell'operazione di trascinamento</span><span class="sxs-lookup"><span data-stu-id="40b01-234">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="40b01-235">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="40b01-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="40b01-236">Nella classe Circle dichiarare una variabile privata <xref:System.Windows.Media.Brush> denominata `_previousFill` e inizializzarla su `null`.</span><span class="sxs-lookup"><span data-stu-id="40b01-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="40b01-237">Aggiungere la seguente <xref:System.Windows.UIElement.OnDragEnter%2A> sostituzione per fornire la gestione delle classi <xref:System.Windows.UIElement.DragEnter> per l'evento.</span><span class="sxs-lookup"><span data-stu-id="40b01-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="40b01-238">Questo <xref:System.Windows.UIElement.OnDragEnter%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b01-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="40b01-239">Salva la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà dell'oggetto <xref:System.Windows.Shapes.Ellipse> nella `_previousFill` variabile.</span><span class="sxs-lookup"><span data-stu-id="40b01-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="40b01-240">Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se i dati possono essere convertiti in un oggetto. <xref:System.Windows.Media.Brush></span><span class="sxs-lookup"><span data-stu-id="40b01-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="40b01-241">Se i dati vengono convertiti in un <xref:System.Windows.Media.Brush>oggetto valido, lo applica <xref:System.Windows.Shapes.Shape.Fill%2A> a del <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="40b01-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="40b01-242">Aggiungere la seguente <xref:System.Windows.UIElement.OnDragLeave%2A> sostituzione per fornire la gestione delle classi <xref:System.Windows.UIElement.DragLeave> per l'evento.</span><span class="sxs-lookup"><span data-stu-id="40b01-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="40b01-243">Questo <xref:System.Windows.UIElement.OnDragLeave%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b01-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="40b01-244">Applica l' <xref:System.Windows.Media.Brush> oggetto salvato `_previousFill` nella variabile all'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> dell'oggetto <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="40b01-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="40b01-245">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="40b01-245">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="40b01-246">Selezionare il testo `green` <xref:System.Windows.Controls.TextBox>in.</span><span class="sxs-lookup"><span data-stu-id="40b01-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="40b01-247">Trascinare il testo su un controllo Circle senza rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="40b01-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="40b01-248">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="40b01-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="40b01-249">![Visualizzare in anteprima gli effetti di un'operazione di trascinamento](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="40b01-249">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="40b01-250">Trascinare il testo dal controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="40b01-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="40b01-251">Il controllo Circle passa da verde a blu.</span><span class="sxs-lookup"><span data-stu-id="40b01-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="40b01-252">Abilitare un pannello per la ricezione dei dati eliminati</span><span class="sxs-lookup"><span data-stu-id="40b01-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="40b01-253">In questa sezione si abilitano i pannelli che ospitano i controlli utente Circle in modo che fungano da destinazioni di rilascio per i dati del cerchio trascinato.</span><span class="sxs-lookup"><span data-stu-id="40b01-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="40b01-254">Si implementerà il codice che consente di spostare un cerchio da un pannello a un altro o di creare una copia di un controllo Circle tenendo premuto il tasto **CTRL** mentre si trascina e si elimina un cerchio.</span><span class="sxs-lookup"><span data-stu-id="40b01-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="40b01-255">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="40b01-255">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="40b01-256">Come illustrato nel codice XAML seguente, in ognuno dei <xref:System.Windows.Controls.StackPanel> controlli aggiungere i gestori per gli <xref:System.Windows.UIElement.DragOver> eventi e <xref:System.Windows.UIElement.Drop> .</span><span class="sxs-lookup"><span data-stu-id="40b01-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="40b01-257">Assegnare un <xref:System.Windows.UIElement.DragOver> nome al `panel_DragOver`gestore eventi,, e <xref:System.Windows.UIElement.Drop> denominare `panel_Drop`il gestore dell'evento,.</span><span class="sxs-lookup"><span data-stu-id="40b01-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="40b01-258">Aprire MainWindows.xaml.cs o MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="40b01-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="40b01-259">Aggiungere il codice seguente per il <xref:System.Windows.UIElement.DragOver> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="40b01-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="40b01-260">Questo <xref:System.Windows.UIElement.DragOver> gestore eventi esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b01-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="40b01-261">Verifica che i dati trascinati contengano i dati "Object" inclusi nel <xref:System.Windows.DataObject> pacchetto dal controllo utente Circle e passati nella chiamata a. <xref:System.Windows.DragDrop.DoDragDrop%2A></span><span class="sxs-lookup"><span data-stu-id="40b01-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="40b01-262">Se i dati dell'oggetto sono presenti, controlla se il tasto **CTRL** è premuto.</span><span class="sxs-lookup"><span data-stu-id="40b01-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="40b01-263">Se viene premuto il tasto **CTRL** , imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà su <xref:System.Windows.DragDropEffects.Copy>.</span><span class="sxs-lookup"><span data-stu-id="40b01-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="40b01-264">In caso contrario, <xref:System.Windows.DragEventArgs.Effects%2A> impostare la <xref:System.Windows.DragDropEffects.Move>proprietà su.</span><span class="sxs-lookup"><span data-stu-id="40b01-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="40b01-265">Aggiungere il codice seguente per il <xref:System.Windows.UIElement.Drop> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="40b01-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="40b01-266">Questo <xref:System.Windows.UIElement.Drop> gestore eventi esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b01-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="40b01-267">Verifica se l' <xref:System.Windows.UIElement.Drop> evento è già stato gestito.</span><span class="sxs-lookup"><span data-stu-id="40b01-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="40b01-268">Ad esempio, se un cerchio viene rilasciato in un altro cerchio che gestisce <xref:System.Windows.UIElement.Drop> l'evento, non si vuole che il pannello che contiene il cerchio lo gestisca anche.</span><span class="sxs-lookup"><span data-stu-id="40b01-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="40b01-269">Se l' <xref:System.Windows.UIElement.Drop> evento non viene gestito, controlla se il tasto **CTRL** è premuto.</span><span class="sxs-lookup"><span data-stu-id="40b01-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="40b01-270">Se si preme il tasto **CTRL** quando si <xref:System.Windows.UIElement.Drop> verifica l'evento, crea una copia del controllo Circle e <xref:System.Windows.Controls.StackPanel>la <xref:System.Windows.Controls.Panel.Children%2A> aggiunge alla raccolta di.</span><span class="sxs-lookup"><span data-stu-id="40b01-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="40b01-271">Se il tasto **CTRL** non è premuto, sposta il cerchio dalla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del relativo pannello <xref:System.Windows.Controls.Panel.Children%2A> padre alla raccolta del pannello su cui è stata rilasciata.</span><span class="sxs-lookup"><span data-stu-id="40b01-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="40b01-272">Imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà per notificare <xref:System.Windows.DragDrop.DoDragDrop%2A> al metodo se è stata eseguita un'operazione di spostamento o copia.</span><span class="sxs-lookup"><span data-stu-id="40b01-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="40b01-273">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="40b01-273">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="40b01-274">Selezionare il testo `green` <xref:System.Windows.Controls.TextBox>da.</span><span class="sxs-lookup"><span data-stu-id="40b01-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="40b01-275">Trascinare il testo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="40b01-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="40b01-276">Trascinare un controllo Circle dal pannello di sinistra al pannello di destra e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="40b01-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="40b01-277">Il cerchio viene rimosso dalla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello sinistro e aggiunto alla raccolta Children del pannello di destra.</span><span class="sxs-lookup"><span data-stu-id="40b01-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="40b01-278">Trascinare un controllo Circle dal pannello in cui si trova nell'altro pannello e rilasciarlo mentre si preme il tasto **CTRL** .</span><span class="sxs-lookup"><span data-stu-id="40b01-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="40b01-279">Il cerchio viene copiato e la copia viene aggiunta alla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="40b01-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="40b01-280">![Trascinamento di un controllo Circle mentre si preme CTRL](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="40b01-280">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="40b01-281">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40b01-281">See also</span></span>

- [<span data-ttu-id="40b01-282">Cenni preliminari sul trascinamento della selezione</span><span class="sxs-lookup"><span data-stu-id="40b01-282">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
