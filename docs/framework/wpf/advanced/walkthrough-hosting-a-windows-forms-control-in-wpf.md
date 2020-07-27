---
title: Ospitare un controllo Windows Forms in WPF
description: Informazioni su come ospitare Windows Forms controlli in Windows Presentation Foundation, che fornisce già molti controlli con un set di funzionalità avanzate.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: ec67cf9fabaa5b7aadbb2a3c21ebf8dd828ee20f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164982"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="be896-103">Procedura dettagliata: Hosting di un controllo Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="be896-103">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="be896-104">offre numerosi controlli con un insieme di funzionalità completo.</span><span class="sxs-lookup"><span data-stu-id="be896-104">provides many controls with a rich feature set.</span></span> <span data-ttu-id="be896-105">Tuttavia, a volte può essere opportuno usare Windows Forms controlli sulle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagine.</span><span class="sxs-lookup"><span data-stu-id="be896-105">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="be896-106">Ad esempio, è possibile che si disponga di un investimento sostanziale nei controlli di Windows Forms esistenti o che si disponga di un controllo Windows Forms che fornisce funzionalità univoche.</span><span class="sxs-lookup"><span data-stu-id="be896-106">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>

<span data-ttu-id="be896-107">In questa procedura dettagliata viene illustrato come ospitare un <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> controllo Windows Forms in una pagina utilizzando il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] codice.</span><span class="sxs-lookup"><span data-stu-id="be896-107">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="be896-108">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere la pagina relativa all' [hosting di un controllo Windows Forms in WPF di esempio](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).</span><span class="sxs-lookup"><span data-stu-id="be896-108">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be896-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="be896-109">Prerequisites</span></span>

<span data-ttu-id="be896-110">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="be896-110">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="be896-111">Hosting del controllo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be896-111">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="be896-112">Per ospitare il controllo MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="be896-112">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="be896-113">Creare un progetto di applicazione WPF denominato `HostingWfInWpf` .</span><span class="sxs-lookup"><span data-stu-id="be896-113">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="be896-114">Aggiungere riferimenti agli assembly indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="be896-114">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="be896-115">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="be896-115">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="be896-116">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="be896-116">System.Windows.Forms</span></span>

3. <span data-ttu-id="be896-117">Aprire MainWindow. XAML in WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="be896-117">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="be896-118">Assegnare un nome all' <xref:System.Windows.Controls.Grid> elemento `grid1` .</span><span class="sxs-lookup"><span data-stu-id="be896-118">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="be896-119">Nella visualizzazione progettazione o nella visualizzazione XAML Selezionare l' <xref:System.Windows.Window> elemento.</span><span class="sxs-lookup"><span data-stu-id="be896-119">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="be896-120">Nella Finestra Proprietà fare clic sulla scheda **eventi** .</span><span class="sxs-lookup"><span data-stu-id="be896-120">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="be896-121">Fare doppio clic sull' <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="be896-121">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="be896-122">Inserire il codice seguente per gestire l' <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="be896-122">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="be896-123">Nella parte superiore del file aggiungere la seguente `Imports` `using` istruzione o.</span><span class="sxs-lookup"><span data-stu-id="be896-123">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="be896-124">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="be896-124">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="be896-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be896-125">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="be896-126">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="be896-126">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="be896-127">Procedura dettagliata: Hosting di un controllo Windows Form in WPF tramite XAML</span><span class="sxs-lookup"><span data-stu-id="be896-127">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="be896-128">Procedura dettagliata: Hosting di un controllo composito Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="be896-128">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="be896-129">Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form</span><span class="sxs-lookup"><span data-stu-id="be896-129">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="be896-130">Controlli Windows Form e controlli WPF equivalenti</span><span class="sxs-lookup"><span data-stu-id="be896-130">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="be896-131">Esempio di hosting di un controllo Windows Forms in WPF</span><span class="sxs-lookup"><span data-stu-id="be896-131">Hosting a Windows Forms Control in WPF Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)
