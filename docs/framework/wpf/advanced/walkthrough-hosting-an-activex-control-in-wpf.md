---
title: 'Procedura dettagliata: hosting di un controllo ActiveX in WPF'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc4f577da04fb8ed15bae3c0497b35803a46f08f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="b9128-102">Procedura dettagliata: hosting di un controllo ActiveX in WPF</span><span class="sxs-lookup"><span data-stu-id="b9128-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="b9128-103">Per migliorare l'interazione con i browser, è possibile utilizzare [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controlli il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su.</span><span class="sxs-lookup"><span data-stu-id="b9128-103">To enable improved interaction with browsers, you can use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="b9128-104">Questa procedura dettagliata illustra come è possibile ospitare il [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] come controllo in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagina.</span><span class="sxs-lookup"><span data-stu-id="b9128-104">This walkthrough demonstrates how you can host the [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>  
  
 <span data-ttu-id="b9128-105">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9128-105">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="b9128-106">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="b9128-106">Creating the project.</span></span>  
  
-   <span data-ttu-id="b9128-107">Creazione del controllo ActiveX.</span><span class="sxs-lookup"><span data-stu-id="b9128-107">Creating the ActiveX control.</span></span>  
  
-   <span data-ttu-id="b9128-108">Hosting del controllo ActiveX in una pagina WPF.</span><span class="sxs-lookup"><span data-stu-id="b9128-108">Hosting the ActiveX control on a WPF Page.</span></span>  
  
 <span data-ttu-id="b9128-109">Dopo aver completato questa procedura dettagliata, si sarà in grado di utilizzare [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controlli il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su.</span><span class="sxs-lookup"><span data-stu-id="b9128-109">When you have completed this walkthrough, you will understand how to use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b9128-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b9128-110">Prerequisites</span></span>  
 <span data-ttu-id="b9128-111">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9128-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]<span data-ttu-id="b9128-112"> installato nel computer in cui è installato Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b9128-112"> installed on the computer where Visual Studio is installed.</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="b9128-113">.</span><span class="sxs-lookup"><span data-stu-id="b9128-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="b9128-114">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="b9128-114">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="b9128-115">Per creare e impostare il progetto</span><span class="sxs-lookup"><span data-stu-id="b9128-115">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="b9128-116">Creare un progetto di applicazione WPF denominato `HostingAxInWpf`.</span><span class="sxs-lookup"><span data-stu-id="b9128-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>  
  
2.  <span data-ttu-id="b9128-117">Aggiungere un progetto libreria di controlli Windows Form alla soluzione e denominare il progetto `WmpAxLib`.</span><span class="sxs-lookup"><span data-stu-id="b9128-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>  
  
3.  <span data-ttu-id="b9128-118">Nel progetto WmpAxLib, aggiungere un riferimento all'assembly di Windows Media Player, denominato Wmp.</span><span class="sxs-lookup"><span data-stu-id="b9128-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>  
  
4.  <span data-ttu-id="b9128-119">Aprire il **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="b9128-119">Open the **Toolbox**.</span></span>  
  
5.  <span data-ttu-id="b9128-120">Fare clic del mouse il **della casella degli strumenti**, quindi fare clic su **Scegli elementi**.</span><span class="sxs-lookup"><span data-stu-id="b9128-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>  
  
6.  <span data-ttu-id="b9128-121">Fare clic su di **componenti COM** , selezionare il **Windows Media Player** controllare e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9128-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b9128-122">Il controllo di Windows Media Player viene aggiunto per il **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="b9128-122">The Windows Media Player control is added to the **Toolbox**.</span></span>  
  
7.  <span data-ttu-id="b9128-123">In Esplora soluzioni fare doppio clic su di **UserControl1** file e quindi fare clic su **rinominare**.</span><span class="sxs-lookup"><span data-stu-id="b9128-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>  
  
8.  <span data-ttu-id="b9128-124">Modificare il nome in `WmpAxControl.vb` o `WmpAxControl.cs`, a seconda del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b9128-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>  
  
9. <span data-ttu-id="b9128-125">Se viene richiesto di rinominare tutti i riferimenti, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b9128-125">If you are prompted to rename all references, click **Yes**.</span></span>  
  
## <a name="creating-the-activex-control"></a><span data-ttu-id="b9128-126">Creazione di un controllo ActiveX</span><span class="sxs-lookup"><span data-stu-id="b9128-126">Creating the ActiveX Control</span></span>  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]<span data-ttu-id="b9128-127"> Genera automaticamente un <xref:System.Windows.Forms.AxHost> classe wrapper per un [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controllare quando il controllo viene aggiunto all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="b9128-127"> automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] control when the control is added to a design surface.</span></span> <span data-ttu-id="b9128-128">La procedura seguente viene creato un assembly gestito denominato AxInterop.WMPLib.dll.</span><span class="sxs-lookup"><span data-stu-id="b9128-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>  
  
#### <a name="to-create-the-activex-control"></a><span data-ttu-id="b9128-129">Per creare il controllo ActiveX</span><span class="sxs-lookup"><span data-stu-id="b9128-129">To create the ActiveX control</span></span>  
  
1.  <span data-ttu-id="b9128-130">Aprire WmpAxControl. vb o WmpAxControl.cs in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b9128-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="b9128-131">Dal **della casella degli strumenti**, aggiungere il controllo di Windows Media Player all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="b9128-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>  
  
3.  <span data-ttu-id="b9128-132">Nella finestra Proprietà impostare la proprietà del controllo Windows Media Player <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="b9128-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
4.  <span data-ttu-id="b9128-133">Compilare il progetto di libreria di controllo WmpAxLib.</span><span class="sxs-lookup"><span data-stu-id="b9128-133">Build the WmpAxLib control library project.</span></span>  
  
## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="b9128-134">Hosting del controllo ActiveX in una pagina WPF</span><span class="sxs-lookup"><span data-stu-id="b9128-134">Hosting the ActiveX Control on a WPF Page</span></span>  
  
#### <a name="to-host-the-activex-control"></a><span data-ttu-id="b9128-135">Per ospitare il controllo ActiveX</span><span class="sxs-lookup"><span data-stu-id="b9128-135">To host the ActiveX control</span></span>  
  
1.  <span data-ttu-id="b9128-136">Nel progetto HostingAxInWpf, aggiungere un riferimento all'oggetto generato [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] assembly di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b9128-136">In the HostingAxInWpf project, add a reference to the generated [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] interoperability assembly.</span></span>  
  
     <span data-ttu-id="b9128-137">Questo assembly è denominato AxInterop.WMPLib.dll ed è stato aggiunto alla cartella di Debug del progetto WmpAxLib quando è stato importato il controllo di Windows Media Player.</span><span class="sxs-lookup"><span data-stu-id="b9128-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>  
  
2.  <span data-ttu-id="b9128-138">Aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration.</span><span class="sxs-lookup"><span data-stu-id="b9128-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="b9128-139">Aggiungere un riferimento di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, denominato System.</span><span class="sxs-lookup"><span data-stu-id="b9128-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>  
  
4.  <span data-ttu-id="b9128-140">Aprire MainWindow. XAML in WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="b9128-140">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
5.  <span data-ttu-id="b9128-141">Nome di <xref:System.Windows.Controls.Grid> elemento `grid1`.</span><span class="sxs-lookup"><span data-stu-id="b9128-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>  
  
     [!code-xaml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  <span data-ttu-id="b9128-142">In visualizzazione progettazione o visualizzazione XAML, selezionare il <xref:System.Windows.Window> elemento.</span><span class="sxs-lookup"><span data-stu-id="b9128-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>  
  
7.  <span data-ttu-id="b9128-143">Nella finestra Proprietà fare clic su di **eventi** scheda.</span><span class="sxs-lookup"><span data-stu-id="b9128-143">In the Properties window, click the **Events** tab.</span></span>  
  
8.  <span data-ttu-id="b9128-144">Fare doppio clic su di <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="b9128-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
9. <span data-ttu-id="b9128-145">Inserire il codice seguente per gestire il <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="b9128-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     <span data-ttu-id="b9128-146">Questo codice crea un'istanza del <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllare e aggiunge un'istanza di `AxWindowsMediaPlayer` controllo come figlio.</span><span class="sxs-lookup"><span data-stu-id="b9128-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="b9128-147">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b9128-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9128-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9128-148">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="b9128-149">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="b9128-149">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="b9128-150">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="b9128-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="b9128-151">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b9128-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
