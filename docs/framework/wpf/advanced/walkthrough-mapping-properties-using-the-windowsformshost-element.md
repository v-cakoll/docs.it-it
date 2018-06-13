---
title: "Procedura dettagliata: mapping di proprietà tramite l'elemento WindowsFormsHost"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: 771c0d972420b929ac757ced684de70d2dc7a58d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549302"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="362b7-102">Procedura dettagliata: mapping di proprietà tramite l'elemento WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="362b7-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>
<span data-ttu-id="362b7-103">Questa procedura dettagliata viene illustrato come utilizzare il <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> proprietà da mappare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà alle proprietà corrispondenti di hosting [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.</span><span class="sxs-lookup"><span data-stu-id="362b7-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
 <span data-ttu-id="362b7-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="362b7-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="362b7-105">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="362b7-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="362b7-106">Definizione del layout dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="362b7-106">Defining the application layout.</span></span>  
  
-   <span data-ttu-id="362b7-107">Definizione di un nuovo mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="362b7-107">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="362b7-108">Definizione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="362b7-108">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="362b7-109">Sostituzione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="362b7-109">Replacing a default property mapping.</span></span>  
  
-   <span data-ttu-id="362b7-110">Estensione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="362b7-110">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="362b7-111">Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Mapping delle proprietà utilizzando l'esempio di elemento WindowsFormsHost](http://go.microsoft.com/fwlink/?LinkID=160019).</span><span class="sxs-lookup"><span data-stu-id="362b7-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](http://go.microsoft.com/fwlink/?LinkID=160019).</span></span>  
  
 <span data-ttu-id="362b7-112">Al termine, sarà possibile eseguire il mapping di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà alle proprietà corrispondenti di hosting [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.</span><span class="sxs-lookup"><span data-stu-id="362b7-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="362b7-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="362b7-113">Prerequisites</span></span>  
 <span data-ttu-id="362b7-114">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="362b7-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="362b7-115">.</span><span class="sxs-lookup"><span data-stu-id="362b7-115">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="362b7-116">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="362b7-116">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="362b7-117">Per creare e impostare il progetto</span><span class="sxs-lookup"><span data-stu-id="362b7-117">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="362b7-118">Creare un progetto di applicazione WPF denominato `PropertyMappingWithWfhSample`.</span><span class="sxs-lookup"><span data-stu-id="362b7-118">Create a WPF Application project named `PropertyMappingWithWfhSample`.</span></span>  
  
2.  <span data-ttu-id="362b7-119">In Esplora soluzioni aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration.</span><span class="sxs-lookup"><span data-stu-id="362b7-119">In Solution Explorer, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="362b7-120">In Esplora soluzioni aggiungere riferimenti agli assembly System. Drawing e Forms.</span><span class="sxs-lookup"><span data-stu-id="362b7-120">In Solution Explorer, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="defining-the-application-layout"></a><span data-ttu-id="362b7-121">Definizione del layout dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="362b7-121">Defining the Application Layout</span></span>  
 <span data-ttu-id="362b7-122">Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-in base che utilizza il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento per ospitare un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.</span><span class="sxs-lookup"><span data-stu-id="362b7-122">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-define-the-application-layout"></a><span data-ttu-id="362b7-123">Per definire il layout dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="362b7-123">To define the application layout</span></span>  
  
1.  <span data-ttu-id="362b7-124">Aprire Window1. XAML nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="362b7-124">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="362b7-125">Sostituire il codice esistente con quello seguente.</span><span class="sxs-lookup"><span data-stu-id="362b7-125">Replace the existing code with the following code.</span></span>  
  
     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  <span data-ttu-id="362b7-126">Aprire Window1.xaml.cs nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="362b7-126">Open Window1.xaml.cs in the Code Editor.</span></span>  
  
4.  <span data-ttu-id="362b7-127">Nella parte superiore del file importare gli spazi dei nomi seguenti.</span><span class="sxs-lookup"><span data-stu-id="362b7-127">At the top of the file, import the following namespaces.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="362b7-128">Definizione di un nuovo mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="362b7-128">Defining a New Property Mapping</span></span>  
 <span data-ttu-id="362b7-129">Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento fornisce mapping di proprietà predefiniti diversi.</span><span class="sxs-lookup"><span data-stu-id="362b7-129">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="362b7-130">Per aggiungere un nuovo mapping di proprietà, chiamare il <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodo il <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="362b7-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="362b7-131">Per definire un nuovo mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="362b7-131">To define a new property mapping</span></span>  
  
-   <span data-ttu-id="362b7-132">Copiare il codice seguente nella definizione di `Window1` classe.</span><span class="sxs-lookup"><span data-stu-id="362b7-132">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     <span data-ttu-id="362b7-133">Il `AddClipMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.UIElement.Clip%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="362b7-133">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="362b7-134">Il `OnClipChange` metodo converte il <xref:System.Windows.UIElement.Clip%2A> proprietà per il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="362b7-134">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="362b7-135">Il `Window1_SizeChanged` metodo consente di gestire la finestra <xref:System.Windows.FrameworkElement.SizeChanged> eventi e le dimensioni dell'area di ritaglio per adattarlo alla finestra dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="362b7-135">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="362b7-136">Rimozione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="362b7-136">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="362b7-137">Rimuovere un mapping di proprietà predefinito chiamando il <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> metodo il <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="362b7-137">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="362b7-138">Per rimuovere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="362b7-138">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="362b7-139">Copiare il codice seguente nella definizione di `Window1` classe.</span><span class="sxs-lookup"><span data-stu-id="362b7-139">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     <span data-ttu-id="362b7-140">Il `RemoveCursorMapping` metodo elimina il mapping predefinito per il <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="362b7-140">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>  
  
## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="362b7-141">Sostituzione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="362b7-141">Replacing a Default Property Mapping</span></span>  
 <span data-ttu-id="362b7-142">Sostituire un mapping di proprietà predefinito rimuovendo il mapping predefinito e la chiamata di <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodo il <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="362b7-142">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="362b7-143">Per sostituire un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="362b7-143">To replace a default property mapping</span></span>  
  
-   <span data-ttu-id="362b7-144">Copiare il codice seguente nella definizione di `Window1` classe.</span><span class="sxs-lookup"><span data-stu-id="362b7-144">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     <span data-ttu-id="362b7-145">Il `ReplaceFlowDirectionMapping` metodo sostituisce il mapping predefinito per il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="362b7-145">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>  
  
     <span data-ttu-id="362b7-146">Il `OnFlowDirectionChange` metodo converte il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà per il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="362b7-146">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>  
  
     <span data-ttu-id="362b7-147">Il `cb_CheckedChanged` metodo gestisca il <xref:System.Windows.Forms.CheckBox.CheckedChanged> evento il <xref:System.Windows.Forms.CheckBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="362b7-147">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="362b7-148">Assegna il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà in base al valore del <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà</span><span class="sxs-lookup"><span data-stu-id="362b7-148">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="362b7-149">Estensione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="362b7-149">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="362b7-150">È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.</span><span class="sxs-lookup"><span data-stu-id="362b7-150">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="362b7-151">Per estendere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="362b7-151">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="362b7-152">Copiare il codice seguente nella definizione di `Window1` classe.</span><span class="sxs-lookup"><span data-stu-id="362b7-152">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     <span data-ttu-id="362b7-153">Il `ExtendBackgroundMapping` metodo aggiunge un convertitore di proprietà personalizzato esistente <xref:System.Windows.Controls.Control.Background%2A> mapping di proprietà.</span><span class="sxs-lookup"><span data-stu-id="362b7-153">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>  
  
     <span data-ttu-id="362b7-154">Il `OnBackgroundChange` metodo assegna un'immagine specifica del controllo ospitato <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="362b7-154">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="362b7-155">Il `OnBackgroundChange` metodo viene chiamato dopo aver applicato il mapping di proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="362b7-155">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="362b7-156">Inizializzazione dei mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="362b7-156">Initializing Your Property Mappings</span></span>  
 <span data-ttu-id="362b7-157">Impostare i mapping di proprietà chiamando i metodi descritti in precedenza <xref:System.Windows.FrameworkElement.Loaded> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="362b7-157">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="362b7-158">Per inizializzare i mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="362b7-158">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="362b7-159">Copiare il codice seguente nella definizione di `Window1` classe.</span><span class="sxs-lookup"><span data-stu-id="362b7-159">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     <span data-ttu-id="362b7-160">Il `WindowLoaded` metodo gestisca il <xref:System.Windows.FrameworkElement.Loaded> evento ed esegue le inizializzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="362b7-160">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="362b7-161">Crea un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="362b7-161">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>  
  
    -   <span data-ttu-id="362b7-162">Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="362b7-162">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="362b7-163">Assegna i valori iniziali alle proprietà mappate.</span><span class="sxs-lookup"><span data-stu-id="362b7-163">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="362b7-164">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="362b7-164">Press F5 to build and run the application.</span></span> <span data-ttu-id="362b7-165">Fare clic sulla casella di controllo per visualizzare l'effetto del <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span><span class="sxs-lookup"><span data-stu-id="362b7-165">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="362b7-166">Quando si seleziona la casella di controllo, il layout inverte l'orientamento da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="362b7-166">When you click the check box, the layout reverses its left-right orientation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="362b7-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="362b7-167">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="362b7-168">Mapping di proprietà di Windows Form e WPF</span><span class="sxs-lookup"><span data-stu-id="362b7-168">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="362b7-169">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="362b7-169">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="362b7-170">Procedura dettagliata: hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="362b7-170">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
