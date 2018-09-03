---
title: 'Procedura dettagliata: mapping delle proprietà tramite il controllo ElementHost'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 34119d889c8d6600fdda12cac33192c32d8e0fa6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467124"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="2ca7f-102">Procedura dettagliata: mapping delle proprietà tramite il controllo ElementHost</span><span class="sxs-lookup"><span data-stu-id="2ca7f-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="2ca7f-103">Questa procedura dettagliata illustra come usare il <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> proprietà a cui mappare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] delle proprietà alle proprietà corrispondenti in un ambiente host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="2ca7f-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ca7f-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="2ca7f-105">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-105">Creating the project.</span></span>

-   <span data-ttu-id="2ca7f-106">Definizione di un nuovo mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-106">Defining a new property mapping.</span></span>

-   <span data-ttu-id="2ca7f-107">Definizione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-107">Removing a default property mapping.</span></span>

-   <span data-ttu-id="2ca7f-108">Estensione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-108">Extending a default property mapping.</span></span>

<span data-ttu-id="2ca7f-109">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Mapping delle proprietà usando l'esempio di controllo ElementHost](https://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="2ca7f-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="2ca7f-110">Al termine, sarà possibile eseguire il mapping [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proprietà corrispondente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le proprietà di un elemento ospitato.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ca7f-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2ca7f-111">Prerequisites</span></span>

<span data-ttu-id="2ca7f-112">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ca7f-112">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="2ca7f-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="2ca7f-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="2ca7f-114">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="2ca7f-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="2ca7f-115">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="2ca7f-115">To create the project</span></span>

1.  <span data-ttu-id="2ca7f-116">Creare un **App di Windows. Forms** progetto denominato `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2.  <span data-ttu-id="2ca7f-117">Nelle **Esplora soluzioni**, aggiungere i riferimenti ai seguenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assembly.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    -   <span data-ttu-id="2ca7f-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="2ca7f-118">PresentationCore</span></span>

    -   <span data-ttu-id="2ca7f-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="2ca7f-119">PresentationFramework</span></span>

    -   <span data-ttu-id="2ca7f-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="2ca7f-120">WindowsBase</span></span>

    -   <span data-ttu-id="2ca7f-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="2ca7f-121">WindowsFormsIntegration</span></span>

3.  <span data-ttu-id="2ca7f-122">Copiare il codice seguente nella parte superiore del `Form1` file di codice.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4.  <span data-ttu-id="2ca7f-123">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="2ca7f-124">Fare doppio clic sul form per aggiungere un gestore eventi per il <xref:System.Windows.Forms.Form.Load> evento.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5.  <span data-ttu-id="2ca7f-125">Tornare alla finestra di progettazione Windows Form e aggiungere un gestore eventi per il form <xref:System.Windows.Forms.Control.Resize> evento.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="2ca7f-126">Per altre informazioni, vedere [procedura: creare impostazioni delle applicazioni usando la finestra di progettazione](https://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span><span class="sxs-lookup"><span data-stu-id="2ca7f-126">For more information, see [How to: Create Event Handlers Using the Designer](https://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>

6.  <span data-ttu-id="2ca7f-127">Dichiarare un <xref:System.Windows.Forms.Integration.ElementHost> campo il `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="2ca7f-128">La definizione di nuovi mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="2ca7f-128">Defining New Property Mappings</span></span>

<span data-ttu-id="2ca7f-129">Il <xref:System.Windows.Forms.Integration.ElementHost> controllo fornisce mapping di proprietà predefiniti diversi.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="2ca7f-130">È possibile aggiungere un nuovo mapping delle proprietà chiamando i <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodo sul <xref:System.Windows.Forms.Integration.ElementHost> del controllo <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="2ca7f-131">Per definire nuovi mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="2ca7f-131">To define new property mappings</span></span>

1.  <span data-ttu-id="2ca7f-132">Copiare il codice seguente nella definizione per il `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="2ca7f-133">Il `AddMarginMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.Forms.Control.Margin%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="2ca7f-134">Il `OnMarginChange` metodo converte il <xref:System.Windows.Forms.Control.Margin%2A> proprietà per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2.  <span data-ttu-id="2ca7f-135">Copiare il codice seguente nella definizione per il `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="2ca7f-136">Il `AddRegionMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.Forms.Control.Region%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="2ca7f-137">Il `OnRegionChange` metodo converte il <xref:System.Windows.Forms.Control.Region%2A> proprietà per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="2ca7f-138">Il `Form1_Resize` metodo gestisce il form <xref:System.Windows.Forms.Control.Resize> eventi e le dimensioni dell'area di ritaglio per adattarlo all'elemento ospitato.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="2ca7f-139">Rimozione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="2ca7f-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="2ca7f-140">Rimuovere un mapping delle proprietà predefinito chiamando il <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> metodo sul <xref:System.Windows.Forms.Integration.ElementHost> del controllo <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="2ca7f-141">Per rimuovere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="2ca7f-141">To remove a default property mapping</span></span>

-   <span data-ttu-id="2ca7f-142">Copiare il codice seguente nella definizione per il `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="2ca7f-143">Il `RemoveCursorMapping` metodo elimina il mapping predefinito per il <xref:System.Windows.Forms.Control.Cursor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="2ca7f-144">Estensione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="2ca7f-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="2ca7f-145">È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="2ca7f-146">Per estendere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="2ca7f-146">To extend a default property mapping</span></span>

-   <span data-ttu-id="2ca7f-147">Copiare il codice seguente nella definizione per il `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="2ca7f-148">Il `ExtendBackColorMapping` metodo aggiunge un convertitore di proprietà personalizzata esistente <xref:System.Windows.Forms.Control.BackColor%2A> mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="2ca7f-149">Il `OnBackColorChange` metodo assegna un'immagine specifica del controllo ospitato <xref:System.Windows.Controls.Control.Background%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="2ca7f-150">Il `OnBackColorChange` metodo viene chiamato dopo aver applicato il mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="2ca7f-151">Inizializzare i mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="2ca7f-151">Initialize your property mappings</span></span>

1.  <span data-ttu-id="2ca7f-152">Copiare il codice seguente nella definizione per il `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="2ca7f-153">Il `Form1_Load` metodo consente di gestire il <xref:System.Windows.Forms.Form.Load> eventi ed esegue l'inizializzazione seguente.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    -   <span data-ttu-id="2ca7f-154">Crea una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    -   <span data-ttu-id="2ca7f-155">Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    -   <span data-ttu-id="2ca7f-156">Assegna i valori iniziali alle proprietà mappate.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-156">Assigns initial values to the mapped properties.</span></span>

2.  <span data-ttu-id="2ca7f-157">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2ca7f-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ca7f-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ca7f-158">See Also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="2ca7f-159">Mapping di proprietà di Windows Form e WPF</span><span class="sxs-lookup"><span data-stu-id="2ca7f-159">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="2ca7f-160">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2ca7f-160">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="2ca7f-161">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="2ca7f-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)