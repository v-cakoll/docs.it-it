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
ms.openlocfilehash: 7ff4ff607ab70b55cda1e2c4736ff773d4907a22
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794123"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="8a191-102">Procedura dettagliata: mapping delle proprietà tramite il controllo ElementHost</span><span class="sxs-lookup"><span data-stu-id="8a191-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="8a191-103">In questa procedura dettagliata viene illustrato come utilizzare la proprietà <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> per eseguire il mapping delle proprietà Windows Forms alle proprietà corrispondenti in un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitato.</span><span class="sxs-lookup"><span data-stu-id="8a191-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map Windows Forms properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="8a191-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a191-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="8a191-105">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8a191-105">Creating the project.</span></span>

- <span data-ttu-id="8a191-106">Definizione di un nuovo mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="8a191-106">Defining a new property mapping.</span></span>

- <span data-ttu-id="8a191-107">Definizione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="8a191-107">Removing a default property mapping.</span></span>

- <span data-ttu-id="8a191-108">Estensione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="8a191-108">Extending a default property mapping.</span></span>

<span data-ttu-id="8a191-109">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [mapping delle proprietà tramite l'esempio di controllo ElementHost](https://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="8a191-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="8a191-110">Al termine, sarà possibile eseguire il mapping delle proprietà di Windows Forms alle proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrispondenti su un elemento ospitato.</span><span class="sxs-lookup"><span data-stu-id="8a191-110">When you are finished, you will be able to map Windows Forms properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8a191-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8a191-111">Prerequisites</span></span>

<span data-ttu-id="8a191-112">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a191-112">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="8a191-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8a191-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="8a191-114">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="8a191-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="8a191-115">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="8a191-115">To create the project</span></span>

1. <span data-ttu-id="8a191-116">Creare un progetto di **App Windows Forms** denominato `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="8a191-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="8a191-117">In **Esplora soluzioni**aggiungere riferimenti agli assembly [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] seguenti.</span><span class="sxs-lookup"><span data-stu-id="8a191-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    - <span data-ttu-id="8a191-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="8a191-118">PresentationCore</span></span>

    - <span data-ttu-id="8a191-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="8a191-119">PresentationFramework</span></span>

    - <span data-ttu-id="8a191-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="8a191-120">WindowsBase</span></span>

    - <span data-ttu-id="8a191-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="8a191-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="8a191-122">Copiare il codice seguente nella parte superiore del file di codice `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8a191-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="8a191-123">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8a191-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="8a191-124">Fare doppio clic sul form per aggiungere un gestore eventi per l'evento <xref:System.Windows.Forms.Form.Load>.</span><span class="sxs-lookup"><span data-stu-id="8a191-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="8a191-125">Tornare alla Progettazione Windows Form e aggiungere un gestore eventi per l'evento <xref:System.Windows.Forms.Control.Resize> del modulo.</span><span class="sxs-lookup"><span data-stu-id="8a191-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="8a191-126">Per altre informazioni, vedere [procedura: creare gestori eventi tramite la finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8a191-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="8a191-127">Dichiarare un campo <xref:System.Windows.Forms.Integration.ElementHost> nella classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8a191-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="8a191-128">Definizione di nuovi mapping di proprietà</span><span class="sxs-lookup"><span data-stu-id="8a191-128">Defining New Property Mappings</span></span>

<span data-ttu-id="8a191-129">Il controllo <xref:System.Windows.Forms.Integration.ElementHost> fornisce diversi mapping di proprietà predefiniti.</span><span class="sxs-lookup"><span data-stu-id="8a191-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="8a191-130">Per aggiungere un nuovo mapping della proprietà, chiamare il metodo <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> sul <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>del controllo <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="8a191-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="8a191-131">Per definire nuovi mapping di proprietà</span><span class="sxs-lookup"><span data-stu-id="8a191-131">To define new property mappings</span></span>

1. <span data-ttu-id="8a191-132">Copiare il codice seguente nella definizione della classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8a191-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="8a191-133">Il metodo `AddMarginMapping` aggiunge un nuovo mapping per la proprietà <xref:System.Windows.Forms.Control.Margin%2A>.</span><span class="sxs-lookup"><span data-stu-id="8a191-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="8a191-134">Il metodo `OnMarginChange` converte la proprietà <xref:System.Windows.Forms.Control.Margin%2A> nella proprietà <xref:System.Windows.FrameworkElement.Margin%2A> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a191-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="8a191-135">Copiare il codice seguente nella definizione della classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8a191-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="8a191-136">Il metodo `AddRegionMapping` aggiunge un nuovo mapping per la proprietà <xref:System.Windows.Forms.Control.Region%2A>.</span><span class="sxs-lookup"><span data-stu-id="8a191-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="8a191-137">Il metodo `OnRegionChange` converte la proprietà <xref:System.Windows.Forms.Control.Region%2A> nella proprietà <xref:System.Windows.UIElement.Clip%2A> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a191-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="8a191-138">Il metodo `Form1_Resize` gestisce l'evento <xref:System.Windows.Forms.Control.Resize> del form e ridimensiona l'area di ridimensionamento per adattarla all'elemento ospitato.</span><span class="sxs-lookup"><span data-stu-id="8a191-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="8a191-139">Rimozione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="8a191-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="8a191-140">Rimuovere un mapping di proprietà predefinito chiamando il metodo <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> sul <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>del controllo <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="8a191-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="8a191-141">Per rimuovere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="8a191-141">To remove a default property mapping</span></span>

- <span data-ttu-id="8a191-142">Copiare il codice seguente nella definizione della classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8a191-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="8a191-143">Il metodo `RemoveCursorMapping` Elimina il mapping predefinito per la proprietà <xref:System.Windows.Forms.Control.Cursor%2A>.</span><span class="sxs-lookup"><span data-stu-id="8a191-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="8a191-144">Estensione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="8a191-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="8a191-145">È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8a191-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="8a191-146">Per estendere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="8a191-146">To extend a default property mapping</span></span>

- <span data-ttu-id="8a191-147">Copiare il codice seguente nella definizione della classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8a191-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="8a191-148">Il metodo `ExtendBackColorMapping` aggiunge un convertitore di proprietà personalizzato al mapping della proprietà <xref:System.Windows.Forms.Control.BackColor%2A> esistente.</span><span class="sxs-lookup"><span data-stu-id="8a191-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="8a191-149">Il metodo `OnBackColorChange` assegna un'immagine specifica alla proprietà <xref:System.Windows.Controls.Control.Background%2A> del controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="8a191-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="8a191-150">Il metodo `OnBackColorChange` viene chiamato dopo l'applicazione del mapping di proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="8a191-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="8a191-151">Inizializzare i mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="8a191-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="8a191-152">Copiare il codice seguente nella definizione della classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8a191-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="8a191-153">Il metodo `Form1_Load` gestisce l'evento <xref:System.Windows.Forms.Form.Load> ed esegue l'inizializzazione seguente.</span><span class="sxs-lookup"><span data-stu-id="8a191-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    - <span data-ttu-id="8a191-154">Crea un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="8a191-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    - <span data-ttu-id="8a191-155">Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="8a191-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="8a191-156">Assegna i valori iniziali alle proprietà mappate.</span><span class="sxs-lookup"><span data-stu-id="8a191-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="8a191-157">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8a191-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a191-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a191-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="8a191-159">Mapping di proprietà di Windows Form e WPF</span><span class="sxs-lookup"><span data-stu-id="8a191-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="8a191-160">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8a191-160">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="8a191-161">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="8a191-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
