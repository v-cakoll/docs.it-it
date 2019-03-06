---
title: "Procedura dettagliata: Mapping di proprietà tramite l'elemento WindowsFormsHost"
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: 86a7a8a937b9407690d7f1981b91857d1b44ded1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373881"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="b03d3-102">Procedura dettagliata: Mapping di proprietà tramite l'elemento WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="b03d3-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="b03d3-103">Questa procedura dettagliata illustra come usare il <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> proprietà a cui mappare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] delle proprietà alle proprietà corrispondenti in un ambiente host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.</span><span class="sxs-lookup"><span data-stu-id="b03d3-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="b03d3-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="b03d3-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="b03d3-105">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="b03d3-105">Creating the project.</span></span>

-   <span data-ttu-id="b03d3-106">Definizione del layout dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b03d3-106">Defining the application layout.</span></span>

-   <span data-ttu-id="b03d3-107">Definizione di un nuovo mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b03d3-107">Defining a new property mapping.</span></span>

-   <span data-ttu-id="b03d3-108">Definizione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="b03d3-108">Removing a default property mapping.</span></span>

-   <span data-ttu-id="b03d3-109">Sostituzione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="b03d3-109">Replacing a default property mapping.</span></span>

-   <span data-ttu-id="b03d3-110">Estensione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="b03d3-110">Extending a default property mapping.</span></span>

<span data-ttu-id="b03d3-111">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Mapping delle proprietà usando l'esempio di elemento WindowsFormsHost](https://go.microsoft.com/fwlink/?LinkID=160019).</span><span class="sxs-lookup"><span data-stu-id="b03d3-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span></span>

<span data-ttu-id="b03d3-112">Al termine, sarà possibile eseguire il mapping [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] delle proprietà alle proprietà corrispondenti in un ambiente host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.</span><span class="sxs-lookup"><span data-stu-id="b03d3-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b03d3-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b03d3-113">Prerequisites</span></span>

<span data-ttu-id="b03d3-114">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b03d3-114">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="b03d3-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="b03d3-115">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="b03d3-116">Creare e configurare il progetto</span><span class="sxs-lookup"><span data-stu-id="b03d3-116">Create and set up the project</span></span>

1.  <span data-ttu-id="b03d3-117">Creare un **applicazione WPF** progetto denominato `PropertyMappingWithWfhSample`.</span><span class="sxs-lookup"><span data-stu-id="b03d3-117">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2.  <span data-ttu-id="b03d3-118">Nelle **Esplora soluzioni**, aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="b03d3-118">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3.  <span data-ttu-id="b03d3-119">Nelle **Esplora soluzioni**, aggiungere i riferimenti agli assembly System. Drawing e System.</span><span class="sxs-lookup"><span data-stu-id="b03d3-119">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="b03d3-120">Definizione del layout dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b03d3-120">Defining the Application Layout</span></span>

<span data-ttu-id="b03d3-121">Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-base dell'applicazione usa il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento host un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.</span><span class="sxs-lookup"><span data-stu-id="b03d3-121">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="b03d3-122">Per definire il layout dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b03d3-122">To define the application layout</span></span>

1.  <span data-ttu-id="b03d3-123">Aprire Window1.xaml nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b03d3-123">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2.  <span data-ttu-id="b03d3-124">Sostituire il codice esistente con quello seguente.</span><span class="sxs-lookup"><span data-stu-id="b03d3-124">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3.  <span data-ttu-id="b03d3-125">Aprire Window1.xaml.cs nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="b03d3-125">Open Window1.xaml.cs in the Code Editor.</span></span>

4.  <span data-ttu-id="b03d3-126">Nella parte superiore del file importare gli spazi dei nomi seguenti.</span><span class="sxs-lookup"><span data-stu-id="b03d3-126">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="b03d3-127">Definizione di un nuovo mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="b03d3-127">Defining a New Property Mapping</span></span>

<span data-ttu-id="b03d3-128">Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento fornisce mapping di proprietà predefiniti diversi.</span><span class="sxs-lookup"><span data-stu-id="b03d3-128">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="b03d3-129">È possibile aggiungere un nuovo mapping delle proprietà chiamando i <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodo sul <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="b03d3-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="b03d3-130">Per definire un nuovo mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="b03d3-130">To define a new property mapping</span></span>

-   <span data-ttu-id="b03d3-131">Copiare il codice seguente nella definizione per il `Window1` classe.</span><span class="sxs-lookup"><span data-stu-id="b03d3-131">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="b03d3-132">Il `AddClipMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.UIElement.Clip%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b03d3-132">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="b03d3-133">Il `OnClipChange` metodo converte il <xref:System.Windows.UIElement.Clip%2A> proprietà per il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b03d3-133">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="b03d3-134">Il `Window1_SizeChanged` metodo gestisce la finestra <xref:System.Windows.FrameworkElement.SizeChanged> eventi e le dimensioni dell'area di ritaglio per adattarlo alla finestra dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b03d3-134">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="b03d3-135">Rimozione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="b03d3-135">Removing a Default Property Mapping</span></span>

<span data-ttu-id="b03d3-136">Rimuovere un mapping delle proprietà predefinito chiamando il <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> metodo sul <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="b03d3-136">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="b03d3-137">Per rimuovere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="b03d3-137">To remove a default property mapping</span></span>

-   <span data-ttu-id="b03d3-138">Copiare il codice seguente nella definizione per il `Window1` classe.</span><span class="sxs-lookup"><span data-stu-id="b03d3-138">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="b03d3-139">Il `RemoveCursorMapping` metodo elimina il mapping predefinito per il <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b03d3-139">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="b03d3-140">Sostituzione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="b03d3-140">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="b03d3-141">Sostituire un mapping delle proprietà predefinito rimuovendo il mapping predefinito e la chiamata di <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodo sul <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="b03d3-141">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="b03d3-142">Per sostituire un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="b03d3-142">To replace a default property mapping</span></span>

-   <span data-ttu-id="b03d3-143">Copiare il codice seguente nella definizione per il `Window1` classe.</span><span class="sxs-lookup"><span data-stu-id="b03d3-143">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="b03d3-144">Il `ReplaceFlowDirectionMapping` metodo sostituisce il mapping predefinito per il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b03d3-144">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="b03d3-145">Il `OnFlowDirectionChange` metodo converte il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà per il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b03d3-145">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="b03d3-146">Il `cb_CheckedChanged` metodo consente di gestire i <xref:System.Windows.Forms.CheckBox.CheckedChanged> evento sul <xref:System.Windows.Forms.CheckBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="b03d3-146">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="b03d3-147">Assegna il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà in base al valore della <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà</span><span class="sxs-lookup"><span data-stu-id="b03d3-147">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="b03d3-148">Estensione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="b03d3-148">Extending a Default Property Mapping</span></span>

<span data-ttu-id="b03d3-149">È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b03d3-149">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="b03d3-150">Per estendere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="b03d3-150">To extend a default property mapping</span></span>

-   <span data-ttu-id="b03d3-151">Copiare il codice seguente nella definizione per il `Window1` classe.</span><span class="sxs-lookup"><span data-stu-id="b03d3-151">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="b03d3-152">Il `ExtendBackgroundMapping` metodo aggiunge un convertitore di proprietà personalizzata esistente <xref:System.Windows.Controls.Control.Background%2A> mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b03d3-152">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="b03d3-153">Il `OnBackgroundChange` metodo assegna un'immagine specifica del controllo ospitato <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b03d3-153">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="b03d3-154">Il `OnBackgroundChange` metodo viene chiamato dopo aver applicato il mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="b03d3-154">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="b03d3-155">Inizializzazione dei mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="b03d3-155">Initializing Your Property Mappings</span></span>

<span data-ttu-id="b03d3-156">Configurare i mapping delle proprietà chiamando i metodi descritti precedentemente <xref:System.Windows.FrameworkElement.Loaded> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b03d3-156">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="b03d3-157">Per inizializzare i mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="b03d3-157">To initialize your property mappings</span></span>

1.  <span data-ttu-id="b03d3-158">Copiare il codice seguente nella definizione per il `Window1` classe.</span><span class="sxs-lookup"><span data-stu-id="b03d3-158">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="b03d3-159">Il `WindowLoaded` metodo consente di gestire il <xref:System.Windows.FrameworkElement.Loaded> eventi ed esegue l'inizializzazione seguente.</span><span class="sxs-lookup"><span data-stu-id="b03d3-159">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    -   <span data-ttu-id="b03d3-160">Crea una [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="b03d3-160">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>

    -   <span data-ttu-id="b03d3-161">Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b03d3-161">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    -   <span data-ttu-id="b03d3-162">Assegna i valori iniziali alle proprietà mappate.</span><span class="sxs-lookup"><span data-stu-id="b03d3-162">Assigns initial values to the mapped properties.</span></span>

2.  <span data-ttu-id="b03d3-163">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b03d3-163">Press **F5** to build and run the application.</span></span> <span data-ttu-id="b03d3-164">Selezionare la casella di controllo per visualizzare l'effetto del <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span><span class="sxs-lookup"><span data-stu-id="b03d3-164">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="b03d3-165">Quando si seleziona la casella di controllo, il layout inverte l'orientamento da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="b03d3-165">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="b03d3-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b03d3-166">See also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="b03d3-167">Mapping di proprietà di Windows Form e WPF</span><span class="sxs-lookup"><span data-stu-id="b03d3-167">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="b03d3-168">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b03d3-168">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="b03d3-169">Procedura dettagliata: Hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="b03d3-169">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)