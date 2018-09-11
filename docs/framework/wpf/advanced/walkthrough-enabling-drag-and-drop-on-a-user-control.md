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
ms.openlocfilehash: e151eb7f428fecb330970210fd7addb1603a211f
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44338675"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="61357-102">Procedura dettagliata: abilitare il trascinamento della selezione in un controllo utente</span><span class="sxs-lookup"><span data-stu-id="61357-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>
<span data-ttu-id="61357-103">Questa procedura dettagliata illustra come creare un controllo utente personalizzato che possa partecipare al trasferimento di dati tramite trascinamento in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61357-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="61357-104">In questa procedura dettagliata, si creerà un controllo personalizzato WPF <xref:System.Windows.Controls.UserControl> che rappresenta una forma circolare.</span><span class="sxs-lookup"><span data-stu-id="61357-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="61357-105">Si implementeranno funzionalità nel controllo per consentire il trasferimento di dati tramite trascinamento.</span><span class="sxs-lookup"><span data-stu-id="61357-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="61357-106">Ad esempio, se si trascina da un controllo Circle a un altro, i dati del colore di riempimento vengono copiati dal controllo Circle di origine a quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="61357-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="61357-107">Se si trascina da un controllo Circle a un <xref:System.Windows.Controls.TextBox>, la rappresentazione di stringa del colore di riempimento viene copiata la <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="61357-108">Si creerà inoltre una piccola applicazione che contiene due controlli panel e un <xref:System.Windows.Controls.TextBox> per testare le funzionalità di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="61357-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="61357-109">Si scriverà codice che consente ai pannelli di elaborare i dati Circle rilasciati per permettere di spostare o copiare cerchi dalla raccolta Children di un pannello all'altro.</span><span class="sxs-lookup"><span data-stu-id="61357-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>  
  
 <span data-ttu-id="61357-110">Questa procedura dettagliata illustra le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="61357-110">This walkthrough illustrates the following tasks:</span></span>  
  
-   <span data-ttu-id="61357-111">Creare un controllo utente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="61357-111">Create a custom user control.</span></span>  
  
-   <span data-ttu-id="61357-112">Consentire al controllo utente di essere un'origine di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="61357-112">Enable the user control to be a drag source.</span></span>  
  
-   <span data-ttu-id="61357-113">Consentire al controllo utente di essere un obiettivo di rilascio.</span><span class="sxs-lookup"><span data-stu-id="61357-113">Enable the user control to be a drop target.</span></span>  
  
-   <span data-ttu-id="61357-114">Consentire a un pannello di ricevere dati rilasciati dal controllo utente.</span><span class="sxs-lookup"><span data-stu-id="61357-114">Enable a panel to receive data dropped from the user control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61357-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="61357-115">Prerequisites</span></span>  
 <span data-ttu-id="61357-116">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="61357-116">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="61357-117">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="61357-117">Visual Studio 2010</span></span>  
  
## <a name="creating-the-application-project"></a><span data-ttu-id="61357-118">Creazione del progetto di applicazione</span><span class="sxs-lookup"><span data-stu-id="61357-118">Creating the Application Project</span></span>  
 <span data-ttu-id="61357-119">In questa sezione si creerà l'infrastruttura dell'applicazione, che include una pagina principale con due pannelli e un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
### <a name="to-create-the-project"></a><span data-ttu-id="61357-120">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="61357-120">To create the project</span></span>  
  
1.  <span data-ttu-id="61357-121">Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="61357-121">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="61357-122">Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="61357-122">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="61357-123">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="61357-123">Open MainWindow.xaml.</span></span>  
  
3.  <span data-ttu-id="61357-124">Aggiungere il markup seguente tra l'apertura e chiusura <xref:System.Windows.Controls.Grid> tag.</span><span class="sxs-lookup"><span data-stu-id="61357-124">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>  
  
     <span data-ttu-id="61357-125">Questo markup crea l'interfaccia utente per l'applicazione di prova.</span><span class="sxs-lookup"><span data-stu-id="61357-125">This markup creates the user interface for the test application.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## <a name="adding-a-new-user-control-to-the-project"></a><span data-ttu-id="61357-126">Aggiunta di un nuovo controllo utente al progetto</span><span class="sxs-lookup"><span data-stu-id="61357-126">Adding a New User Control to the Project</span></span>  
 <span data-ttu-id="61357-127">In questa sezione si aggiungerà un nuovo controllo utente al progetto.</span><span class="sxs-lookup"><span data-stu-id="61357-127">In this section, you will add a new user control to the project.</span></span>  
  
### <a name="to-add-a-new-user-control"></a><span data-ttu-id="61357-128">Per aggiungere un nuovo controllo utente</span><span class="sxs-lookup"><span data-stu-id="61357-128">To add a new user control</span></span>  
  
1.  <span data-ttu-id="61357-129">Scegliere **Aggiungi controllo utente** dal menu Progetto.</span><span class="sxs-lookup"><span data-stu-id="61357-129">On the Project menu, select **Add User Control**.</span></span>  
  
2.  <span data-ttu-id="61357-130">Nella finestra di dialogo Aggiungi nuovo elemento modificare il nome in `Circle.xaml` e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="61357-130">In the Add New Item dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>  
  
     <span data-ttu-id="61357-131">Circle.xaml e il relativo code-behind vengono aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="61357-131">Circle.xaml and its code-behind is added to the project.</span></span>  
  
3.  <span data-ttu-id="61357-132">Aprire Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="61357-132">Open Circle.xaml.</span></span>  
  
     <span data-ttu-id="61357-133">Questo file conterrà gli elementi dell'interfaccia utente del controllo utente.</span><span class="sxs-lookup"><span data-stu-id="61357-133">This file will contain the user interface elements of the user control.</span></span>  
  
4.  <span data-ttu-id="61357-134">Aggiungere il markup seguente alla radice <xref:System.Windows.Controls.Grid> per creare un controllo utente semplice con un cerchio blu come interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="61357-134">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  <span data-ttu-id="61357-135">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="61357-135">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
6.  <span data-ttu-id="61357-136">In C# aggiungere il codice seguente dopo il costruttore predefinito per creare un costruttore di copia.</span><span class="sxs-lookup"><span data-stu-id="61357-136">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="61357-137">In Visual Basic aggiungere il codice seguente per creare un costruttore predefinito e un costruttore di copia.</span><span class="sxs-lookup"><span data-stu-id="61357-137">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>  
  
     <span data-ttu-id="61357-138">Per consentire la copia del controllo utente, aggiungere un metodo di costruttore di copia nel file code-behind.</span><span class="sxs-lookup"><span data-stu-id="61357-138">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="61357-139">Nel controllo utente Circle semplificato si copieranno solo il riempimento e le dimensioni del controllo utente.</span><span class="sxs-lookup"><span data-stu-id="61357-139">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### <a name="to-add-the-user-control-to-the-main-window"></a><span data-ttu-id="61357-140">Per aggiungere il controllo utente alla finestra principale</span><span class="sxs-lookup"><span data-stu-id="61357-140">To add the user control to the main window</span></span>  
  
1.  <span data-ttu-id="61357-141">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="61357-141">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="61357-142">Aggiungere il seguente XAML per l'apertura <xref:System.Windows.Window> tag per creare un riferimento a spazio dei nomi XML per l'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="61357-142">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  <span data-ttu-id="61357-143">Nel primo <xref:System.Windows.Controls.StackPanel>, aggiungere il seguente XAML per creare due istanze del controllo utente Circle nel primo pannello.</span><span class="sxs-lookup"><span data-stu-id="61357-143">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     <span data-ttu-id="61357-144">Il codice XAML completo per il pannello è analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="61357-144">The full XAML for the panel looks like the following.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## <a name="implementing-drag-source-events-in-the-user-control"></a><span data-ttu-id="61357-145">Implementazione di eventi di origine di trascinamento nel controllo utente</span><span class="sxs-lookup"><span data-stu-id="61357-145">Implementing Drag Source Events in the User Control</span></span>  
 <span data-ttu-id="61357-146">In questa sezione si eseguirà l'override di <xref:System.Windows.UIElement.OnMouseMove%2A> (metodo) e avviare l'operazione di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="61357-146">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>  
  
 <span data-ttu-id="61357-147">Se viene avviato un trascinamento viene premuto un pulsante del mouse e il mouse viene spostato, verranno inseriti i dati per il trasferimento in un <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="61357-147">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="61357-148">In questo caso, il controllo Circle assemblerà tre elementi di dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.</span><span class="sxs-lookup"><span data-stu-id="61357-148">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="61357-149">Per avviare un'operazione di riempimento</span><span class="sxs-lookup"><span data-stu-id="61357-149">To initiate a drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="61357-150">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="61357-150">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="61357-151">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnMouseMove%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.MouseMove> evento.</span><span class="sxs-lookup"><span data-stu-id="61357-151">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     <span data-ttu-id="61357-152">Ciò <xref:System.Windows.UIElement.OnMouseMove%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="61357-152">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="61357-153">Controlla se il pulsante sinistro del mouse viene premuto mentre il mouse è in movimento.</span><span class="sxs-lookup"><span data-stu-id="61357-153">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>  
  
    -   <span data-ttu-id="61357-154">Assembla i dati Circle in una <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="61357-154">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="61357-155">In questo caso, il controllo Circle assembla tre elementi dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.</span><span class="sxs-lookup"><span data-stu-id="61357-155">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
    -   <span data-ttu-id="61357-156">Chiama il metodo statico <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> metodo per avviare l'operazione di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="61357-156">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="61357-157">Passare i tre parametri seguenti per il <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo:</span><span class="sxs-lookup"><span data-stu-id="61357-157">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>  
  
        -   <span data-ttu-id="61357-158">`dragSource` - Un riferimento a questo controllo.</span><span class="sxs-lookup"><span data-stu-id="61357-158">`dragSource` – A reference to this control.</span></span>  
  
        -   <span data-ttu-id="61357-159">`data` : Le <xref:System.Windows.DataObject> creato nel codice precedente.</span><span class="sxs-lookup"><span data-stu-id="61357-159">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>  
  
        -   <span data-ttu-id="61357-160">`allowedEffects` -Le operazioni di trascinamento e rilascio consentite, che sono <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="61357-160">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="61357-161">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="61357-161">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="61357-162">Fare clic su uno dei controlli Circle e trascinarlo sui pannelli, su altro controllo Circle e <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-162">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="61357-163">Quando viene trascinato sul <xref:System.Windows.Controls.TextBox>, il cursore cambia per indicare un'operazione di spostamento.</span><span class="sxs-lookup"><span data-stu-id="61357-163">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>  
  
5.  <span data-ttu-id="61357-164">Durante il trascinamento di un cerchio sul <xref:System.Windows.Controls.TextBox>, premere il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="61357-164">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the CTRL key.</span></span> <span data-ttu-id="61357-165">Notare come il cursore cambia aspetto per indicare una copia.</span><span class="sxs-lookup"><span data-stu-id="61357-165">Notice how the cursor changes to indicate a copy.</span></span>  
  
6.  <span data-ttu-id="61357-166">Trascinare e rilasciare un controllo Circle sul <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-166">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="61357-167">Rappresentazione di stringa del colore di riempimento del cerchio viene aggiunto il <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-167">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
     <span data-ttu-id="61357-168">![Rappresentazione di stringa del colore di riempimento del controllo Circle](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="61357-168">![String representation of Circle's fill color](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>  
  
 <span data-ttu-id="61357-169">Per impostazione predefinita, il cursore cambierà aspetto durante un'operazione di trascinamento per indicare l'effetto che avrà il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="61357-169">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="61357-170">È possibile personalizzare il feedback fornito all'utente gestendo il <xref:System.Windows.UIElement.GiveFeedback> evento e l'impostazione di un cursore diverso.</span><span class="sxs-lookup"><span data-stu-id="61357-170">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>  
  
### <a name="to-give-feedback-to-the-user"></a><span data-ttu-id="61357-171">Per fornire un feedback all'utente</span><span class="sxs-lookup"><span data-stu-id="61357-171">To give feedback to the user</span></span>  
  
1.  <span data-ttu-id="61357-172">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="61357-172">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="61357-173">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnGiveFeedback%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.GiveFeedback> evento.</span><span class="sxs-lookup"><span data-stu-id="61357-173">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     <span data-ttu-id="61357-174">Ciò <xref:System.Windows.UIElement.OnGiveFeedback%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="61357-174">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="61357-175">Controlla il <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> i valori impostati nell'obiettivo di rilascio <xref:System.Windows.UIElement.DragOver> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="61357-175">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
    -   <span data-ttu-id="61357-176">Impostare un cursore personalizzato in base il <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="61357-176">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="61357-177">Il cursore ha lo scopo di fornire un feedback visivo all'utente sull'effetto che avrà il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="61357-177">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>  
  
3.  <span data-ttu-id="61357-178">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="61357-178">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="61357-179">Trascinare uno del cerchio controlli sui pannelli, su altro controllo Circle e <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-179">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="61357-180">Si noti che i cursori sono ora i cursori personalizzati specificati nella <xref:System.Windows.UIElement.OnGiveFeedback%2A> eseguire l'override.</span><span class="sxs-lookup"><span data-stu-id="61357-180">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>  
  
     <span data-ttu-id="61357-181">![Trascinamento con cursori personalizzati](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="61357-181">![Drag and drop with custom cursors](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>  
  
5.  <span data-ttu-id="61357-182">Selezionare il testo `green` dal <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-182">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
6.  <span data-ttu-id="61357-183">Trascinare il testo `green` su un controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="61357-183">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="61357-184">Notare che vengono visualizzati i cursori predefiniti per indicare gli effetti dell'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="61357-184">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="61357-185">Il cursore di feedback viene sempre impostato dall'origine di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="61357-185">The feedback cursor is always set by the drag source.</span></span>  
  
## <a name="implementing-drop-target-events-in-the-user-control"></a><span data-ttu-id="61357-186">Implementazione di eventi di obiettivo di rilascio nel controllo utente</span><span class="sxs-lookup"><span data-stu-id="61357-186">Implementing Drop Target Events in the User Control</span></span>  
 <span data-ttu-id="61357-187">In questa sezione si specificherà che il controllo utente è un obiettivo di rilascio, si eseguirà l'override dei metodi che consentono al controllo utente di essere un obiettivo di rilascio e si elaboreranno i dati rilasciati sul controllo.</span><span class="sxs-lookup"><span data-stu-id="61357-187">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>  
  
### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="61357-188">Per consentire al controllo utente di essere un obiettivo di rilascio</span><span class="sxs-lookup"><span data-stu-id="61357-188">To enable the user control to be a drop target</span></span>  
  
1.  <span data-ttu-id="61357-189">Aprire Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="61357-189">Open Circle.xaml.</span></span>  
  
2.  <span data-ttu-id="61357-190">Nell'apertura <xref:System.Windows.Controls.UserControl> tag, aggiungere i <xref:System.Windows.UIElement.AllowDrop%2A> proprietà e impostarla su `true`.</span><span class="sxs-lookup"><span data-stu-id="61357-190">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 <span data-ttu-id="61357-191">Il <xref:System.Windows.UIElement.OnDrop%2A> metodo viene chiamato quando il <xref:System.Windows.UIElement.AllowDrop%2A> è impostata su `true` e dati dall'origine di trascinamento vengono rilasciati sul controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="61357-191">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="61357-192">In questo metodo si elaboreranno i dati rilasciati e li si applicheranno al controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="61357-192">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>  
  
### <a name="to-process-the-dropped-data"></a><span data-ttu-id="61357-193">Per elaborare i dati rilasciati</span><span class="sxs-lookup"><span data-stu-id="61357-193">To process the dropped data</span></span>  
  
1.  <span data-ttu-id="61357-194">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="61357-194">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="61357-195">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDrop%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.Drop> evento.</span><span class="sxs-lookup"><span data-stu-id="61357-195">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     <span data-ttu-id="61357-196">Ciò <xref:System.Windows.UIElement.OnDrop%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="61357-196">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="61357-197">Usa il <xref:System.Windows.DataObject.GetDataPresent%2A> metodo per verificare se i dati trascinati contengono un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="61357-197">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>  
  
    -   <span data-ttu-id="61357-198">Usa il <xref:System.Windows.DataObject.GetData%2A> metodo per estrarre i dati stringa, se presente.</span><span class="sxs-lookup"><span data-stu-id="61357-198">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>  
  
    -   <span data-ttu-id="61357-199">Usa un' <xref:System.Windows.Media.BrushConverter> per provare a convertire la stringa in un <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="61357-199">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="61357-200">Se la conversione ha esito positivo, si applica il pennello per il <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="61357-200">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>  
  
    -   <span data-ttu-id="61357-201">Segni di <xref:System.Windows.UIElement.Drop> evento come gestito.</span><span class="sxs-lookup"><span data-stu-id="61357-201">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="61357-202">È necessario contrassegnare l'evento di trascinamento come gestito per segnalare agli altri elementi che ricevono l'evento che questo è stato gestito dal controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="61357-202">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>  
  
3.  <span data-ttu-id="61357-203">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="61357-203">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="61357-204">Selezionare il testo `green` nella <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-204">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="61357-205">Trascinare il testo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="61357-205">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="61357-206">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="61357-206">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="61357-207">![Convertire una stringa in pennello](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="61357-207">![Convert a string to a brush](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>  
  
6.  <span data-ttu-id="61357-208">Digitare il testo `green` nella <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-208">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="61357-209">Selezionare il testo `gre` nella <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-209">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="61357-210">Trascinarlo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="61357-210">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="61357-211">Notare che il cursore cambia aspetto per indicare che è consentito il trascinamento ma il colore del controllo Circle non cambia poiché `gre` non è un colore valido.</span><span class="sxs-lookup"><span data-stu-id="61357-211">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>  
  
9. <span data-ttu-id="61357-212">Trascinare dal controllo Circle verde e rilasciare sul controllo Circle blu.</span><span class="sxs-lookup"><span data-stu-id="61357-212">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="61357-213">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="61357-213">The Circle changes from blue to green.</span></span> <span data-ttu-id="61357-214">Si noti che il cursore visualizzato dipende dal fatto che il <xref:System.Windows.Controls.TextBox> o cerchio è l'origine di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="61357-214">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>  
  
 <span data-ttu-id="61357-215">Impostando il <xref:System.Windows.UIElement.AllowDrop%2A> proprietà `true` ed elabora i dati rilasciati è tutto ciò che è necessaria per consentire un elemento per ottenere un obiettivo di rilascio.</span><span class="sxs-lookup"><span data-stu-id="61357-215">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="61357-216">Per fornire un'esperienza utente migliore, tuttavia, è necessario gestire anche il <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, e <xref:System.Windows.UIElement.DragOver> eventi.</span><span class="sxs-lookup"><span data-stu-id="61357-216">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="61357-217">In questi eventi, è possibile eseguire controlli e offrire feedback all'utente prima che i dati vengono rilasciati.</span><span class="sxs-lookup"><span data-stu-id="61357-217">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>  
  
 <span data-ttu-id="61357-218">Quando i dati vengono rilasciati sul controllo utente Circle, il controllo deve notificare all'origine di trascinamento se può elaborare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="61357-218">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="61357-219">Se il controllo non è in grado di elaborare i dati, deve rifiutare il rilascio.</span><span class="sxs-lookup"><span data-stu-id="61357-219">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="61357-220">A tale scopo, è necessario gestire il <xref:System.Windows.UIElement.DragOver> evento e impostare il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="61357-220">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>  
  
### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="61357-221">Per verificare se il rilascio dei dati è consentito</span><span class="sxs-lookup"><span data-stu-id="61357-221">To verify that the data drop is allowed</span></span>  
  
1.  <span data-ttu-id="61357-222">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="61357-222">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="61357-223">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDragOver%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.DragOver> evento.</span><span class="sxs-lookup"><span data-stu-id="61357-223">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     <span data-ttu-id="61357-224">Ciò <xref:System.Windows.UIElement.OnDragOver%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="61357-224">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="61357-225">Imposta la proprietà <xref:System.Windows.DragEventArgs.Effects%2A> su <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="61357-225">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>  
  
    -   <span data-ttu-id="61357-226">Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se il controllo utente Circle può elaborare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="61357-226">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>  
  
    -   <span data-ttu-id="61357-227">Se il controllo utente può elaborare i dati, imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="61357-227">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="61357-228">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="61357-228">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="61357-229">Selezionare il testo `gre` nella <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-229">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="61357-230">Trascinare il testo su un controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="61357-230">Drag the text to a Circle control.</span></span> <span data-ttu-id="61357-231">Notare che ora il cursore cambia aspetto per indicare che il trascinamento non è consentito poiché `gre` non è un colore valido.</span><span class="sxs-lookup"><span data-stu-id="61357-231">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>  
  
 <span data-ttu-id="61357-232">È possibile migliorare ulteriormente l'esperienza utente applicando un'anteprima dell'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="61357-232">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="61357-233">Per il controllo utente Circle, si eseguirà l'override di <xref:System.Windows.UIElement.OnDragEnter%2A> e <xref:System.Windows.UIElement.OnDragLeave%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="61357-233">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="61357-234">Quando i dati vengono trascinati sul controllo, lo sfondo corrente <xref:System.Windows.Shapes.Shape.Fill%2A> viene salvato in una variabile segnaposto.</span><span class="sxs-lookup"><span data-stu-id="61357-234">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="61357-235">La stringa viene quindi convertita in un pennello e applicata al <xref:System.Windows.Shapes.Ellipse> che fornisce il cerchio dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="61357-235">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="61357-236">Se i dati vengono trascinati all'esterno del cerchio senza essere rilasciati, originale <xref:System.Windows.Shapes.Shape.Fill%2A> valore viene nuovamente applicato al controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="61357-236">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>  
  
### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="61357-237">Per visualizzare in anteprima gli effetti dell'operazione di trascinamento</span><span class="sxs-lookup"><span data-stu-id="61357-237">To preview the effects of the drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="61357-238">Aprire Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="61357-238">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="61357-239">Nella classe Circle dichiarare una privata <xref:System.Windows.Media.Brush> variabile denominata `_previousFill` e inizializzarla su `null`.</span><span class="sxs-lookup"><span data-stu-id="61357-239">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  <span data-ttu-id="61357-240">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDragEnter%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.DragEnter> evento.</span><span class="sxs-lookup"><span data-stu-id="61357-240">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     <span data-ttu-id="61357-241">Ciò <xref:System.Windows.UIElement.OnDragEnter%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="61357-241">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="61357-242">Salva il <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà del <xref:System.Windows.Shapes.Ellipse> nel `_previousFill` variabile.</span><span class="sxs-lookup"><span data-stu-id="61357-242">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>  
  
    -   <span data-ttu-id="61357-243">Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se i dati possono essere convertiti in un <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="61357-243">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="61357-244">Se i dati vengono convertiti in un oggetto valido <xref:System.Windows.Media.Brush>, viene applicata al <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="61357-244">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
4.  <span data-ttu-id="61357-245">Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDragLeave%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.DragLeave> evento.</span><span class="sxs-lookup"><span data-stu-id="61357-245">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     <span data-ttu-id="61357-246">Ciò <xref:System.Windows.UIElement.OnDragLeave%2A> override esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="61357-246">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="61357-247">Si applica il <xref:System.Windows.Media.Brush> salvato nel `_previousFill` variabili per il <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo utente Circle.</span><span class="sxs-lookup"><span data-stu-id="61357-247">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>  
  
5.  <span data-ttu-id="61357-248">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="61357-248">Press F5 to build and run the application.</span></span>  
  
6.  <span data-ttu-id="61357-249">Selezionare il testo `green` nella <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-249">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="61357-250">Trascinare il testo su un controllo Circle senza rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="61357-250">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="61357-251">Il controllo Circle passa da blu a verde.</span><span class="sxs-lookup"><span data-stu-id="61357-251">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="61357-252">![Visualizzare in anteprima gli effetti di un'operazione di trascinamento](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="61357-252">![Preview the effects of a drag&#45;and&#45;drop operation](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>  
  
8.  <span data-ttu-id="61357-253">Trascinare il testo dal controllo Circle.</span><span class="sxs-lookup"><span data-stu-id="61357-253">Drag the text away from the Circle control.</span></span> <span data-ttu-id="61357-254">Il controllo Circle passa da verde a blu.</span><span class="sxs-lookup"><span data-stu-id="61357-254">The Circle changes from green back to blue.</span></span>  
  
## <a name="enabling-a-panel-to-receive-dropped-data"></a><span data-ttu-id="61357-255">Consentire a un pannello di ricevere i dati rilasciati</span><span class="sxs-lookup"><span data-stu-id="61357-255">Enabling a Panel to Receive Dropped Data</span></span>  
 <span data-ttu-id="61357-256">In questa sezione si consentirà ai pannelli di ospitare controlli utente Circle che fungono da obiettivi di rilascio per i dati Circle trascinati.</span><span class="sxs-lookup"><span data-stu-id="61357-256">In this section, you will enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="61357-257">Si implementerà codice che consente di spostare un controllo Circle da un pannello a un altro o di eseguire una copia di un controllo Circle tenendo premuto CTRL mentre lo si trascina.</span><span class="sxs-lookup"><span data-stu-id="61357-257">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the CTRL key while dragging and dropping a Circle.</span></span>  
  
### <a name="to-enable-the-panel-to-be-a-drop-target"></a><span data-ttu-id="61357-258">Per consentire al pannello di essere un obiettivo di rilascio</span><span class="sxs-lookup"><span data-stu-id="61357-258">To enable the panel to be a drop target</span></span>  
  
1.  <span data-ttu-id="61357-259">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="61357-259">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="61357-260">Come illustrato nella finestra di XAML seguente, in ognuna delle <xref:System.Windows.Controls.StackPanel> (controlli), aggiungere i gestori per il <xref:System.Windows.UIElement.DragOver> e <xref:System.Windows.UIElement.Drop> eventi.</span><span class="sxs-lookup"><span data-stu-id="61357-260">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="61357-261">Nome di <xref:System.Windows.UIElement.DragOver> gestore eventi `panel_DragOver`e assegnare un nome il <xref:System.Windows.UIElement.Drop> gestore eventi, `panel_Drop`.</span><span class="sxs-lookup"><span data-stu-id="61357-261">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  <span data-ttu-id="61357-262">Aprire MainWindows.xaml.cs o MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="61357-262">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>  
  
4.  <span data-ttu-id="61357-263">Aggiungere il codice seguente per il <xref:System.Windows.UIElement.DragOver> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="61357-263">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     <span data-ttu-id="61357-264">Ciò <xref:System.Windows.UIElement.DragOver> gestore eventi esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="61357-264">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="61357-265">Verifica che i dati trascinati contengano i dati "Object" che è stati inseriti nel <xref:System.Windows.DataObject> dal controllo utente Circle e passati nella chiamata a <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="61357-265">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>  
  
    -   <span data-ttu-id="61357-266">Se i dati "Object" non sono presenti, controlla se viene premuto CTRL.</span><span class="sxs-lookup"><span data-stu-id="61357-266">If the "Object" data is present, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="61357-267">Se viene premuto il tasto CTRL, imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Copy>.</span><span class="sxs-lookup"><span data-stu-id="61357-267">If the CTRL key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="61357-268">In caso contrario, impostare il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="61357-268">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
5.  <span data-ttu-id="61357-269">Aggiungere il codice seguente per il <xref:System.Windows.UIElement.Drop> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="61357-269">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     <span data-ttu-id="61357-270">Ciò <xref:System.Windows.UIElement.Drop> gestore eventi esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="61357-270">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="61357-271">Controlla se il <xref:System.Windows.UIElement.Drop> evento è già stato gestito.</span><span class="sxs-lookup"><span data-stu-id="61357-271">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="61357-272">Ad esempio, se viene eliminato un cerchio in un'altra Circle che gestisce il <xref:System.Windows.UIElement.Drop> evento, non si desidera il pannello che contiene il controllo Circle anche gestirla.</span><span class="sxs-lookup"><span data-stu-id="61357-272">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>  
  
    -   <span data-ttu-id="61357-273">Se il <xref:System.Windows.UIElement.Drop> evento non è gestito, controlla se viene premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="61357-273">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="61357-274">Se viene premuto il tasto CTRL quando la <xref:System.Windows.UIElement.Drop> avviene, viene creata una copia del cerchio di controllo e aggiungerlo al <xref:System.Windows.Controls.Panel.Children%2A> insieme del <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="61357-274">If the CTRL key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
    -   <span data-ttu-id="61357-275">Se non viene premuto il tasto CTRL, sposta il controllo Circle dal <xref:System.Windows.Controls.Panel.Children%2A> del pannello padre alla raccolta di <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello che è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="61357-275">If the CTRL key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>  
  
    -   <span data-ttu-id="61357-276">Set il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà per notificare il <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo indica se è stata eseguita un'operazione di copia o spostamento.</span><span class="sxs-lookup"><span data-stu-id="61357-276">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>  
  
6.  <span data-ttu-id="61357-277">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="61357-277">Press F5 to build and run the application.</span></span>  
  
7.  <span data-ttu-id="61357-278">Selezionare il testo `green` dal <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61357-278">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="61357-279">Trascinare il testo su un controllo Circle e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="61357-279">Drag the text over a Circle control and drop it.</span></span>  
  
9. <span data-ttu-id="61357-280">Trascinare un controllo Circle dal pannello di sinistra al pannello di destra e rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="61357-280">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="61357-281">Il controllo Circle viene rimosso dal <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello a sinistra e aggiunto alla raccolta Children del Pannello di destra.</span><span class="sxs-lookup"><span data-stu-id="61357-281">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>  
  
10. <span data-ttu-id="61357-282">Trascinare un controllo Circle dal pannello in cui si trova all'altro pannello premendo CTRL.</span><span class="sxs-lookup"><span data-stu-id="61357-282">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the CTRL key.</span></span> <span data-ttu-id="61357-283">Il controllo Circle viene copiato e la copia viene aggiunto al <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello del ricevente.</span><span class="sxs-lookup"><span data-stu-id="61357-283">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>  
  
     <span data-ttu-id="61357-284">![Trascinamento di un controllo Circle mentre si preme CTRL](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="61357-284">![Dragging a Circle while pressing the CTRL key](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61357-285">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61357-285">See Also</span></span>  
 [<span data-ttu-id="61357-286">Cenni preliminari sul trascinamento della selezione</span><span class="sxs-lookup"><span data-stu-id="61357-286">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
