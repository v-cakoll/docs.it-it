---
title: Disporre i controlli Windows Forms in WPF
titleSuffix: ''
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 5cf48b347be2d0ca6a9b55f3e19affb8b471aa2b
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095099"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="87679-102">Procedura dettagliata: disposizione di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="87679-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="87679-103">Questa procedura dettagliata illustra come usare le funzionalità di layout [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per disporre i controlli Windows Forms in un'applicazione ibrida.</span><span class="sxs-lookup"><span data-stu-id="87679-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange Windows Forms controls in a hybrid application.</span></span>

<span data-ttu-id="87679-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="87679-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="87679-105">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="87679-105">Creating the project.</span></span>
- <span data-ttu-id="87679-106">Uso delle impostazioni di layout predefinite.</span><span class="sxs-lookup"><span data-stu-id="87679-106">Using default layout settings.</span></span>
- <span data-ttu-id="87679-107">Ridimensionamento in base al contenuto.</span><span class="sxs-lookup"><span data-stu-id="87679-107">Sizing to content.</span></span>
- <span data-ttu-id="87679-108">Uso del posizionamento assoluto.</span><span class="sxs-lookup"><span data-stu-id="87679-108">Using absolute positioning.</span></span>
- <span data-ttu-id="87679-109">Specifica esplicita delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="87679-109">Specifying size explicitly.</span></span>
- <span data-ttu-id="87679-110">Impostazione delle proprietà di layout.</span><span class="sxs-lookup"><span data-stu-id="87679-110">Setting layout properties.</span></span>
- <span data-ttu-id="87679-111">Informazioni sulle limitazioni di z order.</span><span class="sxs-lookup"><span data-stu-id="87679-111">Understanding z-order limitations.</span></span>
- <span data-ttu-id="87679-112">Ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="87679-112">Docking.</span></span>
- <span data-ttu-id="87679-113">Impostazione della visibilità.</span><span class="sxs-lookup"><span data-stu-id="87679-113">Setting visibility.</span></span>
- <span data-ttu-id="87679-114">Hosting di un controllo che non si adatta.</span><span class="sxs-lookup"><span data-stu-id="87679-114">Hosting a control that does not stretch.</span></span>
- <span data-ttu-id="87679-115">Scalabilità.</span><span class="sxs-lookup"><span data-stu-id="87679-115">Scaling.</span></span>
- <span data-ttu-id="87679-116">Rotazione.</span><span class="sxs-lookup"><span data-stu-id="87679-116">Rotating.</span></span>
- <span data-ttu-id="87679-117">Impostazione della spaziatura interna e dei margini.</span><span class="sxs-lookup"><span data-stu-id="87679-117">Setting padding and margins.</span></span>
- <span data-ttu-id="87679-118">Uso di contenitori di layout dinamici.</span><span class="sxs-lookup"><span data-stu-id="87679-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="87679-119">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [disposizione di Windows Forms controlli in WPF di esempio](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml).</span><span class="sxs-lookup"><span data-stu-id="87679-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml).</span></span>

<span data-ttu-id="87679-120">Al termine, sarà possibile comprendere Windows Forms funzionalità di layout nelle applicazioni basate su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87679-120">When you are finished, you will have an understanding of Windows Forms layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87679-121">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="87679-121">Prerequisites</span></span>

<span data-ttu-id="87679-122">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="87679-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="87679-123">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="87679-123">Creating the Project</span></span>

<span data-ttu-id="87679-124">Per creare e configurare il progetto, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="87679-124">To create and set up the project, follow these steps:</span></span>

1. <span data-ttu-id="87679-125">Creare un progetto di applicazione WPF denominato `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="87679-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="87679-126">In Esplora soluzioni aggiungere riferimenti agli assembly seguenti:</span><span class="sxs-lookup"><span data-stu-id="87679-126">In Solution Explorer, add references to the following assemblies:</span></span>

    - <span data-ttu-id="87679-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="87679-127">WindowsFormsIntegration</span></span>
    - <span data-ttu-id="87679-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="87679-128">System.Windows.Forms</span></span>
    - <span data-ttu-id="87679-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="87679-129">System.Drawing</span></span>

3. <span data-ttu-id="87679-130">Fare doppio clic su *MainWindow. XAML* per aprirlo nella visualizzazione XAML.</span><span class="sxs-lookup"><span data-stu-id="87679-130">Double-click *MainWindow.xaml* to open it in XAML view.</span></span>

4. <span data-ttu-id="87679-131">Nell'elemento <xref:System.Windows.Window> aggiungere il seguente Windows Forms mapping dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="87679-131">In the <xref:System.Windows.Window> element, add the following Windows Forms namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="87679-132">Nell'elemento <xref:System.Windows.Controls.Grid> impostare la proprietà <xref:System.Windows.Controls.Grid.ShowGridLines%2A> su `true` e definire cinque righe e tre colonne.</span><span class="sxs-lookup"><span data-stu-id="87679-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="87679-133">Uso delle impostazioni di layout predefinite</span><span class="sxs-lookup"><span data-stu-id="87679-133">Using Default Layout Settings</span></span>

<span data-ttu-id="87679-134">Per impostazione predefinita, l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> gestisce il layout per il controllo Windows Forms ospitato.</span><span class="sxs-lookup"><span data-stu-id="87679-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted Windows Forms control.</span></span>

<span data-ttu-id="87679-135">Per usare le impostazioni di layout predefinite, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="87679-135">To use default layout settings, follow these steps:</span></span>

1. <span data-ttu-id="87679-136">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="87679-137">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-137">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-138">Il controllo Windows Forms <xref:System.Windows.Forms.Button?displayProperty=nameWithType> viene visualizzato nella <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="87679-138">The Windows Forms <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="87679-139">Il controllo ospitato viene ridimensionato in base al relativo contenuto e l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene dimensionato per contenere il controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="87679-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="87679-140">Ridimensionamento in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="87679-140">Sizing to Content</span></span>

<span data-ttu-id="87679-141">L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantisce che il controllo ospitato venga ridimensionato per visualizzare correttamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="87679-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

<span data-ttu-id="87679-142">Per ridimensionare il contenuto, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="87679-142">To size to content, follow these steps:</span></span>

1. <span data-ttu-id="87679-143">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="87679-144">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-144">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-145">I due nuovi controlli pulsante vengono ridimensionati in modo da visualizzare la stringa di testo più lunga e le dimensioni del carattere più grandi e gli elementi <xref:System.Windows.Forms.Integration.WindowsFormsHost> vengono ridimensionati per contenere i controlli ospitati.</span><span class="sxs-lookup"><span data-stu-id="87679-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="87679-146">Uso del posizionamento assoluto</span><span class="sxs-lookup"><span data-stu-id="87679-146">Using Absolute Positioning</span></span>

<span data-ttu-id="87679-147">È possibile usare il posizionamento assoluto per inserire l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> in un punto qualsiasi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="87679-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

<span data-ttu-id="87679-148">Per usare il posizionamento assoluto, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="87679-148">To use absolute positioning, follow these steps:</span></span>

1. <span data-ttu-id="87679-149">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="87679-150">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-150">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-151">L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene inserito a 20 pixel dal lato superiore della cella della griglia e a 20 pixel da sinistra.</span><span class="sxs-lookup"><span data-stu-id="87679-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="87679-152">Specifica esplicita delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="87679-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="87679-153">È possibile specificare le dimensioni dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> usando le proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="87679-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

<span data-ttu-id="87679-154">Per specificare le dimensioni in modo esplicito, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="87679-154">To specify size explicitly, follow these steps:</span></span>

1. <span data-ttu-id="87679-155">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="87679-156">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-156">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-157">L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> è impostato su una dimensione di 50 pixel in larghezza per 70 pixel di altezza, minore rispetto alle impostazioni predefinite del layout.</span><span class="sxs-lookup"><span data-stu-id="87679-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="87679-158">Il contenuto del controllo Windows Forms viene ridisposto di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="87679-158">The content of the Windows Forms control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="87679-159">Impostazione delle proprietà di layout</span><span class="sxs-lookup"><span data-stu-id="87679-159">Setting Layout Properties</span></span>

<span data-ttu-id="87679-160">Impostare sempre le proprietà correlate al layout nel controllo ospitato usando le proprietà dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="87679-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="87679-161">L'impostazione diretta delle proprietà di layout nel controllo ospitato darà risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="87679-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="87679-162">L'impostazione delle proprietà correlate al layout nel controllo ospitato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="87679-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

<span data-ttu-id="87679-163">Per visualizzare gli effetti dell'impostazione delle proprietà nel controllo ospitato, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="87679-163">To see the effects of setting properties on the hosted control, follow these steps:</span></span>

1. <span data-ttu-id="87679-164">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="87679-165">In **Esplora soluzioni**fare doppio clic su *MainWindow. XAML. vb* o *MainWindow.XAML.cs* per aprirlo nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="87679-165">In **Solution Explorer**, double-click *MainWindow.xaml.vb* or *MainWindow.xaml.cs* to open it in the Code Editor.</span></span>

3. <span data-ttu-id="87679-166">Copiare il codice seguente nella definizione della classe `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="87679-166">Copy the following code into the `MainWindow` class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="87679-167">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-167">Press <kbd>F5</kbd> to build and run the application.</span></span>

5. <span data-ttu-id="87679-168">Fare clic sul pulsante **fare clic su me** .</span><span class="sxs-lookup"><span data-stu-id="87679-168">Click the **Click me** button.</span></span> <span data-ttu-id="87679-169">Il gestore dell'evento `button1_Click` imposta le proprietà <xref:System.Windows.Forms.Control.Top%2A> e <xref:System.Windows.Forms.Control.Left%2A> sul controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="87679-169">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="87679-170">In questo modo il controllo ospitato viene riposizionato all'interno dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="87679-170">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="87679-171">L'host mantiene la stessa area dello schermo, ma il controllo ospitato viene ritagliato.</span><span class="sxs-lookup"><span data-stu-id="87679-171">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="87679-172">Al contrario, il controllo ospitato deve riempire sempre l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="87679-172">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="87679-173">Informazioni sulle limitazioni di z order</span><span class="sxs-lookup"><span data-stu-id="87679-173">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="87679-174">Gli elementi <xref:System.Windows.Forms.Integration.WindowsFormsHost> visibili vengono sempre disegnati sopra gli altri elementi WPF e non sono interessati dall'ordine z.</span><span class="sxs-lookup"><span data-stu-id="87679-174">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="87679-175">Per visualizzare questo comportamento dell'ordine z, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="87679-175">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="87679-176">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-176">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="87679-177">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-177">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-178">L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene disegnato sull'elemento label.</span><span class="sxs-lookup"><span data-stu-id="87679-178">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="87679-179">Docking</span><span class="sxs-lookup"><span data-stu-id="87679-179">Docking</span></span>

<span data-ttu-id="87679-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento supporta l'ancoraggio [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87679-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="87679-181">Impostare la proprietà associata <xref:System.Windows.Controls.DockPanel.Dock%2A> per ancorare il controllo ospitato in un elemento <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="87679-181">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

<span data-ttu-id="87679-182">Per ancorare un controllo ospitato, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="87679-182">To dock a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="87679-183">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-183">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="87679-184">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-184">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-185">L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> è ancorato al lato destro dell'elemento <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="87679-185">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="87679-186">Impostazione della visibilità</span><span class="sxs-lookup"><span data-stu-id="87679-186">Setting Visibility</span></span>

<span data-ttu-id="87679-187">È possibile rendere invisibile il controllo Windows Forms o comprimerlo impostando la proprietà <xref:System.Windows.UIElement.Visibility%2A> sull'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="87679-187">You can make your Windows Forms control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="87679-188">Quando un controllo non è visibile, non viene visualizzato, ma occupa spazio del layout.</span><span class="sxs-lookup"><span data-stu-id="87679-188">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="87679-189">Quando un controllo è compresso, non viene visualizzato né occupa spazio del layout.</span><span class="sxs-lookup"><span data-stu-id="87679-189">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

<span data-ttu-id="87679-190">Per impostare la visibilità di un controllo ospitato, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="87679-190">To set the visibility of a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="87679-191">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-191">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="87679-192">In *MainWindow. XAML. vb* o *MainWindow.XAML.cs*copiare il codice seguente nella definizione della classe:</span><span class="sxs-lookup"><span data-stu-id="87679-192">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="87679-193">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-193">Press <kbd>F5</kbd> to build and run the application.</span></span>

4. <span data-ttu-id="87679-194">Fare clic sul pulsante **fare clic per rendere invisibile** per rendere invisibile l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="87679-194">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="87679-195">Fare clic sul pulsante **fare clic per comprimere** per nascondere completamente l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> dal layout.</span><span class="sxs-lookup"><span data-stu-id="87679-195">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="87679-196">Quando il controllo Windows Forms viene compresso, gli elementi circostanti vengono ridisposti per occuparne lo spazio.</span><span class="sxs-lookup"><span data-stu-id="87679-196">When the Windows Forms control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="87679-197">Hosting di un controllo che non si adatta</span><span class="sxs-lookup"><span data-stu-id="87679-197">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="87679-198">Alcuni controlli Windows Forms hanno una dimensione fissa e non si adattano per riempire lo spazio disponibile nel layout.</span><span class="sxs-lookup"><span data-stu-id="87679-198">Some Windows Forms controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="87679-199">Ad esempio, il controllo <xref:System.Windows.Forms.MonthCalendar> Visualizza un mese in uno spazio fisso.</span><span class="sxs-lookup"><span data-stu-id="87679-199">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

<span data-ttu-id="87679-200">Per ospitare un controllo che non si estende, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="87679-200">To host a control that does not stretch, follow these steps:</span></span>

1. <span data-ttu-id="87679-201">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-201">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="87679-202">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-202">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-203">L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene centrato nella riga della griglia, ma non viene allungato per riempire lo spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="87679-203">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="87679-204">Se la finestra è sufficientemente grande, è possibile che vengano visualizzati due o più mesi dal controllo <xref:System.Windows.Forms.MonthCalendar> host, che però sono centrati nella riga.</span><span class="sxs-lookup"><span data-stu-id="87679-204">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="87679-205">Il motore di layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] centra gli elementi che non possono essere ridimensionati per riempire lo spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="87679-205">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="87679-206">Scalabilità</span><span class="sxs-lookup"><span data-stu-id="87679-206">Scaling</span></span>

<span data-ttu-id="87679-207">Diversamente dagli elementi WPF, la maggior parte dei controlli Windows Forms non è continuamente scalabile.</span><span class="sxs-lookup"><span data-stu-id="87679-207">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="87679-208">Per fornire scalabilità personalizzata, è necessario eseguire l'override del metodo <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="87679-208">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="87679-209">Per ridimensionare un controllo ospitato usando il comportamento predefinito, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="87679-209">To scale a hosted control by using the default behavior, follow these steps:</span></span>

1. <span data-ttu-id="87679-210">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-210">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="87679-211">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-211">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-212">Il controllo ospitato e gli elementi che lo circondano vengono ridimensionati in base a un fattore di 0,5.</span><span class="sxs-lookup"><span data-stu-id="87679-212">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="87679-213">Tuttavia il tipo di carattere del controllo ospitato non viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="87679-213">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="87679-214">Rotazione</span><span class="sxs-lookup"><span data-stu-id="87679-214">Rotating</span></span>

<span data-ttu-id="87679-215">Diversamente dagli elementi WPF, i controlli Windows Forms non supportano la rotazione.</span><span class="sxs-lookup"><span data-stu-id="87679-215">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="87679-216">L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> non viene ruotato con altri elementi WPF quando viene applicata una trasformazione di rotazione.</span><span class="sxs-lookup"><span data-stu-id="87679-216">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="87679-217">Qualsiasi valore di rotazione diverso da 180 gradi genera l'evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>.</span><span class="sxs-lookup"><span data-stu-id="87679-217">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

<span data-ttu-id="87679-218">Per visualizzare l'effetto della rotazione in un'applicazione ibrida, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="87679-218">To see the effect of rotation in a hybrid application, follow these steps:</span></span>

1. <span data-ttu-id="87679-219">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-219">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="87679-220">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-220">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-221">Il controllo ospitato non viene ruotato, ma i relativi elementi circostanti vengono ruotati di 180 gradi.</span><span class="sxs-lookup"><span data-stu-id="87679-221">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="87679-222">Potrebbe essere necessario ridimensionare la finestra per vedere gli elementi.</span><span class="sxs-lookup"><span data-stu-id="87679-222">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="87679-223">Impostazione della spaziatura interna e dei margini</span><span class="sxs-lookup"><span data-stu-id="87679-223">Setting Padding and Margins</span></span>

<span data-ttu-id="87679-224">La spaziatura interna e i margini nel layout [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono simili a spaziatura interna e margini in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="87679-224">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in Windows Forms.</span></span> <span data-ttu-id="87679-225">È sufficiente impostare le proprietà <xref:System.Windows.Controls.Control.Padding%2A> e <xref:System.Windows.FrameworkElement.Margin%2A> sull'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="87679-225">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

<span data-ttu-id="87679-226">Per impostare spaziatura interna e margini per un controllo ospitato, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="87679-226">To set padding and margins for a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="87679-227">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-227">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="87679-228">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-228">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-229">Le impostazioni di spaziatura interna e margini vengono applicate ai controlli Windows Forms ospitati nello stesso modo in cui vengono applicati in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="87679-229">The padding and margin settings are applied to the hosted Windows Forms controls in the same way they would be applied in Windows Forms.</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="87679-230">Uso di contenitori di layout dinamici</span><span class="sxs-lookup"><span data-stu-id="87679-230">Using Dynamic Layout Containers</span></span>

<span data-ttu-id="87679-231">Windows Forms fornisce due contenitori di layout dinamici, <xref:System.Windows.Forms.FlowLayoutPanel> e <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="87679-231">Windows Forms provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="87679-232">È anche possibile usare questi contenitori in layout [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87679-232">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

<span data-ttu-id="87679-233">Per usare un contenitore di layout dinamico, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="87679-233">To use a dynamic layout container, follow these steps:</span></span>

1. <span data-ttu-id="87679-234">Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="87679-234">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="87679-235">In *MainWindow. XAML. vb* o *MainWindow.XAML.cs*copiare il codice seguente nella definizione della classe:</span><span class="sxs-lookup"><span data-stu-id="87679-235">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="87679-236">Aggiungere una chiamata al metodo `InitializeFlowLayoutPanel` nel costruttore:</span><span class="sxs-lookup"><span data-stu-id="87679-236">Add a call to the `InitializeFlowLayoutPanel` method in the constructor:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="87679-237">Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87679-237">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="87679-238">L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> riempie l'<xref:System.Windows.Controls.DockPanel>e <xref:System.Windows.Forms.FlowLayoutPanel> dispone i relativi controlli figlio nel <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>predefinito.</span><span class="sxs-lookup"><span data-stu-id="87679-238">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="87679-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87679-239">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="87679-240">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="87679-240">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="87679-241">Considerazioni sul layout per l'elemento WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="87679-241">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="87679-242">Disposizione di controlli Windows Forms nell'esempio WPF</span><span class="sxs-lookup"><span data-stu-id="87679-242">Arranging Windows Forms Controls in WPF Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml)
- [<span data-ttu-id="87679-243">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="87679-243">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="87679-244">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="87679-244">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
