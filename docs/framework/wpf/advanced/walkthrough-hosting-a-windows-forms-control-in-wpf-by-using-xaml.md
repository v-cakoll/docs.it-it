---
title: Ospitare un controllo Windows Forms in WPF tramite XAML
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 99c077801a26043e17e0d51ecc0a97b9608784c0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095060"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="93ffa-102">Procedura dettagliata: hosting di controlli Windows Form in WPF tramite XAML</span><span class="sxs-lookup"><span data-stu-id="93ffa-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="93ffa-103">offre numerosi controlli con un insieme di funzionalità completo.</span><span class="sxs-lookup"><span data-stu-id="93ffa-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="93ffa-104">Tuttavia, a volte può essere opportuno usare Windows Forms controlli nelle pagine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93ffa-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="93ffa-105">Ad esempio, è possibile che si disponga di un investimento sostanziale nei controlli di Windows Forms esistenti o che si disponga di un controllo Windows Forms che fornisce funzionalità univoche.</span><span class="sxs-lookup"><span data-stu-id="93ffa-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="93ffa-106">In questa procedura dettagliata viene illustrato come ospitare un controllo <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> di Windows Forms in una pagina [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93ffa-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="93ffa-107">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [hosting di un controllo Windows Forms in WPF usando l'esempio XAML](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span><span class="sxs-lookup"><span data-stu-id="93ffa-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="93ffa-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="93ffa-108">Prerequisites</span></span>  

<span data-ttu-id="93ffa-109">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="93ffa-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="93ffa-110">Hosting del controllo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93ffa-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="93ffa-111">Per ospitare il controllo MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="93ffa-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="93ffa-112">Creare un progetto di applicazione WPF denominato `HostingWfInWpfWithXaml`.</span><span class="sxs-lookup"><span data-stu-id="93ffa-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="93ffa-113">Aggiungere riferimenti agli assembly indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="93ffa-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="93ffa-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="93ffa-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="93ffa-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="93ffa-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="93ffa-116">Aprire MainWindow. XAML in WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="93ffa-116">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
4. <span data-ttu-id="93ffa-117">Nell'elemento <xref:System.Windows.Window> aggiungere il mapping dello spazio dei nomi seguente.</span><span class="sxs-lookup"><span data-stu-id="93ffa-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="93ffa-118">Il mapping dello spazio dei nomi `wf` stabilisce un riferimento all'assembly che contiene il controllo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="93ffa-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="93ffa-119">Nell'elemento <xref:System.Windows.Controls.Grid> aggiungere il codice XAML seguente.</span><span class="sxs-lookup"><span data-stu-id="93ffa-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="93ffa-120">Il controllo <xref:System.Windows.Forms.MaskedTextBox> viene creato come elemento figlio del controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="93ffa-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="93ffa-121">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="93ffa-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93ffa-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93ffa-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="93ffa-123">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93ffa-123">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="93ffa-124">Procedura dettagliata: hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="93ffa-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="93ffa-125">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="93ffa-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="93ffa-126">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="93ffa-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="93ffa-127">Controlli Windows Form e controlli WPF equivalenti</span><span class="sxs-lookup"><span data-stu-id="93ffa-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="93ffa-128">Hosting di un controllo Windows Forms in WPF usando l'esempio XAML</span><span class="sxs-lookup"><span data-stu-id="93ffa-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)
