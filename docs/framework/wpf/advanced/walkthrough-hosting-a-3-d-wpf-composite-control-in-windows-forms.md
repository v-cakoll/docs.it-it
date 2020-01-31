---
title: Ospitare il controllo composito 3D WPF in Windows Forms
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: 07222809d62b207730ddad3c87b8fb60e1602bc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744459"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="f0a36-102">Procedura dettagliata: ospitare un controllo composito 3D WPF in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0a36-102">Walkthrough: Host a 3D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="f0a36-103">In questa procedura dettagliata viene illustrato come creare un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composito e ospitarlo in controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e form usando il controllo <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="f0a36-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="f0a36-104">In questa procedura dettagliata verrà implementato un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> contenente due controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="f0a36-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="f0a36-105">Il <xref:System.Windows.Controls.UserControl> Visualizza un cono tridimensionale (3D).</span><span class="sxs-lookup"><span data-stu-id="f0a36-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3D) cone.</span></span> <span data-ttu-id="f0a36-106">Il rendering degli oggetti 3D è molto più semplice con il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rispetto a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0a36-106">Rendering 3D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="f0a36-107">È pertanto consigliabile ospitare una classe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> per creare grafica 3D in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0a36-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="f0a36-108">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0a36-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="f0a36-109">Creazione della <xref:System.Windows.Controls.UserControl>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0a36-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="f0a36-110">Creazione del progetto host Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f0a36-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="f0a36-111">Hosting della <xref:System.Windows.Controls.UserControl>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0a36-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0a36-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f0a36-112">Prerequisites</span></span>

<span data-ttu-id="f0a36-113">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0a36-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="f0a36-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="f0a36-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="f0a36-115">Creare UserControl</span><span class="sxs-lookup"><span data-stu-id="f0a36-115">Create the UserControl</span></span>

1. <span data-ttu-id="f0a36-116">Creare un progetto **libreria di controlli utente WPF** denominato `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="f0a36-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="f0a36-117">Aprire UserControl1. XAML in WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="f0a36-117">Open UserControl1.xaml in the WPF Designer.</span></span>

3. <span data-ttu-id="f0a36-118">Sostituire il codice generato con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f0a36-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="f0a36-119">Questo codice definisce una <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> che contiene due controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="f0a36-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="f0a36-120">Il primo controllo figlio è un controllo <xref:System.Windows.Controls.Label?displayProperty=nameWithType>; il secondo è un controllo <xref:System.Windows.Controls.Viewport3D> che visualizza un cono 3D.</span><span class="sxs-lookup"><span data-stu-id="f0a36-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="f0a36-121">Creare il progetto host</span><span class="sxs-lookup"><span data-stu-id="f0a36-121">Create the host project</span></span>

1. <span data-ttu-id="f0a36-122">Aggiungere un progetto di **App Windows Forms (.NET Framework)** denominato `WpfUserControlHost` alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="f0a36-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="f0a36-123">In **Esplora soluzioni**aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="f0a36-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="f0a36-124">Aggiungere i riferimenti agli assembly [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0a36-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="f0a36-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="f0a36-125">PresentationCore</span></span>

    - <span data-ttu-id="f0a36-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="f0a36-126">PresentationFramework</span></span>

    - <span data-ttu-id="f0a36-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="f0a36-127">WindowsBase</span></span>

4. <span data-ttu-id="f0a36-128">Aggiungere un riferimento al progetto `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="f0a36-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="f0a36-129">In Esplora soluzioni impostare il progetto `WpfUserControlHost` come progetto di avvio.</span><span class="sxs-lookup"><span data-stu-id="f0a36-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="f0a36-130">Ospitare UserControl</span><span class="sxs-lookup"><span data-stu-id="f0a36-130">Host the UserControl</span></span>

1. <span data-ttu-id="f0a36-131">Nella Progettazione Windows Form aprire Form1.</span><span class="sxs-lookup"><span data-stu-id="f0a36-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="f0a36-132">Nella Finestra Proprietà fare clic su **eventi**, quindi fare doppio clic sull'evento <xref:System.Windows.Forms.Form.Load> per creare un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f0a36-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="f0a36-133">Viene aperto l'editor di codice per il gestore dell'evento `Form1_Load` appena generato.</span><span class="sxs-lookup"><span data-stu-id="f0a36-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="f0a36-134">Sostituire il codice in Form1.cs con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f0a36-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="f0a36-135">Il gestore dell'evento `Form1_Load` crea un'istanza di `UserControl1` e aggiunge alla raccolta dei controlli figlio del controllo <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="f0a36-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="f0a36-136">Il controllo <xref:System.Windows.Forms.Integration.ElementHost> viene aggiunto alla raccolta di controlli figlio del form.</span><span class="sxs-lookup"><span data-stu-id="f0a36-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="f0a36-137">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f0a36-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0a36-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0a36-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="f0a36-139">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f0a36-139">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="f0a36-140">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f0a36-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="f0a36-141">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="f0a36-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="f0a36-142">Hosting di un controllo composito WPF nell'esempio Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0a36-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
