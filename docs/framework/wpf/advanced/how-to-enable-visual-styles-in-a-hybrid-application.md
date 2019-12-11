---
title: "Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 251c53a8665d2eae7c3b5bb23b0a388009362dcc
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960119"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="a4d45-102">Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida</span><span class="sxs-lookup"><span data-stu-id="a4d45-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="a4d45-103">In questo argomento viene illustrato come abilitare gli stili di visualizzazione in un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato in un'applicazione basata su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4d45-103">This topic shows how to enable visual styles on a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="a4d45-104">Se l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>, la maggior parte dei controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] utilizzerà automaticamente gli stili di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="a4d45-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls will automatically use visual styles.</span></span> <span data-ttu-id="a4d45-105">Per altre informazioni, vedere [Rendering dei controlli con stili visivi](../../winforms/controls/rendering-controls-with-visual-styles.md).</span><span class="sxs-lookup"><span data-stu-id="a4d45-105">For more information, see [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="a4d45-106">Per un listato di codice completo delle attività illustrate in questo argomento, vedere l'articolo relativo all' [Abilitazione degli stili di visualizzazione in un'applicazione ibrida](https://go.microsoft.com/fwlink/?LinkID=159986).</span><span class="sxs-lookup"><span data-stu-id="a4d45-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="a4d45-107">Attivazione degli stili di visualizzazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="a4d45-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="a4d45-108">Per attivare gli stili di visualizzazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="a4d45-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="a4d45-109">Creare un progetto di applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denominato `HostingWfWithVisualStyles`.</span><span class="sxs-lookup"><span data-stu-id="a4d45-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="a4d45-110">In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.</span><span class="sxs-lookup"><span data-stu-id="a4d45-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="a4d45-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="a4d45-111">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="a4d45-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="a4d45-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="a4d45-113">Nella casella degli strumenti fare doppio clic sull'icona <xref:System.Windows.Controls.Grid> per inserire un elemento <xref:System.Windows.Controls.Grid> nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a4d45-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="a4d45-114">Nella Finestra Proprietà impostare i valori delle proprietà <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> su **auto**.</span><span class="sxs-lookup"><span data-stu-id="a4d45-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="a4d45-115">Nella visualizzazione progettazione o nella visualizzazione XAML Selezionare il <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="a4d45-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="a4d45-116">Nella Finestra Proprietà fare clic sulla scheda **eventi** .</span><span class="sxs-lookup"><span data-stu-id="a4d45-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="a4d45-117">Fare doppio clic sull'evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="a4d45-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="a4d45-118">In MainWindow. XAML. vb o MainWindow.xaml.cs inserire il codice seguente per gestire l'evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="a4d45-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="a4d45-119">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a4d45-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="a4d45-120">Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] viene disegnato con stili di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="a4d45-120">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="a4d45-121">Disattivazione degli stili di visualizzazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="a4d45-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="a4d45-122">Per disabilitare gli stili di visualizzazione, è sufficiente rimuovere la chiamata al metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4d45-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="a4d45-123">Per disattivare gli stili di visualizzazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="a4d45-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="a4d45-124">Aprire MainWindow.xaml.vb o MainWindow.xaml.cs nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="a4d45-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="a4d45-125">Impostare come commento la chiamata al metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4d45-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="a4d45-126">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a4d45-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="a4d45-127">Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] viene disegnato con lo stile di sistema predefinito.</span><span class="sxs-lookup"><span data-stu-id="a4d45-127">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d45-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4d45-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a4d45-129">Rendering dei controlli con stili visivi</span><span class="sxs-lookup"><span data-stu-id="a4d45-129">Rendering Controls with Visual Styles</span></span>](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [<span data-ttu-id="a4d45-130">Procedura dettagliata: hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="a4d45-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
