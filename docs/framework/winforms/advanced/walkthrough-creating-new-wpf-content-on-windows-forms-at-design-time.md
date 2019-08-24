---
title: 'Procedura dettagliata: Creazione di nuovo contenuto WPF in Windows Form in fase di progettazione'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5e5112aa0b025648ce68a93f0f3da026ec99fe89
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987140"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="3ac34-102">Procedura dettagliata: Crea nuovo contenuto WPF in Windows Forms in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="3ac34-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="3ac34-103">Questo articolo illustra come creare un controllo Windows Presentation Foundation (WPF) da usare nelle applicazioni basate su Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3ac34-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ac34-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3ac34-104">Prerequisites</span></span>

<span data-ttu-id="3ac34-105">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3ac34-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="3ac34-106">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="3ac34-106">Create the project</span></span>

<span data-ttu-id="3ac34-107">Aprire Visual Studio e creare un nuovo progetto di **App Windows Forms (.NET Framework)** in Visual Basic o C# in `HostingWpf`un oggetto visivo denominato.</span><span class="sxs-lookup"><span data-stu-id="3ac34-107">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="3ac34-108">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3ac34-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="3ac34-109">Creare un nuovo controllo WPF</span><span class="sxs-lookup"><span data-stu-id="3ac34-109">Create a new WPF control</span></span>

<span data-ttu-id="3ac34-110">Creare un nuovo controllo WPF e aggiungerlo al progetto è facile come aggiungere qualsiasi altro elemento.</span><span class="sxs-lookup"><span data-stu-id="3ac34-110">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="3ac34-111">Il Progettazione Windows Form funziona con un particolare tipo di controllo denominato *controllo composito*o *controllo utente*.</span><span class="sxs-lookup"><span data-stu-id="3ac34-111">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="3ac34-112">Per altre informazioni sui controlli utente WPF, vedere <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="3ac34-112">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="3ac34-113">Il tipo <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> per WPF è distinto dal tipo di controllo utente fornito da Windows Form, denominato anch'esso <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ac34-113">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="3ac34-114">Per creare un nuovo controllo WPF:</span><span class="sxs-lookup"><span data-stu-id="3ac34-114">To create a new WPF control:</span></span>

1. <span data-ttu-id="3ac34-115">In **Esplora soluzioni**aggiungere un nuovo progetto di **libreria di controlli utente (.NET Framework) WPF** alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="3ac34-115">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="3ac34-116">Usare il nome predefinito per la libreria di controlli, `WpfControlLibrary1`.</span><span class="sxs-lookup"><span data-stu-id="3ac34-116">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="3ac34-117">Il nome predefinito del controllo è `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="3ac34-117">The default control name is `UserControl1.xaml`.</span></span>

   <span data-ttu-id="3ac34-118">L'aggiunta del nuovo controllo ha gli effetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ac34-118">Adding the new control has the following effects:</span></span>

   - <span data-ttu-id="3ac34-119">Viene aggiunto il file UserControl1.xaml.</span><span class="sxs-lookup"><span data-stu-id="3ac34-119">File UserControl1.xaml is added.</span></span>

   - <span data-ttu-id="3ac34-120">Viene aggiunto il file UserControl1.xaml.cs (o UserControl1. XAML. vb).</span><span class="sxs-lookup"><span data-stu-id="3ac34-120">File UserControl1.xaml.cs (or UserControl1.xaml.vb) is added.</span></span> <span data-ttu-id="3ac34-121">Questo file contiene il code-behind per i gestori eventi e l'altra implementazione.</span><span class="sxs-lookup"><span data-stu-id="3ac34-121">This file contains the code-behind for event handlers and other implementation.</span></span>

   - <span data-ttu-id="3ac34-122">Vengono aggiunti riferimenti agli assembly WPF.</span><span class="sxs-lookup"><span data-stu-id="3ac34-122">References to WPF assemblies are added.</span></span>

   - <span data-ttu-id="3ac34-123">Il file UserControl1. XAML viene aperto in WPF Designer per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3ac34-123">File UserControl1.xaml opens in the WPF Designer for Visual Studio.</span></span>

2. <span data-ttu-id="3ac34-124">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="3ac34-124">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="3ac34-125">Nella finestra **Proprietà** impostare il valore delle <xref:System.Windows.FrameworkElement.Width%2A> proprietà e <xref:System.Windows.FrameworkElement.Height%2A> su **200**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-125">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="3ac34-126">Dalla **casella degli strumenti**trascinare un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> controllo nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3ac34-126">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="3ac34-127">Nella finestra **Proprietà** impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà su **contenuto ospitato**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-127">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3ac34-128">In generale, è opportuno ospitare contenuto WPF più sofisticato.</span><span class="sxs-lookup"><span data-stu-id="3ac34-128">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="3ac34-129">Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="3ac34-130">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="3ac34-130">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="3ac34-131">Aggiungere un controllo WPF a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="3ac34-131">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="3ac34-132">Il nuovo controllo WPF è pronto per l'uso sul form.</span><span class="sxs-lookup"><span data-stu-id="3ac34-132">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="3ac34-133">Windows Forms usa il <xref:System.Windows.Forms.Integration.ElementHost> controllo per ospitare il contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="3ac34-133">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="3ac34-134">Per aggiungere un controllo WPF a un Windows Form:</span><span class="sxs-lookup"><span data-stu-id="3ac34-134">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="3ac34-135">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="3ac34-135">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="3ac34-136">Nella **casella degli strumenti**trovare la scheda con etichetta **WPFUserControlLibrary WPF User Controls**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-136">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="3ac34-137">Trascinare un'istanza di `UserControl1` sul form.</span><span class="sxs-lookup"><span data-stu-id="3ac34-137">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="3ac34-138">Un controllo <xref:System.Windows.Forms.Integration.ElementHost> verrà creato automaticamente sul form per ospitare il controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="3ac34-138">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="3ac34-139">Il <xref:System.Windows.Forms.Integration.ElementHost> controllo è denominato `elementHost1` e nella finestra **Proprietà** è possibile vedere che la relativa <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> proprietà è impostata su **UserControl1**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-139">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="3ac34-140">I riferimenti agli assembly WPF vengono aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="3ac34-140">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="3ac34-141">Il controllo `elementHost1` include un pannello smart tag che mostra le opzioni di hosting disponibili.</span><span class="sxs-lookup"><span data-stu-id="3ac34-141">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="3ac34-142">Nel pannello smart tag **attività ElementHost** selezionare **ancora nel contenitore padre**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-142">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="3ac34-143">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ac34-143">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ac34-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3ac34-144">Next steps</span></span>

<span data-ttu-id="3ac34-145">Windows Form e WPF sono tecnologie diverse progettate per interagire strettamente.</span><span class="sxs-lookup"><span data-stu-id="3ac34-145">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="3ac34-146">Per fornire un aspetto e un comportamento più completi nelle applicazioni, provare a eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ac34-146">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="3ac34-147">Ospitare un controllo Windows Form in una pagina WPF.</span><span class="sxs-lookup"><span data-stu-id="3ac34-147">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="3ac34-148">Per altre informazioni, vedere [Procedura dettagliata: Hosting di un controllo Windows Forms in](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)WPF.</span><span class="sxs-lookup"><span data-stu-id="3ac34-148">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="3ac34-149">Applicare stili di visualizzazione Windows Form al contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="3ac34-149">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="3ac34-150">Per altre informazioni, vedere [Procedura: Abilitare gli stili di visualizzazione in un'](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)applicazione ibrida.</span><span class="sxs-lookup"><span data-stu-id="3ac34-150">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="3ac34-151">Modificare lo stile del contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="3ac34-151">Change the style of your WPF content.</span></span> <span data-ttu-id="3ac34-152">Per altre informazioni, vedere [Procedura dettagliata: Applicazione di stili](walkthrough-styling-wpf-content.md)al contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="3ac34-152">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ac34-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ac34-153">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="3ac34-154">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="3ac34-154">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="3ac34-155">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="3ac34-155">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="3ac34-156">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3ac34-156">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
