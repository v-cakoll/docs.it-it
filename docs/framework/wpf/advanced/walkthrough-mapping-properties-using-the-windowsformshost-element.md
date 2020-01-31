---
title: "Procedura dettagliata: mapping di proprietà tramite l'elemento WindowsFormsHost"
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: c076937d6431adf1750793d47ece88dc82edf95c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794110"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="9292d-102">Procedura dettagliata: mapping di proprietà tramite l'elemento WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="9292d-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="9292d-103">In questa procedura dettagliata viene illustrato come utilizzare la proprietà <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> per eseguire il mapping delle proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] alle proprietà corrispondenti in un controllo Windows Forms ospitato.</span><span class="sxs-lookup"><span data-stu-id="9292d-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted Windows Forms control.</span></span>

<span data-ttu-id="9292d-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="9292d-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="9292d-105">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="9292d-105">Creating the project.</span></span>

- <span data-ttu-id="9292d-106">Definizione del layout dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9292d-106">Defining the application layout.</span></span>

- <span data-ttu-id="9292d-107">Definizione di un nuovo mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="9292d-107">Defining a new property mapping.</span></span>

- <span data-ttu-id="9292d-108">Definizione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="9292d-108">Removing a default property mapping.</span></span>

- <span data-ttu-id="9292d-109">Sostituzione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="9292d-109">Replacing a default property mapping.</span></span>

- <span data-ttu-id="9292d-110">Estensione di un mapping delle proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="9292d-110">Extending a default property mapping.</span></span>

<span data-ttu-id="9292d-111">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [mapping delle proprietà tramite l'esempio WindowsFormsHost](https://go.microsoft.com/fwlink/?LinkID=160019).</span><span class="sxs-lookup"><span data-stu-id="9292d-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span></span>

<span data-ttu-id="9292d-112">Al termine, sarà possibile eseguire il mapping delle proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] alle proprietà corrispondenti in un controllo Windows Forms ospitato.</span><span class="sxs-lookup"><span data-stu-id="9292d-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted Windows Forms control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9292d-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9292d-113">Prerequisites</span></span>

<span data-ttu-id="9292d-114">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9292d-114">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="9292d-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="9292d-115">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="9292d-116">Creare e configurare il progetto</span><span class="sxs-lookup"><span data-stu-id="9292d-116">Create and set up the project</span></span>

1. <span data-ttu-id="9292d-117">Creare un progetto di **applicazione WPF** denominato `PropertyMappingWithWfhSample`.</span><span class="sxs-lookup"><span data-stu-id="9292d-117">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2. <span data-ttu-id="9292d-118">In **Esplora soluzioni**aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="9292d-118">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="9292d-119">In **Esplora soluzioni**aggiungere riferimenti agli assembly System. Drawing e System. Windows. Forms.</span><span class="sxs-lookup"><span data-stu-id="9292d-119">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="9292d-120">Definizione del layout dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="9292d-120">Defining the Application Layout</span></span>

<span data-ttu-id="9292d-121">L'applicazione basata su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]usa l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> per ospitare un controllo di Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9292d-121">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a Windows Forms control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="9292d-122">Per definire il layout dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="9292d-122">To define the application layout</span></span>

1. <span data-ttu-id="9292d-123">Aprire Window1. XAML in WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="9292d-123">Open Window1.xaml in the WPF Designer.</span></span>

2. <span data-ttu-id="9292d-124">Sostituire il codice esistente con quello seguente.</span><span class="sxs-lookup"><span data-stu-id="9292d-124">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. <span data-ttu-id="9292d-125">Aprire Window1.xaml.cs nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="9292d-125">Open Window1.xaml.cs in the Code Editor.</span></span>

4. <span data-ttu-id="9292d-126">Nella parte superiore del file importare gli spazi dei nomi seguenti.</span><span class="sxs-lookup"><span data-stu-id="9292d-126">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="9292d-127">Definizione di un nuovo mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="9292d-127">Defining a New Property Mapping</span></span>

<span data-ttu-id="9292d-128">L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> fornisce diversi mapping di proprietà predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9292d-128">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="9292d-129">Per aggiungere un nuovo mapping della proprietà, chiamare il metodo <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> sul <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>dell'elemento del <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="9292d-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="9292d-130">Per definire un nuovo mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="9292d-130">To define a new property mapping</span></span>

- <span data-ttu-id="9292d-131">Copiare il codice seguente nella definizione della classe `Window1`.</span><span class="sxs-lookup"><span data-stu-id="9292d-131">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="9292d-132">Il metodo `AddClipMapping` aggiunge un nuovo mapping per la proprietà <xref:System.Windows.UIElement.Clip%2A>.</span><span class="sxs-lookup"><span data-stu-id="9292d-132">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="9292d-133">Il metodo `OnClipChange` converte la proprietà <xref:System.Windows.UIElement.Clip%2A> nella proprietà<xref:System.Windows.Forms.Control.Region%2A> Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9292d-133">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the Windows Forms<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="9292d-134">Il metodo `Window1_SizeChanged` gestisce l'evento <xref:System.Windows.FrameworkElement.SizeChanged> della finestra e ridimensiona l'area di ridimensionamento per adattarla alla finestra dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9292d-134">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="9292d-135">Rimozione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="9292d-135">Removing a Default Property Mapping</span></span>

<span data-ttu-id="9292d-136">Rimuovere un mapping di proprietà predefinito chiamando il metodo <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> sul <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>dell'elemento del <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="9292d-136">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="9292d-137">Per rimuovere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="9292d-137">To remove a default property mapping</span></span>

- <span data-ttu-id="9292d-138">Copiare il codice seguente nella definizione della classe `Window1`.</span><span class="sxs-lookup"><span data-stu-id="9292d-138">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="9292d-139">Il metodo `RemoveCursorMapping` Elimina il mapping predefinito per la proprietà <xref:System.Windows.FrameworkElement.Cursor%2A>.</span><span class="sxs-lookup"><span data-stu-id="9292d-139">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="9292d-140">Sostituzione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="9292d-140">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="9292d-141">Sostituire un mapping di proprietà predefinito rimuovendo il mapping predefinito e chiamando il metodo <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> sul <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>dell'elemento del <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="9292d-141">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="9292d-142">Per sostituire un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="9292d-142">To replace a default property mapping</span></span>

- <span data-ttu-id="9292d-143">Copiare il codice seguente nella definizione della classe `Window1`.</span><span class="sxs-lookup"><span data-stu-id="9292d-143">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="9292d-144">Il metodo `ReplaceFlowDirectionMapping` sostituisce il mapping predefinito per la proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="9292d-144">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="9292d-145">Il metodo `OnFlowDirectionChange` converte la proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A> nella proprietà<xref:System.Windows.Forms.Control.RightToLeft%2A> Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9292d-145">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the Windows Forms<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="9292d-146">Il metodo `cb_CheckedChanged` gestisce l'evento <xref:System.Windows.Forms.CheckBox.CheckedChanged> sul controllo <xref:System.Windows.Forms.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="9292d-146">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="9292d-147">Assegna la proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A> in base al valore della proprietà <xref:System.Windows.Forms.CheckBox.CheckState%2A></span><span class="sxs-lookup"><span data-stu-id="9292d-147">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="9292d-148">Estensione di un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="9292d-148">Extending a Default Property Mapping</span></span>

<span data-ttu-id="9292d-149">È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9292d-149">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="9292d-150">Per estendere un mapping delle proprietà predefinito</span><span class="sxs-lookup"><span data-stu-id="9292d-150">To extend a default property mapping</span></span>

- <span data-ttu-id="9292d-151">Copiare il codice seguente nella definizione della classe `Window1`.</span><span class="sxs-lookup"><span data-stu-id="9292d-151">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="9292d-152">Il metodo `ExtendBackgroundMapping` aggiunge un convertitore di proprietà personalizzato al mapping della proprietà <xref:System.Windows.Controls.Control.Background%2A> esistente.</span><span class="sxs-lookup"><span data-stu-id="9292d-152">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="9292d-153">Il metodo `OnBackgroundChange` assegna un'immagine specifica alla proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> del controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="9292d-153">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="9292d-154">Il metodo `OnBackgroundChange` viene chiamato dopo l'applicazione del mapping di proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="9292d-154">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="9292d-155">Inizializzazione dei mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="9292d-155">Initializing Your Property Mappings</span></span>

<span data-ttu-id="9292d-156">Configurare i mapping delle proprietà chiamando i metodi descritti in precedenza nel gestore eventi <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="9292d-156">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="9292d-157">Per inizializzare i mapping delle proprietà</span><span class="sxs-lookup"><span data-stu-id="9292d-157">To initialize your property mappings</span></span>

1. <span data-ttu-id="9292d-158">Copiare il codice seguente nella definizione della classe `Window1`.</span><span class="sxs-lookup"><span data-stu-id="9292d-158">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="9292d-159">Il metodo `WindowLoaded` gestisce l'evento <xref:System.Windows.FrameworkElement.Loaded> ed esegue l'inizializzazione seguente.</span><span class="sxs-lookup"><span data-stu-id="9292d-159">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    - <span data-ttu-id="9292d-160">Crea una Windows Forms controllo<xref:System.Windows.Forms.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="9292d-160">Creates a Windows Forms<xref:System.Windows.Forms.CheckBox> control.</span></span>

    - <span data-ttu-id="9292d-161">Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="9292d-161">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="9292d-162">Assegna i valori iniziali alle proprietà mappate.</span><span class="sxs-lookup"><span data-stu-id="9292d-162">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="9292d-163">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9292d-163">Press **F5** to build and run the application.</span></span> <span data-ttu-id="9292d-164">Fare clic sulla casella di controllo per visualizzare l'effetto del mapping del <xref:System.Windows.FrameworkElement.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="9292d-164">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="9292d-165">Quando si seleziona la casella di controllo, il layout inverte l'orientamento da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="9292d-165">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="9292d-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9292d-166">See also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="9292d-167">Mapping di proprietà di Windows Form e WPF</span><span class="sxs-lookup"><span data-stu-id="9292d-167">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="9292d-168">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9292d-168">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="9292d-169">Procedura dettagliata: hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="9292d-169">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
