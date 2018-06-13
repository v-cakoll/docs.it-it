---
title: 'Procedura dettagliata: hosting di controlli Windows Form in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 515135893c0d6cf251977bbddc13241e8b6b60bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546829"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="f1e8e-102">Procedura dettagliata: hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="f1e8e-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="f1e8e-103"> offre numerosi controlli con un insieme di funzionalità completo.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-103"> provides many controls with a rich feature set.</span></span> <span data-ttu-id="f1e8e-104">Tuttavia, può talvolta si desidera utilizzare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ai controlli del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagine.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="f1e8e-105">Ad esempio, è possibile un investimento sostanziale esistente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli o si può disporre di un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo che fornisce funzionalità univoche.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="f1e8e-106">Questa procedura dettagliata viene illustrato come ospitare un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagina tramite codice.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-106">This walkthrough shows you how to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>  
  
 <span data-ttu-id="f1e8e-107">Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [ospita un controllo Windows Form in WPF esempio](http://go.microsoft.com/fwlink/?LinkID=160057).</span><span class="sxs-lookup"><span data-stu-id="f1e8e-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=160057).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f1e8e-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f1e8e-108">Prerequisites</span></span>  
 <span data-ttu-id="f1e8e-109">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1e8e-109">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="f1e8e-110">.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-110">.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="f1e8e-111">Hosting del controllo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f1e8e-111">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="f1e8e-112">Per ospitare il controllo MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="f1e8e-112">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="f1e8e-113">Creare un progetto di applicazione WPF denominato `HostingWfInWpf`.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-113">Create a WPF Application project named `HostingWfInWpf`.</span></span>  
  
2.  <span data-ttu-id="f1e8e-114">Aggiungere riferimenti agli assembly indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-114">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="f1e8e-115">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="f1e8e-115">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="f1e8e-116">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="f1e8e-116">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="f1e8e-117">Aprire MainWindow. XAML nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1e8e-117">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="f1e8e-118">Nome di <xref:System.Windows.Controls.Grid> elemento `grid1`.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-118">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>  
  
     [!code-xaml[HostingWfInWPF#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]  
  
5.  <span data-ttu-id="f1e8e-119">In visualizzazione progettazione o visualizzazione XAML, selezionare il <xref:System.Windows.Window> elemento.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-119">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>  
  
6.  <span data-ttu-id="f1e8e-120">Nella finestra Proprietà fare clic su di **eventi** scheda.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-120">In the Properties window, click the **Events** tab.</span></span>  
  
7.  <span data-ttu-id="f1e8e-121">Fare doppio clic su di <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-121">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
8.  <span data-ttu-id="f1e8e-122">Inserire il codice seguente per gestire il <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-122">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfInWPF#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]  
  
9. <span data-ttu-id="f1e8e-123">Nella parte superiore del file, aggiungere le seguenti `Imports` o `using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-123">At the top of the file, add the following `Imports` or `using` statement.</span></span>  
  
     [!code-csharp[HostingWfInWPF#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]  
  
10. <span data-ttu-id="f1e8e-124">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f1e8e-124">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e8e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1e8e-125">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="f1e8e-126">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="f1e8e-126">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="f1e8e-127">Procedura dettagliata: Hosting di controlli Windows Form in WPF tramite XAML</span><span class="sxs-lookup"><span data-stu-id="f1e8e-127">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)  
 [<span data-ttu-id="f1e8e-128">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="f1e8e-128">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="f1e8e-129">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f1e8e-129">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="f1e8e-130">Controlli Windows Form e controlli WPF equivalenti</span><span class="sxs-lookup"><span data-stu-id="f1e8e-130">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [<span data-ttu-id="f1e8e-131">Esempio di hosting di un controllo Windows Forms in WPF</span><span class="sxs-lookup"><span data-stu-id="f1e8e-131">Hosting a Windows Forms Control in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160057)
