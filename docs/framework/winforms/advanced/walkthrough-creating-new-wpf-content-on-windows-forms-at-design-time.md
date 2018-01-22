---
title: 'Procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc357b8ad1ff450c699878dfffe1fbb6e2440f49
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="f9d59-102">Procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f9d59-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="f9d59-103">Questo argomento descrive come creare un controllo Windows Presentation Foundation (WPF) da usare nelle applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f9d59-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>  
  
 <span data-ttu-id="f9d59-104">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9d59-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="f9d59-105">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="f9d59-105">Create the project.</span></span>  
  
-   <span data-ttu-id="f9d59-106">Creare un nuovo controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="f9d59-106">Create a new WPF control.</span></span>  
  
-   <span data-ttu-id="f9d59-107">Aggiungere il nuovo controllo WPF a un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f9d59-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="f9d59-108">Il controllo WPF è ospitato in un controllo <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="f9d59-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9d59-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="f9d59-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f9d59-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="f9d59-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f9d59-111">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f9d59-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f9d59-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f9d59-112">Prerequisites</span></span>  
 <span data-ttu-id="f9d59-113">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9d59-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="f9d59-114">.</span><span class="sxs-lookup"><span data-stu-id="f9d59-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="f9d59-115">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="f9d59-115">Creating the Project</span></span>  
 <span data-ttu-id="f9d59-116">Il primo passaggio consiste nella creazione del progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f9d59-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9d59-117">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f9d59-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="f9d59-118">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="f9d59-118">To create the project</span></span>  
  
-   <span data-ttu-id="f9d59-119">Creare un nuovo progetto applicazione Windows Forms in Visual Basic o Visual c# denominato `HostingWpf`.</span><span class="sxs-lookup"><span data-stu-id="f9d59-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `HostingWpf`.</span></span>  
  
## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="f9d59-120">Creazione di un nuovo controllo WPF</span><span class="sxs-lookup"><span data-stu-id="f9d59-120">Creating a New WPF Control</span></span>  
 <span data-ttu-id="f9d59-121">Creare un nuovo controllo WPF e aggiungerlo al progetto è facile come aggiungere qualsiasi altro elemento.</span><span class="sxs-lookup"><span data-stu-id="f9d59-121">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="f9d59-122">Progettazione Windows Form funziona con un particolare tipo di controllo denominato *controllo composito*, o *controllo utente*.</span><span class="sxs-lookup"><span data-stu-id="f9d59-122">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="f9d59-123">Per altre informazioni sui controlli utente WPF, vedere <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="f9d59-123">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9d59-124">Il tipo <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> per WPF è distinto dal tipo di controllo utente fornito da Windows Form, denominato anch'esso <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9d59-124">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>  
  
#### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="f9d59-125">Per creare un nuovo controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="f9d59-125">To create a new WPF control</span></span>  
  
1.  <span data-ttu-id="f9d59-126">In **Esplora**, aggiungere un nuovo **libreria di controlli utente WPF** progetto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="f9d59-126">In **Solution Explorer**, add a new **WPF User Control Library** project to the solution.</span></span> <span data-ttu-id="f9d59-127">Usare il nome predefinito per la libreria di controlli, `WpfControlLibrary1`.</span><span class="sxs-lookup"><span data-stu-id="f9d59-127">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="f9d59-128">Il nome predefinito del controllo è `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="f9d59-128">The default control name is `UserControl1.xaml`.</span></span>  
  
     <span data-ttu-id="f9d59-129">L'aggiunta del nuovo controllo ha gli effetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9d59-129">Adding the new control has the following effects.</span></span>  
  
    -   <span data-ttu-id="f9d59-130">Viene aggiunto il file UserControl1.xaml.</span><span class="sxs-lookup"><span data-stu-id="f9d59-130">File UserControl1.xaml is added.</span></span>  
  
    -   <span data-ttu-id="f9d59-131">Viene aggiunto il file UserControl1.xaml.cs o UserControl1.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f9d59-131">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="f9d59-132">Questo file contiene il code-behind per i gestori eventi e l'altra implementazione.</span><span class="sxs-lookup"><span data-stu-id="f9d59-132">This file contains the code-behind for event handlers and other implementation.</span></span>  
  
    -   <span data-ttu-id="f9d59-133">Vengono aggiunti riferimenti agli assembly WPF.</span><span class="sxs-lookup"><span data-stu-id="f9d59-133">References to WPF assemblies are added.</span></span>  
  
    -   <span data-ttu-id="f9d59-134">Il file UserControl1.xaml viene aperto in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9d59-134">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="f9d59-135">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="f9d59-135">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="f9d59-136">Per ulteriori informazioni, vedere [procedura: selezionare e spostare elementi nella finestra di progettazione](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="f9d59-136">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="f9d59-137">Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà `200`.</span><span class="sxs-lookup"><span data-stu-id="f9d59-137">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="f9d59-138">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> controllo sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f9d59-138">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>  
  
5.  <span data-ttu-id="f9d59-139">Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà **contenuto ospitato**.</span><span class="sxs-lookup"><span data-stu-id="f9d59-139">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9d59-140">In generale, è opportuno ospitare contenuto WPF più sofisticato.</span><span class="sxs-lookup"><span data-stu-id="f9d59-140">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="f9d59-141">Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.</span><span class="sxs-lookup"><span data-stu-id="f9d59-141">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
6.  <span data-ttu-id="f9d59-142">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="f9d59-142">Build the project.</span></span>  
  
## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="f9d59-143">Aggiunta di un controllo WPF a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="f9d59-143">Adding a WPF Control to a Windows Form</span></span>  
 <span data-ttu-id="f9d59-144">Il nuovo controllo WPF è pronto per l'uso sul form.</span><span class="sxs-lookup"><span data-stu-id="f9d59-144">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="f9d59-145">Windows Forms usa il controllo <xref:System.Windows.Forms.Integration.ElementHost> per ospitare contenuto WPF</span><span class="sxs-lookup"><span data-stu-id="f9d59-145">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content</span></span>  
  
#### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="f9d59-146">Per aggiungere un controllo WPF a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="f9d59-146">To add a WPF control to a Windows Form</span></span>  
  
1.  <span data-ttu-id="f9d59-147">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f9d59-147">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="f9d59-148">Nel **della casella degli strumenti**, individuare la scheda **controlli utente WPF WPFUserControlLibrary**.</span><span class="sxs-lookup"><span data-stu-id="f9d59-148">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>  
  
3.  <span data-ttu-id="f9d59-149">Trascinare un'istanza di `UserControl1` sul form.</span><span class="sxs-lookup"><span data-stu-id="f9d59-149">Drag an instance of `UserControl1` onto the form.</span></span>  
  
    -   <span data-ttu-id="f9d59-150">Un controllo <xref:System.Windows.Forms.Integration.ElementHost> verrà creato automaticamente sul form per ospitare il controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="f9d59-150">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>  
  
    -   <span data-ttu-id="f9d59-151">Il <xref:System.Windows.Forms.Integration.ElementHost> controllo è denominato `elementHost1` e nel **proprietà** , è possibile visualizzare il relativo <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> è impostata su **UserControl1**.</span><span class="sxs-lookup"><span data-stu-id="f9d59-151">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>  
  
    -   <span data-ttu-id="f9d59-152">I riferimenti agli assembly WPF vengono aggiunti al progetto.</span><span class="sxs-lookup"><span data-stu-id="f9d59-152">References to WPF assemblies are added to the project.</span></span>  
  
    -   <span data-ttu-id="f9d59-153">Il controllo `elementHost1` include un pannello smart tag che mostra le opzioni di hosting disponibili.</span><span class="sxs-lookup"><span data-stu-id="f9d59-153">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>  
  
4.  <span data-ttu-id="f9d59-154">Nel **ElementHost Tasks** pannello smart tag, seleziona **ancora nel contenitore padre**.</span><span class="sxs-lookup"><span data-stu-id="f9d59-154">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>  
  
5.  <span data-ttu-id="f9d59-155">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f9d59-155">Press F5 to build and run the application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f9d59-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f9d59-156">Next Steps</span></span>  
 <span data-ttu-id="f9d59-157">Windows Form e WPF sono tecnologie diverse progettate per interagire strettamente.</span><span class="sxs-lookup"><span data-stu-id="f9d59-157">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="f9d59-158">Per migliorare l'aspetto e il comportamento nelle applicazioni, provare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f9d59-158">To provide richer appearance and behavior in your applications, try the following.</span></span>  
  
-   <span data-ttu-id="f9d59-159">Ospitare un controllo Windows Form in una pagina WPF.</span><span class="sxs-lookup"><span data-stu-id="f9d59-159">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="f9d59-160">Per ulteriori informazioni, vedere [procedura dettagliata: Hosting di un controllo Windows Form in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="f9d59-160">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>  
  
-   <span data-ttu-id="f9d59-161">Applicare stili di visualizzazione Windows Form al contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="f9d59-161">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="f9d59-162">Per altre informazioni, vedere [Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span><span class="sxs-lookup"><span data-stu-id="f9d59-162">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>  
  
-   <span data-ttu-id="f9d59-163">Modificare lo stile del contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="f9d59-163">Change the style of your WPF content.</span></span> <span data-ttu-id="f9d59-164">Per ulteriori informazioni, vedere [procedura dettagliata: applicazione di stili del contenuto WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span><span class="sxs-lookup"><span data-stu-id="f9d59-164">For more information, see [Walkthrough: Styling WPF Content](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d59-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9d59-165">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="f9d59-166">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f9d59-166">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="f9d59-167">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="f9d59-167">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="f9d59-168">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="f9d59-168">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
