---
title: 'Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: cc5e1acd26763e2dd4324497f5d9ecde216ea975
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "56441463"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="0fa87-102">Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="0fa87-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>

<span data-ttu-id="0fa87-103">Questo argomento descrive come creare un controllo Windows Presentation Foundation (WPF) da usare nelle applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0fa87-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="0fa87-104">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fa87-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="0fa87-105">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="0fa87-105">Create the project.</span></span>

- <span data-ttu-id="0fa87-106">Creare un nuovo controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="0fa87-106">Create a new WPF control.</span></span>

- <span data-ttu-id="0fa87-107">Aggiungere il nuovo controllo WPF a un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0fa87-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="0fa87-108">Il controllo WPF è ospitato in un controllo <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="0fa87-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0fa87-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0fa87-109">Prerequisites</span></span>

<span data-ttu-id="0fa87-110">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fa87-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="0fa87-111">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0fa87-111">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="0fa87-112">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="0fa87-112">Creating the Project</span></span>

<span data-ttu-id="0fa87-113">Il primo passaggio consiste nella creazione del progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0fa87-113">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="0fa87-114">Aprire Visual Studio e creare una nuova **Windows Forms App (.NET Framework)** progetto in Visual Basic o Visual c# denominato `HostingWpf`.</span><span class="sxs-lookup"><span data-stu-id="0fa87-114">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="0fa87-115">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0fa87-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="0fa87-116">Creazione di un nuovo controllo WPF</span><span class="sxs-lookup"><span data-stu-id="0fa87-116">Creating a New WPF Control</span></span>

<span data-ttu-id="0fa87-117">Creare un nuovo controllo WPF e aggiungerlo al progetto è facile come aggiungere qualsiasi altro elemento.</span><span class="sxs-lookup"><span data-stu-id="0fa87-117">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="0fa87-118">Finestra di progettazione Windows Form funziona con un particolare tipo di controllo denominato *controllo composito*, o *controllo utente*.</span><span class="sxs-lookup"><span data-stu-id="0fa87-118">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="0fa87-119">Per altre informazioni sui controlli utente WPF, vedere <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="0fa87-119">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="0fa87-120">Il tipo <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> per WPF è distinto dal tipo di controllo utente fornito da Windows Form, denominato anch'esso <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0fa87-120">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="0fa87-121">Per creare un nuovo controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="0fa87-121">To create a new WPF control</span></span>

1. <span data-ttu-id="0fa87-122">Nelle **Esplora soluzioni**, aggiungere un nuovo **libreria di controlli utente WPF (.NET Framework)** progetto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="0fa87-122">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="0fa87-123">Usare il nome predefinito per la libreria di controlli, `WpfControlLibrary1`.</span><span class="sxs-lookup"><span data-stu-id="0fa87-123">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="0fa87-124">Il nome predefinito del controllo è `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="0fa87-124">The default control name is `UserControl1.xaml`.</span></span>

     <span data-ttu-id="0fa87-125">Aggiunta del nuovo controllo ha gli effetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fa87-125">Adding the new control has the following effects:</span></span>

    - <span data-ttu-id="0fa87-126">Viene aggiunto il file UserControl1.xaml.</span><span class="sxs-lookup"><span data-stu-id="0fa87-126">File UserControl1.xaml is added.</span></span>

    - <span data-ttu-id="0fa87-127">Viene aggiunto il file UserControl1.xaml.cs o UserControl1.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="0fa87-127">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="0fa87-128">Questo file contiene il code-behind per i gestori eventi e l'altra implementazione.</span><span class="sxs-lookup"><span data-stu-id="0fa87-128">This file contains the code-behind for event handlers and other implementation.</span></span>

    - <span data-ttu-id="0fa87-129">Vengono aggiunti riferimenti agli assembly WPF.</span><span class="sxs-lookup"><span data-stu-id="0fa87-129">References to WPF assemblies are added.</span></span>

    - <span data-ttu-id="0fa87-130">Il file UserControl1.xaml viene aperto in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fa87-130">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>

2. <span data-ttu-id="0fa87-131">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="0fa87-131">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="0fa87-132">Per altre informazioni, vedere [Procedura: Selezionare e spostare gli elementi nell'area di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0fa87-132">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="0fa87-133">Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da **200**.</span><span class="sxs-lookup"><span data-stu-id="0fa87-133">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="0fa87-134">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> controllo nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0fa87-134">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="0fa87-135">Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà **contenuto ospitato**.</span><span class="sxs-lookup"><span data-stu-id="0fa87-135">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0fa87-136">In generale, è opportuno ospitare contenuto WPF più sofisticato.</span><span class="sxs-lookup"><span data-stu-id="0fa87-136">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="0fa87-137">Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.</span><span class="sxs-lookup"><span data-stu-id="0fa87-137">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="0fa87-138">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="0fa87-138">Build the project.</span></span>

## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="0fa87-139">Aggiunta di un controllo WPF a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0fa87-139">Adding a WPF Control to a Windows Form</span></span>

<span data-ttu-id="0fa87-140">Il nuovo controllo WPF è pronto per l'uso sul form.</span><span class="sxs-lookup"><span data-stu-id="0fa87-140">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="0fa87-141">Windows Form usa il <xref:System.Windows.Forms.Integration.ElementHost> controllo per ospitare contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="0fa87-141">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="0fa87-142">Per aggiungere un controllo WPF a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0fa87-142">To add a WPF control to a Windows Form</span></span>

1. <span data-ttu-id="0fa87-143">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0fa87-143">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="0fa87-144">Nel **casella degli strumenti**, trovare la scheda con etichettata **controlli utente WPF WPFUserControlLibrary**.</span><span class="sxs-lookup"><span data-stu-id="0fa87-144">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="0fa87-145">Trascinare un'istanza di `UserControl1` sul form.</span><span class="sxs-lookup"><span data-stu-id="0fa87-145">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="0fa87-146">Un controllo <xref:System.Windows.Forms.Integration.ElementHost> verrà creato automaticamente sul form per ospitare il controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="0fa87-146">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="0fa87-147">Il <xref:System.Windows.Forms.Integration.ElementHost> controllo è denominato `elementHost1` e nel **delle proprietà** finestra, è possibile visualizzare relativo <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> è impostata su **UserControl1**.</span><span class="sxs-lookup"><span data-stu-id="0fa87-147">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="0fa87-148">I riferimenti agli assembly WPF vengono aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="0fa87-148">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="0fa87-149">Il controllo `elementHost1` include un pannello smart tag che mostra le opzioni di hosting disponibili.</span><span class="sxs-lookup"><span data-stu-id="0fa87-149">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="0fa87-150">Nel **ElementHost Tasks** pannello smart tag, seleziona **ancora nel contenitore padre**.</span><span class="sxs-lookup"><span data-stu-id="0fa87-150">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="0fa87-151">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0fa87-151">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0fa87-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0fa87-152">Next Steps</span></span>

<span data-ttu-id="0fa87-153">Windows Form e WPF sono tecnologie diverse progettate per interagire strettamente.</span><span class="sxs-lookup"><span data-stu-id="0fa87-153">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="0fa87-154">Per migliorare l'aspetto e comportamento nelle applicazioni, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="0fa87-154">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="0fa87-155">Ospitare un controllo Windows Form in una pagina WPF.</span><span class="sxs-lookup"><span data-stu-id="0fa87-155">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="0fa87-156">Per altre informazioni, vedere [Procedura dettagliata: Controllo che ospita un Windows Form in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="0fa87-156">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="0fa87-157">Applicare stili di visualizzazione Windows Form al contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="0fa87-157">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="0fa87-158">Per altre informazioni, vedere [Procedura: Abilitare gli stili di visualizzazione in un'applicazione ibrida](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span><span class="sxs-lookup"><span data-stu-id="0fa87-158">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="0fa87-159">Modificare lo stile del contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="0fa87-159">Change the style of your WPF content.</span></span> <span data-ttu-id="0fa87-160">Per altre informazioni, vedere [Procedura dettagliata: Applicazione degli stili WPF contenuto](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span><span class="sxs-lookup"><span data-stu-id="0fa87-160">For more information, see [Walkthrough: Styling WPF Content](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0fa87-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fa87-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="0fa87-162">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="0fa87-162">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="0fa87-163">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="0fa87-163">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [<span data-ttu-id="0fa87-164">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0fa87-164">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
