---
title: Ospitare un controllo Windows Forms in WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 2ed4e153a2513dc99d22a1538399156c138eb9e5
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123831"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="637cf-102">Procedura dettagliata: hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="637cf-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="637cf-103">offre numerosi controlli con un insieme di funzionalità completo.</span><span class="sxs-lookup"><span data-stu-id="637cf-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="637cf-104">Tuttavia, a volte può essere opportuno usare Windows Forms controlli nelle pagine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="637cf-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="637cf-105">Ad esempio, è possibile che si disponga di un investimento sostanziale nei controlli di Windows Forms esistenti o che si disponga di un controllo Windows Forms che fornisce funzionalità univoche.</span><span class="sxs-lookup"><span data-stu-id="637cf-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>

<span data-ttu-id="637cf-106">In questa procedura dettagliata viene illustrato come ospitare un controllo <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> di Windows Forms in una pagina di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizzando il codice.</span><span class="sxs-lookup"><span data-stu-id="637cf-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="637cf-107">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere la pagina relativa all' [hosting di un controllo Windows Forms in WPF di esempio](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).</span><span class="sxs-lookup"><span data-stu-id="637cf-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="637cf-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="637cf-108">Prerequisites</span></span>

<span data-ttu-id="637cf-109">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="637cf-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="637cf-110">Hosting del controllo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="637cf-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="637cf-111">Per ospitare il controllo MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="637cf-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="637cf-112">Creare un progetto di applicazione WPF denominato `HostingWfInWpf`.</span><span class="sxs-lookup"><span data-stu-id="637cf-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="637cf-113">Aggiungere riferimenti agli assembly indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="637cf-113">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="637cf-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="637cf-114">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="637cf-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="637cf-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="637cf-116">Aprire MainWindow. XAML in WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="637cf-116">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="637cf-117">Denominare l'elemento <xref:System.Windows.Controls.Grid> `grid1`.</span><span class="sxs-lookup"><span data-stu-id="637cf-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="637cf-118">Nella visualizzazione progettazione o nella visualizzazione XAML Selezionare l'elemento <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="637cf-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="637cf-119">Nella Finestra Proprietà fare clic sulla scheda **eventi** .</span><span class="sxs-lookup"><span data-stu-id="637cf-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="637cf-120">Fare doppio clic sull'evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="637cf-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="637cf-121">Inserire il codice seguente per gestire l'evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="637cf-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="637cf-122">Nella parte superiore del file aggiungere la seguente `Imports` o `using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="637cf-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="637cf-123">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="637cf-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="637cf-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="637cf-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="637cf-125">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="637cf-125">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="637cf-126">Procedura dettagliata: Hosting di controlli Windows Form in WPF tramite XAML</span><span class="sxs-lookup"><span data-stu-id="637cf-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="637cf-127">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="637cf-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="637cf-128">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="637cf-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="637cf-129">Controlli Windows Form e controlli WPF equivalenti</span><span class="sxs-lookup"><span data-stu-id="637cf-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="637cf-130">Esempio di hosting di un controllo Windows Forms in WPF</span><span class="sxs-lookup"><span data-stu-id="637cf-130">Hosting a Windows Forms Control in WPF Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)
