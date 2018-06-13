---
title: 'Procedura dettagliata: disposizione di controlli Windows Form in WPF'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: f2cf82c54724a43a60fb9077c5731d4b4ad2cfd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549659"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="e4e00-102">Procedura dettagliata: disposizione di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="e4e00-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="e4e00-103">Questa procedura dettagliata viene illustrato come utilizzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le funzionalità di layout per disporre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli in un'applicazione ibrida.</span><span class="sxs-lookup"><span data-stu-id="e4e00-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="e4e00-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4e00-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="e4e00-105">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e4e00-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="e4e00-106">Uso delle impostazioni di layout predefinite.</span><span class="sxs-lookup"><span data-stu-id="e4e00-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="e4e00-107">Ridimensionamento in base al contenuto.</span><span class="sxs-lookup"><span data-stu-id="e4e00-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="e4e00-108">Uso del posizionamento assoluto.</span><span class="sxs-lookup"><span data-stu-id="e4e00-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="e4e00-109">Specifica esplicita delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e4e00-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="e4e00-110">Impostazione delle proprietà di layout.</span><span class="sxs-lookup"><span data-stu-id="e4e00-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="e4e00-111">Informazioni sulle limitazioni di z order.</span><span class="sxs-lookup"><span data-stu-id="e4e00-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="e4e00-112">Ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="e4e00-112">Docking.</span></span>  
  
-   <span data-ttu-id="e4e00-113">Impostazione della visibilità.</span><span class="sxs-lookup"><span data-stu-id="e4e00-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="e4e00-114">Hosting di un controllo che non si adatta.</span><span class="sxs-lookup"><span data-stu-id="e4e00-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="e4e00-115">Ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-115">Scaling.</span></span>  
  
-   <span data-ttu-id="e4e00-116">Rotazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-116">Rotating.</span></span>  
  
-   <span data-ttu-id="e4e00-117">Impostazione della spaziatura interna e dei margini.</span><span class="sxs-lookup"><span data-stu-id="e4e00-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="e4e00-118">Uso di contenitori di layout dinamici.</span><span class="sxs-lookup"><span data-stu-id="e4e00-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="e4e00-119">Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [disposizione di controlli Windows Form in WPF](http://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="e4e00-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="e4e00-120">Al termine, si avrà una migliore comprensione di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] le caratteristiche di layout in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazioni basate su.</span><span class="sxs-lookup"><span data-stu-id="e4e00-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e4e00-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e4e00-121">Prerequisites</span></span>  
 <span data-ttu-id="e4e00-122">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4e00-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="e4e00-123">.</span><span class="sxs-lookup"><span data-stu-id="e4e00-123">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="e4e00-124">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="e4e00-124">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="e4e00-125">Per creare e impostare il progetto</span><span class="sxs-lookup"><span data-stu-id="e4e00-125">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="e4e00-126">Creare un progetto di applicazione WPF denominato `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="e4e00-126">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="e4e00-127">In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.</span><span class="sxs-lookup"><span data-stu-id="e4e00-127">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="e4e00-128">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="e4e00-128">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="e4e00-129">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="e4e00-129">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="e4e00-130">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="e4e00-130">System.Drawing</span></span>  
  
3.  <span data-ttu-id="e4e00-131">Fare doppio clic sul file MainWindow.xaml per aprirlo nella visualizzazione XAML.</span><span class="sxs-lookup"><span data-stu-id="e4e00-131">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="e4e00-132">Nel <xref:System.Windows.Window> elemento, aggiungere il seguente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mapping dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e4e00-132">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="e4e00-133">Nel <xref:System.Windows.Controls.Grid> insieme di elementi di <xref:System.Windows.Controls.Grid.ShowGridLines%2A> proprietà `true` e definire cinque righe e tre colonne.</span><span class="sxs-lookup"><span data-stu-id="e4e00-133">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="e4e00-134">Uso delle impostazioni di layout predefinite</span><span class="sxs-lookup"><span data-stu-id="e4e00-134">Using Default Layout Settings</span></span>  
 <span data-ttu-id="e4e00-135">Per impostazione predefinita, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento gestisce il layout del controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.</span><span class="sxs-lookup"><span data-stu-id="e4e00-135">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="e4e00-136">Per usare le impostazioni di layout predefinite</span><span class="sxs-lookup"><span data-stu-id="e4e00-136">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="e4e00-137">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-137">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="e4e00-138">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-138">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-139">Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> verrà visualizzato un controllo di <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="e4e00-139">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="e4e00-140">Il controllo viene ridimensionato in base al contenuto e <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene ridimensionato in base al controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="e4e00-140">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="e4e00-141">Ridimensionamento in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="e4e00-141">Sizing to Content</span></span>  
 <span data-ttu-id="e4e00-142">Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento garantisce che il controllo viene ridimensionato per visualizzare correttamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="e4e00-142">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="e4e00-143">Per ridimensionare in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="e4e00-143">To size to content</span></span>  
  
1.  <span data-ttu-id="e4e00-144">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-144">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="e4e00-145">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-145">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-146">I due nuovi controlli pulsante vengono ridimensionati per visualizzare correttamente, la stringa di testo più lungo e dimensione del carattere e il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementi vengono ridimensionati in base ai controlli ospitati.</span><span class="sxs-lookup"><span data-stu-id="e4e00-146">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="e4e00-147">Uso del posizionamento assoluto</span><span class="sxs-lookup"><span data-stu-id="e4e00-147">Using Absolute Positioning</span></span>  
 <span data-ttu-id="e4e00-148">È possibile utilizzare il posizionamento assoluto per inserire il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento in un punto qualsiasi nell'interfaccia utente (UI).</span><span class="sxs-lookup"><span data-stu-id="e4e00-148">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="e4e00-149">Per usare il posizionamento assoluto</span><span class="sxs-lookup"><span data-stu-id="e4e00-149">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="e4e00-150">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-150">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="e4e00-151">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-151">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-152">Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene inserito 20 pixel dal lato superiore della cella della griglia e 20 pixel dal bordo sinistro.</span><span class="sxs-lookup"><span data-stu-id="e4e00-152">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="e4e00-153">Specifica esplicita delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="e4e00-153">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="e4e00-154">È possibile specificare le dimensioni del <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento utilizzando il <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e4e00-154">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="e4e00-155">Per specificare le dimensioni in modo esplicito</span><span class="sxs-lookup"><span data-stu-id="e4e00-155">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="e4e00-156">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-156">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="e4e00-157">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-157">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-158">Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento è impostato su una dimensione pari a 50 pixel in larghezza per 70 pixel di altezza, che è minore di impostazioni di layout predefinito.</span><span class="sxs-lookup"><span data-stu-id="e4e00-158">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="e4e00-159">Il contenuto del [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene riordinato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="e4e00-159">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="e4e00-160">Impostazione delle proprietà di layout</span><span class="sxs-lookup"><span data-stu-id="e4e00-160">Setting Layout Properties</span></span>  
 <span data-ttu-id="e4e00-161">Impostare sempre le proprietà relative al layout del controllo ospitato utilizzando le proprietà del <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-161">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="e4e00-162">L'impostazione diretta delle proprietà di layout nel controllo ospitato darà risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="e4e00-162">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="e4e00-163">Impostazione delle proprietà relative al layout del controllo ospitato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e4e00-163">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="e4e00-164">Per visualizzare gli effetti dell'impostazione delle proprietà nel controllo</span><span class="sxs-lookup"><span data-stu-id="e4e00-164">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="e4e00-165">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-165">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="e4e00-166">In Esplora soluzioni fare doppio clic su MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="e4e00-166">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="e4e00-167">vb o MainWindow.xaml.cs per aprirlo nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="e4e00-167">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="e4e00-168">Copiare il codice seguente nel `MainWindow` definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="e4e00-168">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  <span data-ttu-id="e4e00-169">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-169">Press F5 to build and run the application.</span></span>  
  
5.  <span data-ttu-id="e4e00-170">Fare clic su di **Click me** pulsante.</span><span class="sxs-lookup"><span data-stu-id="e4e00-170">Click the **Click me** button.</span></span> <span data-ttu-id="e4e00-171">Il `button1_Click` gestore eventi imposta il <xref:System.Windows.Forms.Control.Top%2A> e <xref:System.Windows.Forms.Control.Left%2A> le proprietà del controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="e4e00-171">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="e4e00-172">In questo modo il controllo ospitato venga riposizionato all'interno di <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-172">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="e4e00-173">L'host mantiene la stessa area dello schermo, ma il controllo ospitato viene ritagliato.</span><span class="sxs-lookup"><span data-stu-id="e4e00-173">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="e4e00-174">Al contrario, il controllo ospitato dovrebbe sempre occupare il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-174">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="understanding-z-order-limitations"></a><span data-ttu-id="e4e00-175">Informazioni sulle limitazioni di z order</span><span class="sxs-lookup"><span data-stu-id="e4e00-175">Understanding Z-Order Limitations</span></span>  
 <span data-ttu-id="e4e00-176">Visibile <xref:System.Windows.Forms.Integration.WindowsFormsHost> gli elementi vengono sempre disegnati sopra gli altri elementi WPF e non vengono influenzati dall'ordine z.</span><span class="sxs-lookup"><span data-stu-id="e4e00-176">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="e4e00-177">Per visualizzare questo comportamento nell'ordine z, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4e00-177">To see this z-order behavior, do the following:</span></span>

1.  <span data-ttu-id="e4e00-178">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-178">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
 
2.  <span data-ttu-id="e4e00-179">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-179">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-180">Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene disegnato un elemento tramite l'elemento label.</span><span class="sxs-lookup"><span data-stu-id="e4e00-180">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>  


## <a name="docking"></a><span data-ttu-id="e4e00-181">Ancoraggio</span><span class="sxs-lookup"><span data-stu-id="e4e00-181">Docking</span></span>  
 <span data-ttu-id="e4e00-182"><xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento supporta [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="e4e00-182"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="e4e00-183">Impostare il <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà associata per ancorare il controllo ospitato in un <xref:System.Windows.Controls.DockPanel> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-183">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="e4e00-184">Per ancorare un controllo ospitato</span><span class="sxs-lookup"><span data-stu-id="e4e00-184">To dock a hosted control</span></span>  
  
1.  <span data-ttu-id="e4e00-185">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-185">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  <span data-ttu-id="e4e00-186">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-186">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-187">Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene ancorato al lato destro del <xref:System.Windows.Controls.DockPanel> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-187">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
## <a name="setting-visibility"></a><span data-ttu-id="e4e00-188">Impostazione della visibilità</span><span class="sxs-lookup"><span data-stu-id="e4e00-188">Setting Visibility</span></span>  
 <span data-ttu-id="e4e00-189">È possibile rendere il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo invisibile o comprimerlo impostando il <xref:System.Windows.UIElement.Visibility%2A> proprietà il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-189">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="e4e00-190">Quando un controllo non è visibile, non viene visualizzato, ma occupa spazio del layout.</span><span class="sxs-lookup"><span data-stu-id="e4e00-190">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="e4e00-191">Quando un controllo è compresso, non viene visualizzato né occupa spazio del layout.</span><span class="sxs-lookup"><span data-stu-id="e4e00-191">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="e4e00-192">Per impostare la visibilità di un controllo ospitato</span><span class="sxs-lookup"><span data-stu-id="e4e00-192">To set the visibility of a hosted control</span></span>  
  
1.  <span data-ttu-id="e4e00-193">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-193">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  <span data-ttu-id="e4e00-194">In MainWindow.xaml.vb o MainWindow.xaml.cs copiare il codice seguente nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="e4e00-194">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  <span data-ttu-id="e4e00-195">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-195">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="e4e00-196">Fare clic su di **fare clic per rendere invisibili** pulsante per rendere il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento invisibile.</span><span class="sxs-lookup"><span data-stu-id="e4e00-196">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>  
  
5.  <span data-ttu-id="e4e00-197">Fare clic su di **fare clic per comprimere** pulsante per nascondere il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento dal layout completamente.</span><span class="sxs-lookup"><span data-stu-id="e4e00-197">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="e4e00-198">Quando il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene compresso, gli elementi circostanti vengono riorganizzati in modo da occupare lo spazio.</span><span class="sxs-lookup"><span data-stu-id="e4e00-198">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>  
  
## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="e4e00-199">Hosting di un controllo che non si adatta</span><span class="sxs-lookup"><span data-stu-id="e4e00-199">Hosting a Control That Does Not Stretch</span></span>  
 <span data-ttu-id="e4e00-200">Alcuni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli hanno dimensioni fisse e non si adattano per riempire lo spazio disponibile nel layout.</span><span class="sxs-lookup"><span data-stu-id="e4e00-200">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="e4e00-201">Ad esempio, il <xref:System.Windows.Forms.MonthCalendar> controllo consente di visualizzare un mese in uno spazio fisso.</span><span class="sxs-lookup"><span data-stu-id="e4e00-201">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="e4e00-202">Per ospitare un controllo che non si adatta</span><span class="sxs-lookup"><span data-stu-id="e4e00-202">To host a control that does not stretch</span></span>  
  
1.  <span data-ttu-id="e4e00-203">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-203">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  <span data-ttu-id="e4e00-204">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-204">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-205">Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene centrato nella riga della griglia, ma non è estesa per riempire lo spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="e4e00-205">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="e4e00-206">Se la finestra è sufficientemente grande, è possibile riscontrare due o più mesi tramite l'hosting <xref:System.Windows.Forms.MonthCalendar> controllo, ma questi sono centrati nella riga.</span><span class="sxs-lookup"><span data-stu-id="e4e00-206">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="e4e00-207">Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motore di layout Centra gli elementi che non possono essere ridimensionati per riempire lo spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="e4e00-207">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>  
  
## <a name="scaling"></a><span data-ttu-id="e4e00-208">Ridimensionamento</span><span class="sxs-lookup"><span data-stu-id="e4e00-208">Scaling</span></span>  
 <span data-ttu-id="e4e00-209">A differenza degli elementi WPF, la maggior parte dei controlli Windows Form non sono scalabili in modo continuo.</span><span class="sxs-lookup"><span data-stu-id="e4e00-209">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="e4e00-210">Consenta un ridimensionamento personalizzato, si esegue l'override di <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="e4e00-210">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span> 
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="e4e00-211">Per ridimensionare un controllo ospitato usando il comportamento predefinito</span><span class="sxs-lookup"><span data-stu-id="e4e00-211">To scale a hosted control by using the default behavior</span></span>  
  
1.  <span data-ttu-id="e4e00-212">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-212">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  <span data-ttu-id="e4e00-213">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-213">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-214">Il controllo ospitato e gli elementi che lo circondano vengono ridimensionati in base a un fattore di 0,5.</span><span class="sxs-lookup"><span data-stu-id="e4e00-214">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="e4e00-215">Tuttavia il tipo di carattere del controllo ospitato non viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="e4e00-215">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="e4e00-216">Rotazione</span><span class="sxs-lookup"><span data-stu-id="e4e00-216">Rotating</span></span>  
 <span data-ttu-id="e4e00-217">A differenza degli elementi WPF, controlli Windows Form non supportano la rotazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-217">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="e4e00-218">Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento non ruota con altri elementi di WPF quando viene applicata una trasformazione di rotazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-218">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="e4e00-219">Qualsiasi valore di rotazione diverso da 180 gradi genera il <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> evento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-219">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>
 
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="e4e00-220">Per visualizzare l'effetto di rotazione in un'applicazione ibrida</span><span class="sxs-lookup"><span data-stu-id="e4e00-220">To see the effect of rotation in a hybrid application</span></span>  
  
1.  <span data-ttu-id="e4e00-221">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-221">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  <span data-ttu-id="e4e00-222">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-222">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-223">Il controllo ospitato non viene ruotato, ma i relativi elementi circostanti vengono ruotati di 180 gradi.</span><span class="sxs-lookup"><span data-stu-id="e4e00-223">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="e4e00-224">Potrebbe essere necessario ridimensionare la finestra per vedere gli elementi.</span><span class="sxs-lookup"><span data-stu-id="e4e00-224">You may have to resize the window to see the elements.</span></span>  
 

## <a name="setting-padding-and-margins"></a><span data-ttu-id="e4e00-225">Impostazione della spaziatura interna e dei margini</span><span class="sxs-lookup"><span data-stu-id="e4e00-225">Setting Padding and Margins</span></span>  
 <span data-ttu-id="e4e00-226">Spaziatura e margini in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout sono simili alla spaziatura interna e margini [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4e00-226">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="e4e00-227">Impostare semplicemente il <xref:System.Windows.Controls.Control.Padding%2A> e <xref:System.Windows.FrameworkElement.Margin%2A> proprietà il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-227">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="e4e00-228">Per impostare spaziatura interna e margini per un controllo ospitato</span><span class="sxs-lookup"><span data-stu-id="e4e00-228">To set padding and margins for a hosted control</span></span>  
  
1.  <span data-ttu-id="e4e00-229">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-229">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  <span data-ttu-id="e4e00-230">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-230">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-231">Le impostazioni di spaziatura e margini vengono applicate in essa contenuto [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli nello stesso modo in cui verrebbero applicate in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4e00-231">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="e4e00-232">Uso di contenitori di layout dinamici</span><span class="sxs-lookup"><span data-stu-id="e4e00-232">Using Dynamic Layout Containers</span></span>  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="e4e00-233"> fornisce due contenitori di layout dinamico, <xref:System.Windows.Forms.FlowLayoutPanel> e <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="e4e00-233"> provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="e4e00-234">È inoltre possibile utilizzare questi contenitori in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout.</span><span class="sxs-lookup"><span data-stu-id="e4e00-234">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>  
  
#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="e4e00-235">Per usare un contenitore di layout dinamico</span><span class="sxs-lookup"><span data-stu-id="e4e00-235">To use a dynamic layout container</span></span>  
  
1.  <span data-ttu-id="e4e00-236">Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4e00-236">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  <span data-ttu-id="e4e00-237">In MainWindow.xaml.vb o MainWindow.xaml.cs copiare il codice seguente nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="e4e00-237">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  <span data-ttu-id="e4e00-238">Aggiungere una chiamata al `InitializeFlowLayoutPanel` metodo nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="e4e00-238">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="e4e00-239">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e00-239">Press F5 to build and run the application.</span></span> <span data-ttu-id="e4e00-240">Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento riempie il <xref:System.Windows.Controls.DockPanel>, e <xref:System.Windows.Forms.FlowLayoutPanel> dispone i controlli figlio nel valore predefinito <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4e00-240">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e00-241">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4e00-241">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="e4e00-242">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="e4e00-242">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="e4e00-243">Considerazioni sul layout per l'elemento WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="e4e00-243">Layout Considerations for the WindowsFormsHost Element</span></span>](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [<span data-ttu-id="e4e00-244">Disposizione dei Windows Form controlli nell'esempio di WPF</span><span class="sxs-lookup"><span data-stu-id="e4e00-244">Arranging Windows Forms Controls in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [<span data-ttu-id="e4e00-245">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="e4e00-245">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="e4e00-246">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e4e00-246">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
