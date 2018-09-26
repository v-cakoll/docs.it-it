---
title: 'Procedura dettagliata: abilitare il trascinamento della selezione in un controllo utente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 7ca4987da8422c00e3fc34ff4605ddd13e4091b6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193729"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="5fb4f-102">Procedura dettagliata: abilitare il trascinamento della selezione in un controllo utente</span><span class="sxs-lookup"><span data-stu-id="5fb4f-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="5fb4f-103">Questa procedura dettagliata illustra come creare un controllo utente personalizzato che possa partecipare al trasferimento di dati tramite trascinamento in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fb4f-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="5fb4f-104">In questa procedura dettagliata, si creerà un controllo personalizzato WPF <xref:System.Windows.Controls.UserControl> che rappresenta una forma circolare.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="5fb4f-105">Si implementeranno funzionalità nel controllo per consentire il trasferimento di dati tramite trascinamento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="5fb4f-106">Ad esempio, se si trascina da un controllo Circle a un altro, i dati del colore di riempimento vengono copiati dal controllo Circle di origine a quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="5fb4f-107">Se si trascina da un controllo Circle a un <xref:System.Windows.Controls.TextBox>, la rappresentazione di stringa del colore di riempimento viene copiata la <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="5fb4f-108">Si creerà inoltre una piccola applicazione che contiene due controlli panel e un <xref:System.Windows.Controls.TextBox> per testare le funzionalità di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="5fb4f-109">Si scriverà codice che consente ai pannelli di elaborare i dati Circle rilasciati per permettere di spostare o copiare cerchi dalla raccolta Children di un pannello all'altro.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="5fb4f-110">Questa procedura dettagliata illustra le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fb4f-110">This walkthrough illustrates the following tasks:</span></span>

-   <span data-ttu-id="5fb4f-111">Creare un controllo utente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-111">Create a custom user control.</span></span>

-   <span data-ttu-id="5fb4f-112">Consentire al controllo utente di essere un'origine di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-112">Enable the user control to be a drag source.</span></span>

-   <span data-ttu-id="5fb4f-113">Consentire al controllo utente di essere un obiettivo di rilascio.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-113">Enable the user control to be a drop target.</span></span>

-   <span data-ttu-id="5fb4f-114">Consentire a un pannello di ricevere dati rilasciati dal controllo utente.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5fb4f-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5fb4f-115">Prerequisites</span></span>

<span data-ttu-id="5fb4f-116">È necessario Visual Studio per completare questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="5fb4f-117">Creare il progetto di applicazione</span><span class="sxs-lookup"><span data-stu-id="5fb4f-117">Create the Application Project</span></span>
 <span data-ttu-id="5fb4f-118">In questa sezione si creerà l'infrastruttura dell'applicazione, che include una pagina principale con due pannelli e un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1.  <span data-ttu-id="5fb4f-119">Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="5fb4f-120">Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="5fb4f-120">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>

2.  <span data-ttu-id="5fb4f-121">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-121">Open MainWindow.xaml.</span></span>

3.  <span data-ttu-id="5fb4f-122">Aggiungere il markup seguente tra l'apertura e chiusura <xref:System.Windows.Controls.Grid> tag.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="5fb4f-123">Questo markup crea l'interfaccia utente per l'applicazione di prova.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="5fb4f-124">Aggiungere un nuovo controllo utente al progetto</span><span class="sxs-lookup"><span data-stu-id="5fb4f-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="5fb4f-125">In questa sezione si aggiungerà un nuovo controllo utente al progetto.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-125">In this section, you will add a new user control to the project.</span></span>

1.  <span data-ttu-id="5fb4f-126">Scegliere **Aggiungi controllo utente** dal menu Progetto.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-126">On the Project menu, select **Add User Control**.</span></span>

2.  <span data-ttu-id="5fb4f-127">Nel **Aggiungi nuovo elemento** finestra di dialogo, modificare il nome da `Circle.xaml`, fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="5fb4f-128">Circle.xaml e il relativo code-behind vengono aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-128">Circle.xaml and its code-behind is added to the project.</span></span>

3.  <span data-ttu-id="5fb4f-129">Aprire Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="5fb4f-130">Questo file conterrà gli elementi dell'interfaccia utente del controllo utente.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-130">This file will contain the user interface elements of the user control.</span></span>

4.  <span data-ttu-id="5fb4f-131">Aggiungere il markup seguente alla radice <xref:System.Windows.Controls.Grid> per creare un controllo utente semplice con un cerchio blu come interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5.  <span data-ttu-id="5fb4f-132">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6.  <span data-ttu-id="5fb4f-133">In C# aggiungere il codice seguente dopo il costruttore predefinito per creare un costruttore di copia.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-133">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="5fb4f-134">In Visual Basic aggiungere il codice seguente per creare un costruttore predefinito e un costruttore di copia.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-134">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>

     <span data-ttu-id="5fb4f-135">Per consentire la copia del controllo utente, aggiungere un metodo di costruttore di copia nel file code-behind.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="5fb4f-136">Nel controllo utente Circle semplificato si copieranno solo il riempimento e le dimensioni del controllo utente.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="5fb4f-137">Aggiungere il controllo utente alla finestra principale</span><span class="sxs-lookup"><span data-stu-id="5fb4f-137">Add the user control to the main window</span></span>

1.  <span data-ttu-id="5fb4f-138">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-138">Open MainWindow.xaml.</span></span>

2.  <span data-ttu-id="5fb4f-139">Aggiungere il seguente XAML per l'apertura <xref:System.Windows.Window> tag per creare un riferimento a spazio dei nomi XML per l'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```
    xmlns:local="clr-namespace:DragDropExample"
    ```

3.  <span data-ttu-id="5fb4f-140">Nel primo <xref:System.Windows.Controls.StackPanel>, aggiungere il seguente XAML per creare due istanze del controllo utente Circle nel primo pannello.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="5fb4f-141">Il codice XAML completo per il pannello è analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="5fb4f-142">Implementare eventi di origine di trascinamento nel controllo utente</span><span class="sxs-lookup"><span data-stu-id="5fb4f-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="5fb4f-143">In questa sezione si eseguirà l'override di <xref:System.Windows.UIElement.OnMouseMove%2A> (metodo) e avviare l'operazione di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="5fb4f-144">Se viene avviato un trascinamento viene premuto un pulsante del mouse e il mouse viene spostato, verranno inseriti i dati per il trasferimento in un <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="5fb4f-145">In questo caso, il controllo Circle assemblerà tre elementi di dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="5fb4f-146">Per avviare un'operazione di riempimento</span><span class="sxs-lookup"><span data-stu-id="5fb4f-146">To initiate a drag-and-drop operation</span></span>

1.  <span data-ttu-id="5fb4f-147">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="5fb4f-148">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnMouseMove%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.MouseMove> evento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="5fb4f-149">Ciò <xref:System.Windows.UIElement.OnMouseMove%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fb4f-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="5fb4f-150">Controlla se il pulsante sinistro del mouse viene premuto mentre il mouse è in movimento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    -   <span data-ttu-id="5fb4f-151">Assembla i dati Circle in una <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="5fb4f-152">In questo caso, il controllo Circle assembla tre elementi dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    -   <span data-ttu-id="5fb4f-153">Chiama il metodo statico <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> metodo per avviare l'operazione di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="5fb4f-154">Passare i tre parametri seguenti per il <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo:</span><span class="sxs-lookup"><span data-stu-id="5fb4f-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        -   <span data-ttu-id="5fb4f-155">`dragSource` - Un riferimento a questo controllo.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-155">`dragSource` – A reference to this control.</span></span>

        -   <span data-ttu-id="5fb4f-156">`data` : Le <xref:System.Windows.DataObject> creato nel codice precedente.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        -   <span data-ttu-id="5fb4f-157">`allowedEffects` -Le operazioni di trascinamento e rilascio consentite, che sono <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3.  <span data-ttu-id="5fb4f-158">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-158">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="5fb4f-159">Fare clic su uno dei controlli Circle e trascinarlo sui pannelli, su altro controllo Circle e <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="5fb4f-160">Quando viene trascinato sul <xref:System.Windows.Controls.TextBox>, il cursore cambia per indicare un'operazione di spostamento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5.  <span data-ttu-id="5fb4f-161">Durante il trascinamento di un cerchio tramite il <xref:System.Windows.Controls.TextBox>, premere la **Ctrl** chiave.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="5fb4f-162">Notare come il cursore cambia aspetto per indicare una copia.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-162">Notice how the cursor changes to indicate a copy.</span></span>

6.  <span data-ttu-id="5fb4f-163">Trascinare e rilasciare un controllo Circle sul <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="5fb4f-164">Rappresentazione di stringa del colore di riempimento del cerchio viene aggiunto il <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="5fb4f-165">![Rappresentazione di stringa del colore di riempimento del controllo Circle](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="5fb4f-165">![String representation of Circle's fill color](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="5fb4f-166">Per impostazione predefinita, il cursore cambierà aspetto durante un'operazione di trascinamento per indicare l'effetto che avrà il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="5fb4f-167">È possibile personalizzare il feedback fornito all'utente gestendo il <xref:System.Windows.UIElement.GiveFeedback> evento e l'impostazione di un cursore diverso.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="5fb4f-168">Fornire commenti e suggerimenti all'utente</span><span class="sxs-lookup"><span data-stu-id="5fb4f-168">Give feedback to the user</span></span>

1.  <span data-ttu-id="5fb4f-169">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="5fb4f-170">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnGiveFeedback%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.GiveFeedback> evento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="5fb4f-171">Ciò <xref:System.Windows.UIElement.OnGiveFeedback%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fb4f-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="5fb4f-172">Controlla il <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> i valori impostati nell'obiettivo di rilascio <xref:System.Windows.UIElement.DragOver> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    -   <span data-ttu-id="5fb4f-173">Impostare un cursore personalizzato in base il <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="5fb4f-174">Il cursore ha lo scopo di fornire un feedback visivo all'utente sull'effetto che avrà il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3.  <span data-ttu-id="5fb4f-175">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-175">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="5fb4f-176">Trascinare uno del cerchio controlli sui pannelli, su altro controllo Circle e <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="5fb4f-177">Si noti che i cursori sono ora i cursori personalizzati specificati nella <xref:System.Windows.UIElement.OnGiveFeedback%2A> eseguire l'override.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="5fb4f-178">![Trascinamento con cursori personalizzati](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="5fb4f-178">![Drag and drop with custom cursors](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5.  <span data-ttu-id="5fb4f-179">Selezionare il testo `green` dal <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6.  <span data-ttu-id="5fb4f-180">Trascinare il testo `green` su un controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="5fb4f-181">Notare che vengono visualizzati i cursori predefiniti per indicare gli effetti dell'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="5fb4f-182">Il cursore di feedback viene sempre impostato dall'origine di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="5fb4f-183">Implementare gli eventi di destinazione di rilascio nel controllo utente</span><span class="sxs-lookup"><span data-stu-id="5fb4f-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="5fb4f-184">In questa sezione si specificherà che il controllo utente è un obiettivo di rilascio, si eseguirà l'override dei metodi che consentono al controllo utente di essere un obiettivo di rilascio e si elaboreranno i dati rilasciati sul controllo.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="5fb4f-185">Per consentire al controllo utente di essere un obiettivo di rilascio</span><span class="sxs-lookup"><span data-stu-id="5fb4f-185">To enable the user control to be a drop target</span></span>

1.  <span data-ttu-id="5fb4f-186">Aprire Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-186">Open Circle.xaml.</span></span>

2.  <span data-ttu-id="5fb4f-187">Nell'apertura <xref:System.Windows.Controls.UserControl> tag, aggiungere i <xref:System.Windows.UIElement.AllowDrop%2A> proprietà e impostarla su `true`.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="5fb4f-188">Il <xref:System.Windows.UIElement.OnDrop%2A> metodo viene chiamato quando il <xref:System.Windows.UIElement.AllowDrop%2A> è impostata su `true` e dati dall'origine di trascinamento vengono rilasciati sul controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="5fb4f-189">In questo metodo si elaboreranno i dati rilasciati e li si applicheranno al controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="5fb4f-190">Per elaborare i dati rilasciati</span><span class="sxs-lookup"><span data-stu-id="5fb4f-190">To process the dropped data</span></span>

1.  <span data-ttu-id="5fb4f-191">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="5fb4f-192">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDrop%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.Drop> evento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="5fb4f-193">Ciò <xref:System.Windows.UIElement.OnDrop%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fb4f-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="5fb4f-194">Usa il <xref:System.Windows.DataObject.GetDataPresent%2A> metodo per verificare se i dati trascinati contengono un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    -   <span data-ttu-id="5fb4f-195">Usa il <xref:System.Windows.DataObject.GetData%2A> metodo per estrarre i dati stringa, se presente.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    -   <span data-ttu-id="5fb4f-196">Usa un' <xref:System.Windows.Media.BrushConverter> per provare a convertire la stringa in un <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    -   <span data-ttu-id="5fb4f-197">Se la conversione ha esito positivo, si applica il pennello per il <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    -   <span data-ttu-id="5fb4f-198">Segni di <xref:System.Windows.UIElement.Drop> evento come gestito.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="5fb4f-199">È necessario contrassegnare l'evento di trascinamento come gestito per segnalare agli altri elementi che ricevono l'evento che questo è stato gestito dal controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3.  <span data-ttu-id="5fb4f-200">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-200">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="5fb4f-201">Selezionare il testo `green` nella <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5.  <span data-ttu-id="5fb4f-202">Trascinare il testo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="5fb4f-203">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="5fb4f-204">![Convertire una stringa in pennello](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="5fb4f-204">![Convert a string to a brush](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6.  <span data-ttu-id="5fb4f-205">Digitare il testo `green` nella <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7.  <span data-ttu-id="5fb4f-206">Selezionare il testo `gre` nella <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8.  <span data-ttu-id="5fb4f-207">Trascinarlo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="5fb4f-208">Notare che il cursore cambia aspetto per indicare che è consentito il trascinamento ma il colore del controllo Circle non cambia poiché `gre` non è un colore valido.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="5fb4f-209">Trascinare dal controllo Circle verde e rilasciare sul controllo Circle blu.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="5fb4f-210">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="5fb4f-211">Si noti che il cursore visualizzato dipende dal fatto che il <xref:System.Windows.Controls.TextBox> o cerchio è l'origine di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="5fb4f-212">Impostando il <xref:System.Windows.UIElement.AllowDrop%2A> proprietà `true` ed elabora i dati rilasciati è tutto ciò che è necessaria per consentire un elemento per ottenere un obiettivo di rilascio.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="5fb4f-213">Per fornire un'esperienza utente migliore, tuttavia, è necessario gestire anche il <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, e <xref:System.Windows.UIElement.DragOver> eventi.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="5fb4f-214">In questi eventi, è possibile eseguire controlli e offrire feedback all'utente prima che i dati vengono rilasciati.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="5fb4f-215">Quando i dati vengono rilasciati sul controllo utente Circle, il controllo deve notificare all'origine di trascinamento se può elaborare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="5fb4f-216">Se il controllo non è in grado di elaborare i dati, deve rifiutare il rilascio.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="5fb4f-217">A tale scopo, è necessario gestire il <xref:System.Windows.UIElement.DragOver> evento e impostare il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="5fb4f-218">Per verificare se il rilascio dei dati è consentito</span><span class="sxs-lookup"><span data-stu-id="5fb4f-218">To verify that the data drop is allowed</span></span>

1.  <span data-ttu-id="5fb4f-219">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="5fb4f-220">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDragOver%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.DragOver> evento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="5fb4f-221">Ciò <xref:System.Windows.UIElement.OnDragOver%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fb4f-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="5fb4f-222">Imposta la proprietà <xref:System.Windows.DragEventArgs.Effects%2A> su <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    -   <span data-ttu-id="5fb4f-223">Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se il controllo utente Circle può elaborare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    -   <span data-ttu-id="5fb4f-224">Se il controllo utente può elaborare i dati, imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3.  <span data-ttu-id="5fb4f-225">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-225">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="5fb4f-226">Selezionare il testo `gre` nella <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5.  <span data-ttu-id="5fb4f-227">Trascinare il testo su un controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="5fb4f-228">Notare che ora il cursore cambia aspetto per indicare che il trascinamento non è consentito poiché `gre` non è un colore valido.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="5fb4f-229">È possibile migliorare ulteriormente l'esperienza utente applicando un'anteprima dell'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="5fb4f-230">Per il controllo utente Circle, si eseguirà l'override di <xref:System.Windows.UIElement.OnDragEnter%2A> e <xref:System.Windows.UIElement.OnDragLeave%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="5fb4f-231">Quando i dati vengono trascinati sul controllo, lo sfondo corrente <xref:System.Windows.Shapes.Shape.Fill%2A> viene salvato in una variabile segnaposto.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="5fb4f-232">La stringa viene quindi convertita in un pennello e applicata al <xref:System.Windows.Shapes.Ellipse> che fornisce il cerchio dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="5fb4f-233">Se i dati vengono trascinati all'esterno del cerchio senza essere rilasciati, originale <xref:System.Windows.Shapes.Shape.Fill%2A> valore viene nuovamente applicato al controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="5fb4f-234">Per visualizzare in anteprima gli effetti dell'operazione di trascinamento</span><span class="sxs-lookup"><span data-stu-id="5fb4f-234">To preview the effects of the drag-and-drop operation</span></span>

1.  <span data-ttu-id="5fb4f-235">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="5fb4f-236">Nella classe Circle dichiarare una privata <xref:System.Windows.Media.Brush> variabile denominata `_previousFill` e inizializzarla su `null`.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3.  <span data-ttu-id="5fb4f-237">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDragEnter%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.DragEnter> evento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="5fb4f-238">Ciò <xref:System.Windows.UIElement.OnDragEnter%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fb4f-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="5fb4f-239">Salva il <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà del <xref:System.Windows.Shapes.Ellipse> nel `_previousFill` variabile.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    -   <span data-ttu-id="5fb4f-240">Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se i dati possono essere convertiti in un <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    -   <span data-ttu-id="5fb4f-241">Se i dati vengono convertiti in un oggetto valido <xref:System.Windows.Media.Brush>, viene applicata al <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4.  <span data-ttu-id="5fb4f-242">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDragLeave%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.DragLeave> evento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="5fb4f-243">Ciò <xref:System.Windows.UIElement.OnDragLeave%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fb4f-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="5fb4f-244">Si applica il <xref:System.Windows.Media.Brush> salvato nel `_previousFill` variabili per il <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5.  <span data-ttu-id="5fb4f-245">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-245">Press **F5** to build and run the application.</span></span>

6.  <span data-ttu-id="5fb4f-246">Selezionare il testo `green` nella <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7.  <span data-ttu-id="5fb4f-247">Trascinare il testo su un controllo Circle senza rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="5fb4f-248">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="5fb4f-249">![Visualizzare in anteprima gli effetti di un'operazione di trascinamento](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="5fb4f-249">![Preview the effects of a drag&#45;and&#45;drop operation](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8.  <span data-ttu-id="5fb4f-250">Trascinare il testo dal controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="5fb4f-251">Il controllo Circle passa da verde a blu.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="5fb4f-252">Abilitare un pannello di ricevere dati rilasciati</span><span class="sxs-lookup"><span data-stu-id="5fb4f-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="5fb4f-253">In questa sezione si abilita i pannelli di ospitano controlli utente Circle per fungere da destinazioni di rilascio per i dati Circle trascinati.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="5fb4f-254">Si implementerà codice che consente di spostare un controllo Circle da un pannello a altro o per creare una copia di un controllo Circle tenendo premuto il **Ctrl** chiave durante il trascinamento della selezione di un cerchio.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1.  <span data-ttu-id="5fb4f-255">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-255">Open MainWindow.xaml.</span></span>

2.  <span data-ttu-id="5fb4f-256">Come illustrato nella finestra di XAML seguente, in ognuna delle <xref:System.Windows.Controls.StackPanel> (controlli), aggiungere i gestori per il <xref:System.Windows.UIElement.DragOver> e <xref:System.Windows.UIElement.Drop> eventi.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="5fb4f-257">Nome di <xref:System.Windows.UIElement.DragOver> gestore eventi `panel_DragOver`e assegnare un nome il <xref:System.Windows.UIElement.Drop> gestore eventi, `panel_Drop`.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3.  <span data-ttu-id="5fb4f-258">Aprire MainWindows.xaml.cs o MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4.  <span data-ttu-id="5fb4f-259">Aggiungere il codice seguente per il <xref:System.Windows.UIElement.DragOver> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="5fb4f-260">Ciò <xref:System.Windows.UIElement.DragOver> gestore eventi esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fb4f-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    -   <span data-ttu-id="5fb4f-261">Verifica che i dati trascinati contengano i dati "Object" che è stati inseriti nel <xref:System.Windows.DataObject> dal controllo utente Circle e passati nella chiamata a <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    -   <span data-ttu-id="5fb4f-262">Se i dati "Object" sono presenti, controlla se il **Ctrl** viene premuto.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    -   <span data-ttu-id="5fb4f-263">Se il **Ctrl** viene premuto, imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Copy>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="5fb4f-264">In caso contrario, impostare il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5.  <span data-ttu-id="5fb4f-265">Aggiungere il codice seguente per il <xref:System.Windows.UIElement.Drop> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="5fb4f-266">Ciò <xref:System.Windows.UIElement.Drop> gestore eventi esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fb4f-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    -   <span data-ttu-id="5fb4f-267">Controlla se il <xref:System.Windows.UIElement.Drop> evento è già stato gestito.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="5fb4f-268">Ad esempio, se viene eliminato un cerchio in un'altra Circle che gestisce il <xref:System.Windows.UIElement.Drop> evento, non si desidera il pannello che contiene il controllo Circle anche gestirla.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    -   <span data-ttu-id="5fb4f-269">Se il <xref:System.Windows.UIElement.Drop> evento non è gestito, controlla se il **Ctrl** viene premuto.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    -   <span data-ttu-id="5fb4f-270">Se il **Ctrl** premuto quando il <xref:System.Windows.UIElement.Drop> avviene, viene creata una copia del cerchio di controllo e aggiungerlo al <xref:System.Windows.Controls.Panel.Children%2A> raccolta del <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    -   <span data-ttu-id="5fb4f-271">Se il **Ctrl** non viene premuto, sposta il controllo Circle dal <xref:System.Windows.Controls.Panel.Children%2A> del pannello padre alla raccolta di <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello che è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    -   <span data-ttu-id="5fb4f-272">Set il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà per notificare il <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo indica se è stata eseguita un'operazione di copia o spostamento.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6.  <span data-ttu-id="5fb4f-273">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-273">Press **F5** to build and run the application.</span></span>

7.  <span data-ttu-id="5fb4f-274">Selezionare il testo `green` dal <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8.  <span data-ttu-id="5fb4f-275">Trascinare il testo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="5fb4f-276">Trascinare un controllo Circle dal pannello di sinistra al pannello di destra e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="5fb4f-277">Il controllo Circle viene rimosso dal <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello a sinistra e aggiunto alla raccolta Children del Pannello di destra.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="5fb4f-278">Trascinare un controllo Circle dal Pannello di cui si trova a altro pannello e rilasciarlo mentre si tiene premuto il **Ctrl** chiave.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="5fb4f-279">Il controllo Circle viene copiato e la copia viene aggiunto al <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello del ricevente.</span><span class="sxs-lookup"><span data-stu-id="5fb4f-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="5fb4f-280">![Trascinamento di un controllo Circle mentre si preme CTRL](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="5fb4f-280">![Dragging a Circle while pressing the CTRL key](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="5fb4f-281">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fb4f-281">See Also</span></span>

- [<span data-ttu-id="5fb4f-282">Cenni preliminari sul trascinamento della selezione</span><span class="sxs-lookup"><span data-stu-id="5fb4f-282">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)