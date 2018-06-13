---
title: 'Procedura dettagliata: mapping delle proprietà tramite il controllo ElementHost'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: b5af1f45a0d01761358e83c890544ec1a11836e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549191"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="f7455-102">Procedura dettagliata: mapping delle proprietà tramite il controllo ElementHost</span><span class="sxs-lookup"><span data-stu-id="f7455-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>
<span data-ttu-id="f7455-103">Questa procedura dettagliata viene illustrato come utilizzare il <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> proprietà da mappare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proprietà alle proprietà corrispondenti di hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="f7455-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>  
  
 <span data-ttu-id="f7455-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7455-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="f7455-105">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="f7455-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="f7455-106">Definizione di un nuovo mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7455-106">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="f7455-107">Definizione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="f7455-107">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="f7455-108">Estensione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="f7455-108">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="f7455-109">Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Mapping delle proprietà utilizzando l'esempio di controllo ElementHost](http://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="f7455-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](http://go.microsoft.com/fwlink/?LinkID=160018).</span></span>  
  
 <span data-ttu-id="f7455-110">Al termine, sarà possibile eseguire il mapping di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proprietà corrispondente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le proprietà di un elemento ospitato.</span><span class="sxs-lookup"><span data-stu-id="f7455-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f7455-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f7455-111">Prerequisites</span></span>  
 <span data-ttu-id="f7455-112">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7455-112">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="f7455-113">.</span><span class="sxs-lookup"><span data-stu-id="f7455-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="f7455-114">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="f7455-114">Creating the Project</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="f7455-115">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="f7455-115">To create the project</span></span>  
  
1.  <span data-ttu-id="f7455-116">Creare un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] progetto di applicazione denominato `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="f7455-116">Create a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project named `PropertyMappingWithElementHost`.</span></span> <span data-ttu-id="f7455-117">Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione Windows Form](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="f7455-117">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="f7455-118">In Esplora soluzioni aggiungere riferimenti ai seguenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assembly.</span><span class="sxs-lookup"><span data-stu-id="f7455-118">In Solution Explorer, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>  
  
    -   <span data-ttu-id="f7455-119">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="f7455-119">PresentationCore</span></span>  
  
    -   <span data-ttu-id="f7455-120">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="f7455-120">PresentationFramework</span></span>  
  
    -   <span data-ttu-id="f7455-121">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="f7455-121">WindowsBase</span></span>  
  
    -   <span data-ttu-id="f7455-122">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="f7455-122">WindowsFormsIntegration</span></span>  
  
3.  <span data-ttu-id="f7455-123">Copiare il codice seguente all'inizio del `Form1` file di codice.</span><span class="sxs-lookup"><span data-stu-id="f7455-123">Copy the following code into the top of the `Form1` code file.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  <span data-ttu-id="f7455-124">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f7455-124">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="f7455-125">Fare doppio clic sul form per aggiungere un gestore eventi per il <xref:System.Windows.Forms.Form.Load> evento.</span><span class="sxs-lookup"><span data-stu-id="f7455-125">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
5.  <span data-ttu-id="f7455-126">Tornare a Progettazione Windows Form e aggiungere un gestore eventi per il modulo <xref:System.Windows.Forms.Control.Resize> evento.</span><span class="sxs-lookup"><span data-stu-id="f7455-126">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="f7455-127">Per ulteriori informazioni, vedere [procedura: creare di gestori di eventi utilizzando la finestra di progettazione](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span><span class="sxs-lookup"><span data-stu-id="f7455-127">For more information, see [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>  
  
6.  <span data-ttu-id="f7455-128">Dichiarare un <xref:System.Windows.Forms.Integration.ElementHost> campo la `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="f7455-128">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## <a name="defining-new-property-mappings"></a><span data-ttu-id="f7455-129">Definizione di nuovi mapping di proprietà</span><span class="sxs-lookup"><span data-stu-id="f7455-129">Defining New Property Mappings</span></span>  
 <span data-ttu-id="f7455-130">Il <xref:System.Windows.Forms.Integration.ElementHost> controllo fornisce mapping di proprietà predefiniti diversi.</span><span class="sxs-lookup"><span data-stu-id="f7455-130">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="f7455-131">Per aggiungere un nuovo mapping di proprietà, chiamare il <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodo il <xref:System.Windows.Forms.Integration.ElementHost> del controllo <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="f7455-131">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-new-property-mappings"></a><span data-ttu-id="f7455-132">Per definire nuovi mapping di proprietà</span><span class="sxs-lookup"><span data-stu-id="f7455-132">To define new property mappings</span></span>  
  
1.  <span data-ttu-id="f7455-133">Copiare il codice seguente nella definizione di `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="f7455-133">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     <span data-ttu-id="f7455-134">Il `AddMarginMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.Forms.Control.Margin%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7455-134">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>  
  
     <span data-ttu-id="f7455-135">Il `OnMarginChange` metodo converte il <xref:System.Windows.Forms.Control.Margin%2A> proprietà per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7455-135">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>  
  
2.  <span data-ttu-id="f7455-136">Copiare il codice seguente nella definizione di `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="f7455-136">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     <span data-ttu-id="f7455-137">Il `AddRegionMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.Forms.Control.Region%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7455-137">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="f7455-138">Il `OnRegionChange` metodo converte il <xref:System.Windows.Forms.Control.Region%2A> proprietà per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7455-138">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="f7455-139">Il `Form1_Resize` metodo gestisce il modulo <xref:System.Windows.Forms.Control.Resize> eventi e le dimensioni dell'area di ritaglio per adattarlo all'elemento ospitato.</span><span class="sxs-lookup"><span data-stu-id="f7455-139">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="f7455-140">Rimozione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="f7455-140">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="f7455-141">Rimuovere un mapping di proprietà predefinito chiamando il <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> metodo il <xref:System.Windows.Forms.Integration.ElementHost> del controllo <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="f7455-141">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="f7455-142">Per rimuovere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="f7455-142">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="f7455-143">Copiare il codice seguente nella definizione di `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="f7455-143">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     <span data-ttu-id="f7455-144">Il `RemoveCursorMapping` metodo elimina il mapping predefinito per il <xref:System.Windows.Forms.Control.Cursor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7455-144">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="f7455-145">Estensione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="f7455-145">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="f7455-146">È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f7455-146">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="f7455-147">Per estendere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="f7455-147">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="f7455-148">Copiare il codice seguente nella definizione di `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="f7455-148">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     <span data-ttu-id="f7455-149">Il `ExtendBackColorMapping` metodo aggiunge un convertitore di proprietà personalizzato esistente <xref:System.Windows.Forms.Control.BackColor%2A> mapping di proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7455-149">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>  
  
     <span data-ttu-id="f7455-150">Il `OnBackColorChange` metodo assegna un'immagine specifica del controllo ospitato <xref:System.Windows.Controls.Control.Background%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7455-150">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="f7455-151">Il `OnBackColorChange` metodo viene chiamato dopo aver applicato il mapping di proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="f7455-151">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="f7455-152">Inizializzazione dei mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="f7455-152">Initializing Your Property Mappings</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="f7455-153">Per inizializzare i mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="f7455-153">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="f7455-154">Copiare il codice seguente nella definizione di `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="f7455-154">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     <span data-ttu-id="f7455-155">Il `Form1_Load` metodo gestisca il <xref:System.Windows.Forms.Form.Load> evento ed esegue le inizializzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f7455-155">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="f7455-156">Crea un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="f7455-156">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>  
  
    -   <span data-ttu-id="f7455-157">Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7455-157">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="f7455-158">Assegna i valori iniziali alle proprietà mappate.</span><span class="sxs-lookup"><span data-stu-id="f7455-158">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="f7455-159">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f7455-159">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7455-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7455-160">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="f7455-161">Mapping di proprietà di Windows Form e WPF</span><span class="sxs-lookup"><span data-stu-id="f7455-161">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="f7455-162">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="f7455-162">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="f7455-163">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f7455-163">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
