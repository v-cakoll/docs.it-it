---
title: 'Procedura dettagliata: hosting di controlli compositi 3D di WPF in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: a9aca5d1aff1057d85509be517bb352b4b27bf9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548207"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="3f5d0-102">Procedura dettagliata: hosting di controlli compositi 3D di WPF in Windows Form</span><span class="sxs-lookup"><span data-stu-id="3f5d0-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>
<span data-ttu-id="3f5d0-103">Questa procedura dettagliata illustra come creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composito controllare e inserirlo in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] form e controlli tramite il <xref:System.Windows.Forms.Integration.ElementHost> controllo.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
 <span data-ttu-id="3f5d0-104">In questa procedura dettagliata, verrà implementata una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> che contiene due controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="3f5d0-105">Il <xref:System.Windows.Controls.UserControl> consente di visualizzare un cono tridimensionale (3D).</span><span class="sxs-lookup"><span data-stu-id="3f5d0-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="3f5d0-106">Il rendering di oggetti 3D è molto più semplice con la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rispetto con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f5d0-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="3f5d0-107">È pertanto utile per ospitare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> classe per creare la grafica 3D in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f5d0-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
 <span data-ttu-id="3f5d0-108">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f5d0-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="3f5d0-109">Creazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>  
  
-   <span data-ttu-id="3f5d0-110">Creazione del progetto host Windows Form.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-110">Creating the Windows Forms host project.</span></span>  
  
-   <span data-ttu-id="3f5d0-111">Hosting di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>  
  
 <span data-ttu-id="3f5d0-112">Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [ospita un controllo composito WPF 3D in Windows Form](http://go.microsoft.com/fwlink/?LinkID=160001).</span><span class="sxs-lookup"><span data-stu-id="3f5d0-112">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a 3-D WPF Composite Control in Windows Forms Sample](http://go.microsoft.com/fwlink/?LinkID=160001).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3f5d0-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3f5d0-113">Prerequisites</span></span>  
 <span data-ttu-id="3f5d0-114">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f5d0-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="3f5d0-115">.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-115">.</span></span>  
  
<a name="To_Create_the_UserControl"></a>   
## <a name="creating-the-usercontrol"></a><span data-ttu-id="3f5d0-116">Creazione di UserControl</span><span class="sxs-lookup"><span data-stu-id="3f5d0-116">Creating the UserControl</span></span>  
  
#### <a name="to-create-the-usercontrol"></a><span data-ttu-id="3f5d0-117">Per creare il controllo UserControl</span><span class="sxs-lookup"><span data-stu-id="3f5d0-117">To create the UserControl</span></span>  
  
1.  <span data-ttu-id="3f5d0-118">Creare un progetto libreria di controlli utente WPF denominato `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-118">Create a WPF User Control Library project named `HostingWpfUserControlInWf`.</span></span>  
  
2.  <span data-ttu-id="3f5d0-119">Aprire UserControl1. XAML nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f5d0-119">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
3.  <span data-ttu-id="3f5d0-120">Sostituire il codice generato con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-120">Replace the generated code with the following code.</span></span>  
  
     <span data-ttu-id="3f5d0-121">Questo codice definisce un <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> che contiene due controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-121">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="3f5d0-122">Il primo controllo figlio è un <xref:System.Windows.Controls.Label?displayProperty=nameWithType> controllo; il secondo è un <xref:System.Windows.Controls.Viewport3D> controllo che visualizza un cono 3D.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-122">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>  
  
     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="3f5d0-123">Creazione del progetto host Windows Form</span><span class="sxs-lookup"><span data-stu-id="3f5d0-123">Creating the Windows Forms Host Project</span></span>  
  
#### <a name="to-create-the-host-project"></a><span data-ttu-id="3f5d0-124">Per creare il progetto host</span><span class="sxs-lookup"><span data-stu-id="3f5d0-124">To create the host project</span></span>  
  
1.  <span data-ttu-id="3f5d0-125">Aggiungere un progetto di applicazione Windows denominato `WpfUserControlHost` alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-125">Add a Windows application project named `WpfUserControlHost` to the solution.</span></span> <span data-ttu-id="3f5d0-126">Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="3f5d0-126">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="3f5d0-127">In Esplora soluzioni aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-127">In Solution Explorer, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="3f5d0-128">Aggiungere riferimenti ai seguenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assembly:</span><span class="sxs-lookup"><span data-stu-id="3f5d0-128">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>  
  
    -   <span data-ttu-id="3f5d0-129">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="3f5d0-129">PresentationCore</span></span>  
  
    -   <span data-ttu-id="3f5d0-130">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="3f5d0-130">PresentationFramework</span></span>  
  
    -   <span data-ttu-id="3f5d0-131">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="3f5d0-131">WindowsBase</span></span>  
  
4.  <span data-ttu-id="3f5d0-132">Aggiungere un riferimento al progetto `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-132">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>  
  
5.  <span data-ttu-id="3f5d0-133">In Esplora soluzioni, impostare il `WpfUserControlHost` progetto come progetto di avvio.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-133">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## <a name="hosting-the-windows-presentation-foundation-usercontrol"></a><span data-ttu-id="3f5d0-134">Hosting di Windows Presentation Foundation UserControl</span><span class="sxs-lookup"><span data-stu-id="3f5d0-134">Hosting the Windows Presentation Foundation UserControl</span></span>  
  
#### <a name="to-host-the-usercontrol"></a><span data-ttu-id="3f5d0-135">Per ospitare il controllo UserControl</span><span class="sxs-lookup"><span data-stu-id="3f5d0-135">To host the UserControl</span></span>  
  
1.  <span data-ttu-id="3f5d0-136">In Progettazione Windows Form, aprire Form1.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-136">In the Windows Forms Designer, open Form1.</span></span>  
  
2.  <span data-ttu-id="3f5d0-137">Nella finestra Proprietà fare clic su **eventi**, quindi fare doppio clic sul <xref:System.Windows.Forms.Form.Load> creare un gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-137">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>  
  
     <span data-ttu-id="3f5d0-138">Verrà aperto l'Editor di codice appena generato `Form1_Load` gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-138">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>  
  
3.  <span data-ttu-id="3f5d0-139">Sostituire il codice in Form1. cs con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-139">Replace the code in Form1.cs with the following code.</span></span>  
  
     <span data-ttu-id="3f5d0-140">Il `Form1_Load` gestore eventi crea un'istanza di `UserControl1` e aggiunge OILT il <xref:System.Windows.Forms.Integration.ElementHost> insieme di controlli figlio del controllo.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-140">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="3f5d0-141">Il <xref:System.Windows.Forms.Integration.ElementHost> controllo viene aggiunto alla raccolta del form dei controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-141">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  <span data-ttu-id="3f5d0-142">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3f5d0-142">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f5d0-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f5d0-143">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="3f5d0-144">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="3f5d0-144">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="3f5d0-145">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="3f5d0-145">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="3f5d0-146">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="3f5d0-146">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="3f5d0-147">Hosting di un controllo composito WPF in Windows Form</span><span class="sxs-lookup"><span data-stu-id="3f5d0-147">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160001)
