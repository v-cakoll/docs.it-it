---
title: 'Procedura dettagliata: Disposizione di controlli Windows Form in WPF'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: fa0181e95a03324c4cfa9395ae57439c260d1c23
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972303"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="592f1-102">Procedura dettagliata: Disposizione di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="592f1-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="592f1-103">Questa procedura dettagliata illustra come usare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le funzionalità di layout per disporre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] i controlli in un'applicazione ibrida.</span><span class="sxs-lookup"><span data-stu-id="592f1-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>

<span data-ttu-id="592f1-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="592f1-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="592f1-105">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="592f1-105">Creating the project.</span></span>

- <span data-ttu-id="592f1-106">Uso delle impostazioni di layout predefinite.</span><span class="sxs-lookup"><span data-stu-id="592f1-106">Using default layout settings.</span></span>

- <span data-ttu-id="592f1-107">Ridimensionamento in base al contenuto.</span><span class="sxs-lookup"><span data-stu-id="592f1-107">Sizing to content.</span></span>

- <span data-ttu-id="592f1-108">Uso del posizionamento assoluto.</span><span class="sxs-lookup"><span data-stu-id="592f1-108">Using absolute positioning.</span></span>

- <span data-ttu-id="592f1-109">Specifica esplicita delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="592f1-109">Specifying size explicitly.</span></span>

- <span data-ttu-id="592f1-110">Impostazione delle proprietà di layout.</span><span class="sxs-lookup"><span data-stu-id="592f1-110">Setting layout properties.</span></span>

- <span data-ttu-id="592f1-111">Informazioni sulle limitazioni di z order.</span><span class="sxs-lookup"><span data-stu-id="592f1-111">Understanding z-order limitations.</span></span>

- <span data-ttu-id="592f1-112">Ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="592f1-112">Docking.</span></span>

- <span data-ttu-id="592f1-113">Impostazione della visibilità.</span><span class="sxs-lookup"><span data-stu-id="592f1-113">Setting visibility.</span></span>

- <span data-ttu-id="592f1-114">Hosting di un controllo che non si adatta.</span><span class="sxs-lookup"><span data-stu-id="592f1-114">Hosting a control that does not stretch.</span></span>

- <span data-ttu-id="592f1-115">Ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="592f1-115">Scaling.</span></span>

- <span data-ttu-id="592f1-116">Rotazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-116">Rotating.</span></span>

- <span data-ttu-id="592f1-117">Impostazione della spaziatura interna e dei margini.</span><span class="sxs-lookup"><span data-stu-id="592f1-117">Setting padding and margins.</span></span>

- <span data-ttu-id="592f1-118">Uso di contenitori di layout dinamici.</span><span class="sxs-lookup"><span data-stu-id="592f1-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="592f1-119">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [disposizione di Windows Forms controlli in WPF di esempio](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="592f1-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="592f1-120">Al termine, si avrà una conoscenza delle funzionalità di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]applicazioni basate su.</span><span class="sxs-lookup"><span data-stu-id="592f1-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="592f1-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="592f1-121">Prerequisites</span></span>

<span data-ttu-id="592f1-122">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="592f1-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="592f1-123">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="592f1-123">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="592f1-124">Per creare e impostare il progetto</span><span class="sxs-lookup"><span data-stu-id="592f1-124">To create and set up the project</span></span>

1. <span data-ttu-id="592f1-125">Creare un progetto di applicazione WPF `WpfLayoutHostingWf`denominato.</span><span class="sxs-lookup"><span data-stu-id="592f1-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="592f1-126">In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.</span><span class="sxs-lookup"><span data-stu-id="592f1-126">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="592f1-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="592f1-127">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="592f1-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="592f1-128">System.Windows.Forms</span></span>

    - <span data-ttu-id="592f1-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="592f1-129">System.Drawing</span></span>

3. <span data-ttu-id="592f1-130">Fare doppio clic sul file MainWindow.xaml per aprirlo nella visualizzazione XAML.</span><span class="sxs-lookup"><span data-stu-id="592f1-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>

4. <span data-ttu-id="592f1-131">Nell'elemento aggiungere il mapping dello spazio dei nomi seguente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. <xref:System.Windows.Window></span><span class="sxs-lookup"><span data-stu-id="592f1-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="592f1-132">Nell'elemento impostare la <xref:System.Windows.Controls.Grid.ShowGridLines%2A> proprietà su `true` e definire cinque righe e tre colonne. <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="592f1-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="592f1-133">Uso delle impostazioni di layout predefinite</span><span class="sxs-lookup"><span data-stu-id="592f1-133">Using Default Layout Settings</span></span>

<span data-ttu-id="592f1-134">Per impostazione predefinita, <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento gestisce il layout per il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="592f1-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-use-default-layout-settings"></a><span data-ttu-id="592f1-135">Per usare le impostazioni di layout predefinite</span><span class="sxs-lookup"><span data-stu-id="592f1-135">To use default layout settings</span></span>

1. <span data-ttu-id="592f1-136">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="592f1-137">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-138"><xref:System.Windows.Controls.Canvas>Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo<xref:System.Windows.Forms.Button?displayProperty=nameWithType> viene visualizzato in.</span><span class="sxs-lookup"><span data-stu-id="592f1-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="592f1-139">Il controllo ospitato viene ridimensionato in base al relativo contenuto e <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento viene dimensionato per contenere il controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="592f1-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="592f1-140">Ridimensionamento in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="592f1-140">Sizing to Content</span></span>

<span data-ttu-id="592f1-141">L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento garantisce che il controllo ospitato venga ridimensionato per visualizzare correttamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="592f1-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

### <a name="to-size-to-content"></a><span data-ttu-id="592f1-142">Per ridimensionare in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="592f1-142">To size to content</span></span>

1. <span data-ttu-id="592f1-143">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="592f1-144">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-145">I due nuovi controlli pulsante vengono ridimensionati in modo da visualizzare la stringa di testo più lunga e le dimensioni <xref:System.Windows.Forms.Integration.WindowsFormsHost> del carattere più grandi e gli elementi vengono ridimensionati per contenere i controlli ospitati.</span><span class="sxs-lookup"><span data-stu-id="592f1-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="592f1-146">Uso del posizionamento assoluto</span><span class="sxs-lookup"><span data-stu-id="592f1-146">Using Absolute Positioning</span></span>

<span data-ttu-id="592f1-147">È possibile usare il posizionamento assoluto per posizionare <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento in un punto qualsiasi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="592f1-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

### <a name="to-use-absolute-positioning"></a><span data-ttu-id="592f1-148">Per usare il posizionamento assoluto</span><span class="sxs-lookup"><span data-stu-id="592f1-148">To use absolute positioning</span></span>

1. <span data-ttu-id="592f1-149">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="592f1-150">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-151">L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene inserito a 20 pixel dal lato superiore della cella della griglia e a 20 pixel da sinistra.</span><span class="sxs-lookup"><span data-stu-id="592f1-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="592f1-152">Specifica esplicita delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="592f1-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="592f1-153">È possibile specificare le dimensioni dell' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento usando le <xref:System.Windows.FrameworkElement.Width%2A> proprietà e <xref:System.Windows.FrameworkElement.Height%2A> .</span><span class="sxs-lookup"><span data-stu-id="592f1-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

### <a name="to-specify-size-explicitly"></a><span data-ttu-id="592f1-154">Per specificare le dimensioni in modo esplicito</span><span class="sxs-lookup"><span data-stu-id="592f1-154">To specify size explicitly</span></span>

1. <span data-ttu-id="592f1-155">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="592f1-156">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-157">L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento è impostato su una dimensione di 50 pixel in larghezza per 70 pixel di altezza, minore rispetto alle impostazioni predefinite del layout.</span><span class="sxs-lookup"><span data-stu-id="592f1-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="592f1-158">Il contenuto del [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene ridisposto di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="592f1-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="592f1-159">Impostazione delle proprietà di layout</span><span class="sxs-lookup"><span data-stu-id="592f1-159">Setting Layout Properties</span></span>

<span data-ttu-id="592f1-160">Impostare sempre le proprietà correlate al layout nel controllo ospitato usando le proprietà dell' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="592f1-161">L'impostazione diretta delle proprietà di layout nel controllo ospitato darà risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="592f1-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="592f1-162">L'impostazione delle proprietà correlate al layout nel controllo ospitato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="592f1-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="592f1-163">Per visualizzare gli effetti dell'impostazione delle proprietà nel controllo</span><span class="sxs-lookup"><span data-stu-id="592f1-163">To see the effects of setting properties on the hosted control</span></span>

1. <span data-ttu-id="592f1-164">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="592f1-165">In Esplora soluzioni fare doppio clic su MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="592f1-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="592f1-166">vb o MainWindow.xaml.cs per aprirlo nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="592f1-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>

3. <span data-ttu-id="592f1-167">Copiare il codice seguente nella definizione `MainWindow` della classe.</span><span class="sxs-lookup"><span data-stu-id="592f1-167">Copy the following code into the `MainWindow` class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="592f1-168">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-168">Press F5 to build and run the application.</span></span>

5. <span data-ttu-id="592f1-169">Fare clic sul pulsante **fare clic su me** .</span><span class="sxs-lookup"><span data-stu-id="592f1-169">Click the **Click me** button.</span></span> <span data-ttu-id="592f1-170">Il `button1_Click` gestore eventi imposta le <xref:System.Windows.Forms.Control.Top%2A> proprietà <xref:System.Windows.Forms.Control.Left%2A> e sul controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="592f1-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="592f1-171">In questo modo il controllo ospitato viene riposizionato all'interno dell' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="592f1-172">L'host mantiene la stessa area dello schermo, ma il controllo ospitato viene ritagliato.</span><span class="sxs-lookup"><span data-stu-id="592f1-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="592f1-173">Al contrario, il controllo ospitato deve sempre riempire <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="592f1-174">Informazioni sulle limitazioni di z order</span><span class="sxs-lookup"><span data-stu-id="592f1-174">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="592f1-175">Gli <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementi visibili vengono sempre disegnati sopra gli altri elementi WPF e non sono interessati dall'ordine z.</span><span class="sxs-lookup"><span data-stu-id="592f1-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="592f1-176">Per visualizzare questo comportamento dell'ordine z, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="592f1-176">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="592f1-177">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="592f1-178">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-179">L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene disegnato sull'elemento label.</span><span class="sxs-lookup"><span data-stu-id="592f1-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="592f1-180">Ancoraggio</span><span class="sxs-lookup"><span data-stu-id="592f1-180">Docking</span></span>

<span data-ttu-id="592f1-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost>l'elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta l'ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="592f1-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="592f1-182">Impostare la <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà associata per ancorare il controllo ospitato in <xref:System.Windows.Controls.DockPanel> un elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="592f1-183">Per ancorare un controllo ospitato</span><span class="sxs-lookup"><span data-stu-id="592f1-183">To dock a hosted control</span></span>

1. <span data-ttu-id="592f1-184">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="592f1-185">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-186">L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento è ancorato al lato destro <xref:System.Windows.Controls.DockPanel> dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="592f1-187">Impostazione della visibilità</span><span class="sxs-lookup"><span data-stu-id="592f1-187">Setting Visibility</span></span>

<span data-ttu-id="592f1-188">È possibile rendere il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo invisibile o comprimerlo impostando <xref:System.Windows.UIElement.Visibility%2A> la proprietà sull' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="592f1-189">Quando un controllo non è visibile, non viene visualizzato, ma occupa spazio del layout.</span><span class="sxs-lookup"><span data-stu-id="592f1-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="592f1-190">Quando un controllo è compresso, non viene visualizzato né occupa spazio del layout.</span><span class="sxs-lookup"><span data-stu-id="592f1-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="592f1-191">Per impostare la visibilità di un controllo ospitato</span><span class="sxs-lookup"><span data-stu-id="592f1-191">To set the visibility of a hosted control</span></span>

1. <span data-ttu-id="592f1-192">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="592f1-193">In MainWindow.xaml.vb o MainWindow.xaml.cs copiare il codice seguente nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="592f1-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="592f1-194">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-194">Press F5 to build and run the application.</span></span>

4. <span data-ttu-id="592f1-195">Fare clic sul pulsante **fare clic per rendere invisibile** per <xref:System.Windows.Forms.Integration.WindowsFormsHost> rendere invisibile l'elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="592f1-196">Fare clic sul pulsante **fare clic per** comprimere per nascondere completamente l' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento del layout.</span><span class="sxs-lookup"><span data-stu-id="592f1-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="592f1-197">Quando il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene compresso, gli elementi circostanti vengono ridisposti per occuparne lo spazio.</span><span class="sxs-lookup"><span data-stu-id="592f1-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="592f1-198">Hosting di un controllo che non si adatta</span><span class="sxs-lookup"><span data-stu-id="592f1-198">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="592f1-199">Alcuni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli hanno dimensioni fisse e non si adattano per riempire lo spazio disponibile nel layout.</span><span class="sxs-lookup"><span data-stu-id="592f1-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="592f1-200">Ad esempio, il <xref:System.Windows.Forms.MonthCalendar> controllo Visualizza un mese in uno spazio fisso.</span><span class="sxs-lookup"><span data-stu-id="592f1-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="592f1-201">Per ospitare un controllo che non si adatta</span><span class="sxs-lookup"><span data-stu-id="592f1-201">To host a control that does not stretch</span></span>

1. <span data-ttu-id="592f1-202">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="592f1-203">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-204">L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento è centrato nella riga della griglia, ma non viene allungato per riempire lo spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="592f1-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="592f1-205">Se la finestra è sufficientemente grande, è possibile che vengano visualizzati due o più mesi dal controllo <xref:System.Windows.Forms.MonthCalendar> ospitato, che però sono centrati nella riga.</span><span class="sxs-lookup"><span data-stu-id="592f1-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="592f1-206">Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motore di layout centra gli elementi che non possono essere ridimensionati per riempire lo spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="592f1-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="592f1-207">Ridimensionamento</span><span class="sxs-lookup"><span data-stu-id="592f1-207">Scaling</span></span>

<span data-ttu-id="592f1-208">Diversamente dagli elementi WPF, la maggior parte dei controlli Windows Forms non è continuamente scalabile.</span><span class="sxs-lookup"><span data-stu-id="592f1-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="592f1-209">Per fornire scalabilità personalizzata, eseguire l' <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> override del metodo.</span><span class="sxs-lookup"><span data-stu-id="592f1-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="592f1-210">Per ridimensionare un controllo ospitato usando il comportamento predefinito</span><span class="sxs-lookup"><span data-stu-id="592f1-210">To scale a hosted control by using the default behavior</span></span>

1. <span data-ttu-id="592f1-211">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="592f1-212">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-213">Il controllo ospitato e gli elementi che lo circondano vengono ridimensionati in base a un fattore di 0,5.</span><span class="sxs-lookup"><span data-stu-id="592f1-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="592f1-214">Tuttavia il tipo di carattere del controllo ospitato non viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="592f1-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="592f1-215">Rotazione</span><span class="sxs-lookup"><span data-stu-id="592f1-215">Rotating</span></span>

<span data-ttu-id="592f1-216">Diversamente dagli elementi WPF, i controlli Windows Forms non supportano la rotazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="592f1-217">L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento non viene ruotato con altri elementi WPF quando viene applicata una trasformazione di rotazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="592f1-218">Qualsiasi valore di rotazione diverso da 180 gradi genera <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> l'evento.</span><span class="sxs-lookup"><span data-stu-id="592f1-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="592f1-219">Per visualizzare l'effetto di rotazione in un'applicazione ibrida</span><span class="sxs-lookup"><span data-stu-id="592f1-219">To see the effect of rotation in a hybrid application</span></span>

1. <span data-ttu-id="592f1-220">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="592f1-221">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-222">Il controllo ospitato non viene ruotato, ma i relativi elementi circostanti vengono ruotati di 180 gradi.</span><span class="sxs-lookup"><span data-stu-id="592f1-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="592f1-223">Potrebbe essere necessario ridimensionare la finestra per vedere gli elementi.</span><span class="sxs-lookup"><span data-stu-id="592f1-223">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="592f1-224">Impostazione della spaziatura interna e dei margini</span><span class="sxs-lookup"><span data-stu-id="592f1-224">Setting Padding and Margins</span></span>

<span data-ttu-id="592f1-225">La spaziatura interna e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] i margini nel layout sono simili a spaziatura interna e margini in. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]</span><span class="sxs-lookup"><span data-stu-id="592f1-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="592f1-226">È sufficiente impostare <xref:System.Windows.Controls.Control.Padding%2A> le <xref:System.Windows.FrameworkElement.Margin%2A> proprietà e sull' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="592f1-227">Per impostare spaziatura interna e margini per un controllo ospitato</span><span class="sxs-lookup"><span data-stu-id="592f1-227">To set padding and margins for a hosted control</span></span>

1. <span data-ttu-id="592f1-228">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="592f1-229">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-230">Le impostazioni di spaziatura interna e margini vengono [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] applicate ai controlli ospitati nello stesso modo in cui [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]verrebbero applicate.</span><span class="sxs-lookup"><span data-stu-id="592f1-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="592f1-231">Uso di contenitori di layout dinamici</span><span class="sxs-lookup"><span data-stu-id="592f1-231">Using Dynamic Layout Containers</span></span>

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="592f1-232">fornisce due contenitori di layout dinamici <xref:System.Windows.Forms.FlowLayoutPanel> , <xref:System.Windows.Forms.TableLayoutPanel>e.</span><span class="sxs-lookup"><span data-stu-id="592f1-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="592f1-233">È anche possibile usare questi contenitori nei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout.</span><span class="sxs-lookup"><span data-stu-id="592f1-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="592f1-234">Per usare un contenitore di layout dinamico</span><span class="sxs-lookup"><span data-stu-id="592f1-234">To use a dynamic layout container</span></span>

1. <span data-ttu-id="592f1-235">Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="592f1-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="592f1-236">In MainWindow.xaml.vb o MainWindow.xaml.cs copiare il codice seguente nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="592f1-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="592f1-237">Aggiungere una chiamata al metodo `InitializeFlowLayoutPanel` nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="592f1-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="592f1-238">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="592f1-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="592f1-239">L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento riempie l' <xref:System.Windows.Controls.DockPanel>oggetto e <xref:System.Windows.Forms.FlowLayoutPanel> dispone i relativi controlli figlio nel valore predefinito <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="592f1-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="592f1-240">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="592f1-240">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="592f1-241">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="592f1-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="592f1-242">Considerazioni sul layout per l'elemento WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="592f1-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="592f1-243">Disposizione di controlli Windows Forms nell'esempio WPF</span><span class="sxs-lookup"><span data-stu-id="592f1-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="592f1-244">Procedura dettagliata: Hosting di un controllo Windows Forms composito in WPF</span><span class="sxs-lookup"><span data-stu-id="592f1-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="592f1-245">Procedura dettagliata: Hosting di un controllo composito WPF in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="592f1-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
