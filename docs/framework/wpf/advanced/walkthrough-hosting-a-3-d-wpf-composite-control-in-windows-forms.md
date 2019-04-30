---
title: 'Procedura dettagliata: Hosting di un controllo composito WPF 3D in Windows Form'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: e5b98a33f29759a81ba1cbc1fefbd45c0e5bf736
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007149"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="1ad3c-102">Procedura dettagliata: Hosting di un controllo composito WPF 3D in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1ad3c-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="1ad3c-103">Questa procedura dettagliata illustra come creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composito controllano e ospitarlo in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] form e controlli tramite il <xref:System.Windows.Forms.Integration.ElementHost> controllo.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="1ad3c-104">In questa procedura dettagliata verrà implementata una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> che contiene due controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="1ad3c-105">Il <xref:System.Windows.Controls.UserControl> Visualizza un cono tridimensionale (3D).</span><span class="sxs-lookup"><span data-stu-id="1ad3c-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="1ad3c-106">Il rendering di oggetti 3D è molto più semplice con il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rispetto a con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ad3c-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="1ad3c-107">Pertanto, è logico all'host un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> classe per creare grafica 3D nel [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ad3c-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="1ad3c-108">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ad3c-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="1ad3c-109">Creazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="1ad3c-110">Creazione del progetto host Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="1ad3c-111">Hosting di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ad3c-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1ad3c-112">Prerequisites</span></span>

<span data-ttu-id="1ad3c-113">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ad3c-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="1ad3c-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="1ad3c-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="1ad3c-115">Creare la classe UserControl</span><span class="sxs-lookup"><span data-stu-id="1ad3c-115">Create the UserControl</span></span>

1. <span data-ttu-id="1ad3c-116">Creare un **libreria di controlli utente WPF** progetto denominato `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="1ad3c-117">Aprire UserControl1.xaml nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ad3c-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3. <span data-ttu-id="1ad3c-118">Sostituire il codice generato con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1ad3c-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="1ad3c-119">Questo codice definisce un <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> che contiene due controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="1ad3c-120">Il primo controllo figlio è un <xref:System.Windows.Controls.Label?displayProperty=nameWithType> controllo; il secondo è un <xref:System.Windows.Controls.Viewport3D> controllo che visualizza un cono 3D.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="1ad3c-121">Creare il progetto host</span><span class="sxs-lookup"><span data-stu-id="1ad3c-121">Create the host project</span></span>

1. <span data-ttu-id="1ad3c-122">Aggiungere un **App WPF (.NET Framework)** progetto denominato `WpfUserControlHost` alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-122">Add a **WPF App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span> <span data-ttu-id="1ad3c-123">Per altre informazioni, vedere [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="1ad3c-123">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="1ad3c-124">Nelle **Esplora soluzioni**, aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-124">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="1ad3c-125">Aggiungere i riferimenti ai seguenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assembly:</span><span class="sxs-lookup"><span data-stu-id="1ad3c-125">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="1ad3c-126">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="1ad3c-126">PresentationCore</span></span>

    - <span data-ttu-id="1ad3c-127">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="1ad3c-127">PresentationFramework</span></span>

    - <span data-ttu-id="1ad3c-128">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="1ad3c-128">WindowsBase</span></span>

4. <span data-ttu-id="1ad3c-129">Aggiungere un riferimento al progetto `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-129">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="1ad3c-130">In Esplora soluzioni, impostare il `WpfUserControlHost` progetto come progetto di avvio.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-130">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="1ad3c-131">Ospitare il controllo UserControl</span><span class="sxs-lookup"><span data-stu-id="1ad3c-131">Host the UserControl</span></span>

1. <span data-ttu-id="1ad3c-132">Aprire Form1 in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-132">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="1ad3c-133">Nella finestra Proprietà, fare clic su **eventi**e quindi fare doppio clic il <xref:System.Windows.Forms.Form.Load> eventi per creare un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-133">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="1ad3c-134">Si apre l'Editor di codice appena generato `Form1_Load` gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-134">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="1ad3c-135">Sostituire il codice in Form1.cs con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-135">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="1ad3c-136">Il `Form1_Load` gestore eventi crea un'istanza di `UserControl1` e aggiunge ripristinare il <xref:System.Windows.Forms.Integration.ElementHost> insieme di controlli figlio del controllo.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-136">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="1ad3c-137">Il <xref:System.Windows.Forms.Integration.ElementHost> controllo viene aggiunto alla raccolta del modulo dei controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-137">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="1ad3c-138">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1ad3c-138">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ad3c-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ad3c-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="1ad3c-140">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1ad3c-140">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="1ad3c-141">Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1ad3c-141">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="1ad3c-142">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="1ad3c-142">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="1ad3c-143">Hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1ad3c-143">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)