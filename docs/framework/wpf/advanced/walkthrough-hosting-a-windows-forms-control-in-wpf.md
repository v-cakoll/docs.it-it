---
title: 'Procedura dettagliata: Hosting di un controllo Windows Form in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 4e9b42738ff661425b05a63f2a5e5790c5cbd84b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311916"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="94ddf-102">Procedura dettagliata: Hosting di un controllo Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="94ddf-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="94ddf-103">offre numerosi controlli con un insieme di funzionalità completo.</span><span class="sxs-lookup"><span data-stu-id="94ddf-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="94ddf-104">Tuttavia, può a volte si desidera utilizzare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ai controlli di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagine.</span><span class="sxs-lookup"><span data-stu-id="94ddf-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="94ddf-105">Ad esempio, potrebbe essere un investimento sostanziale nella esistente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli o si può avere un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo che fornisce funzionalità univoche.</span><span class="sxs-lookup"><span data-stu-id="94ddf-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>

<span data-ttu-id="94ddf-106">Questa procedura dettagliata viene illustrato come ospitare un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagina tramite il codice.</span><span class="sxs-lookup"><span data-stu-id="94ddf-106">This walkthrough shows you how to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="94ddf-107">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Hosting di controlli Windows Form in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span><span class="sxs-lookup"><span data-stu-id="94ddf-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94ddf-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="94ddf-108">Prerequisites</span></span>

<span data-ttu-id="94ddf-109">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="94ddf-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="94ddf-110">Hosting del controllo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94ddf-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="94ddf-111">Per ospitare il controllo MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="94ddf-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="94ddf-112">Creare un progetto di applicazione WPF denominato `HostingWfInWpf`.</span><span class="sxs-lookup"><span data-stu-id="94ddf-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="94ddf-113">Aggiungere riferimenti agli assembly indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="94ddf-113">Add references to the following assemblies.</span></span>

    -   <span data-ttu-id="94ddf-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="94ddf-114">WindowsFormsIntegration</span></span>

    -   <span data-ttu-id="94ddf-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="94ddf-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="94ddf-116">Aprire MainWindow. XAML nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94ddf-116">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

4. <span data-ttu-id="94ddf-117">Nome di <xref:System.Windows.Controls.Grid> elemento `grid1`.</span><span class="sxs-lookup"><span data-stu-id="94ddf-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="94ddf-118">Nella visualizzazione progettazione o XAML, selezionare il <xref:System.Windows.Window> elemento.</span><span class="sxs-lookup"><span data-stu-id="94ddf-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="94ddf-119">Nella finestra Proprietà scegliere il **eventi** scheda.</span><span class="sxs-lookup"><span data-stu-id="94ddf-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="94ddf-120">Fare doppio clic il <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="94ddf-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="94ddf-121">Inserire il codice seguente per gestire il <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="94ddf-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="94ddf-122">Nella parte superiore del file, aggiungere quanto segue `Imports` o `using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="94ddf-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="94ddf-123">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="94ddf-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="94ddf-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94ddf-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="94ddf-125">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94ddf-125">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="94ddf-126">Procedura dettagliata: Hosting di controlli Windows Form in WPF tramite XAML</span><span class="sxs-lookup"><span data-stu-id="94ddf-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="94ddf-127">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="94ddf-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="94ddf-128">Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form</span><span class="sxs-lookup"><span data-stu-id="94ddf-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="94ddf-129">Controlli Windows Form e controlli WPF equivalenti</span><span class="sxs-lookup"><span data-stu-id="94ddf-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="94ddf-130">Esempio di hosting di un controllo Windows Forms in WPF</span><span class="sxs-lookup"><span data-stu-id="94ddf-130">Hosting a Windows Forms Control in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160057)
