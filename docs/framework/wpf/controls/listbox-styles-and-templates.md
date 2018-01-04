---
title: Stili e modelli di ListBox
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edf8c50424a9694c4e00f5bf319d3122999bda85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="listbox-styles-and-templates"></a><span data-ttu-id="da538-102">Stili e modelli di ListBox</span><span class="sxs-lookup"><span data-stu-id="da538-102">ListBox Styles and Templates</span></span>
<span data-ttu-id="da538-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.ListBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="da538-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="da538-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="da538-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="da538-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="da538-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="listbox-parts"></a><span data-ttu-id="da538-106">Parti di ListBox</span><span class="sxs-lookup"><span data-stu-id="da538-106">ListBox Parts</span></span>  
 <span data-ttu-id="da538-107">Il <xref:System.Windows.Controls.ListBox> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="da538-107">The <xref:System.Windows.Controls.ListBox> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="da538-108">Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.ListBox>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="da538-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ListBox>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="da538-109">(Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.ListBox>; <xref:System.Windows.Controls.ScrollViewer> Abilita lo scorrimento all'interno del controllo).</span><span class="sxs-lookup"><span data-stu-id="da538-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ListBox>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="da538-110">Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="da538-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="listbox-states"></a><span data-ttu-id="da538-111">Stati di ListBox</span><span class="sxs-lookup"><span data-stu-id="da538-111">ListBox States</span></span>  
 <span data-ttu-id="da538-112">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.ListBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="da538-112">The following table lists the visual states for the <xref:System.Windows.Controls.ListBox> control.</span></span>  
  
|<span data-ttu-id="da538-113">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="da538-113">VisualState Name</span></span>|<span data-ttu-id="da538-114">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="da538-114">VisualStateGroup Name</span></span>|<span data-ttu-id="da538-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da538-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="da538-116">Valido</span><span class="sxs-lookup"><span data-stu-id="da538-116">Valid</span></span>|<span data-ttu-id="da538-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="da538-117">ValidationStates</span></span>|<span data-ttu-id="da538-118">Il controllo è valido.</span><span class="sxs-lookup"><span data-stu-id="da538-118">The control is valid.</span></span>|  
|<span data-ttu-id="da538-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="da538-119">InvalidFocused</span></span>|<span data-ttu-id="da538-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="da538-120">ValidationStates</span></span>|<span data-ttu-id="da538-121">Il controllo non è valido e ha uno stato attivo.</span><span class="sxs-lookup"><span data-stu-id="da538-121">The control is not valid and has focus.</span></span>|  
|<span data-ttu-id="da538-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="da538-122">InvalidUnfocused</span></span>|<span data-ttu-id="da538-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="da538-123">ValidationStates</span></span>|<span data-ttu-id="da538-124">Il controllo non è valido e non ha uno stato attivo.</span><span class="sxs-lookup"><span data-stu-id="da538-124">The control is not valid and does not have focus.</span></span>|  
  
## <a name="listboxitem-parts"></a><span data-ttu-id="da538-125">Parti di ListBoxItem</span><span class="sxs-lookup"><span data-stu-id="da538-125">ListBoxItem Parts</span></span>  
 <span data-ttu-id="da538-126">Il <xref:System.Windows.Controls.ListBoxItem> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="da538-126">The <xref:System.Windows.Controls.ListBoxItem> control does not have any named parts.</span></span>  
  
## <a name="listboxitem-states"></a><span data-ttu-id="da538-127">Stati di ListBoxItem</span><span class="sxs-lookup"><span data-stu-id="da538-127">ListBoxItem States</span></span>  
 <span data-ttu-id="da538-128">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.ListBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="da538-128">The following table lists the visual states for the <xref:System.Windows.Controls.ListBox> control.</span></span>  
  
|<span data-ttu-id="da538-129">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="da538-129">VisualState Name</span></span>|<span data-ttu-id="da538-130">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="da538-130">VisualStateGroup Name</span></span>|<span data-ttu-id="da538-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da538-131">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="da538-132">Normale</span><span class="sxs-lookup"><span data-stu-id="da538-132">Normal</span></span>|<span data-ttu-id="da538-133">CommonStates</span><span class="sxs-lookup"><span data-stu-id="da538-133">CommonStates</span></span>|<span data-ttu-id="da538-134">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="da538-134">The default state.</span></span>|  
|<span data-ttu-id="da538-135">MouseOver</span><span class="sxs-lookup"><span data-stu-id="da538-135">MouseOver</span></span>|<span data-ttu-id="da538-136">CommonStates</span><span class="sxs-lookup"><span data-stu-id="da538-136">CommonStates</span></span>|<span data-ttu-id="da538-137">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="da538-137">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="da538-138">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="da538-138">Disabled</span></span>|<span data-ttu-id="da538-139">CommonStates</span><span class="sxs-lookup"><span data-stu-id="da538-139">CommonStates</span></span>|<span data-ttu-id="da538-140">L'elemento è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="da538-140">The item is disabled.</span></span>|  
|<span data-ttu-id="da538-141">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="da538-141">Focused</span></span>|<span data-ttu-id="da538-142">FocusStates</span><span class="sxs-lookup"><span data-stu-id="da538-142">FocusStates</span></span>|<span data-ttu-id="da538-143">L'elemento ha uno stato attivo.</span><span class="sxs-lookup"><span data-stu-id="da538-143">The item has focus.</span></span>|  
|<span data-ttu-id="da538-144">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="da538-144">Unfocused</span></span>|<span data-ttu-id="da538-145">FocusStates</span><span class="sxs-lookup"><span data-stu-id="da538-145">FocusStates</span></span>|<span data-ttu-id="da538-146">L'elemento non ha uno stato attivo.</span><span class="sxs-lookup"><span data-stu-id="da538-146">The item does not have focus.</span></span>|  
|<span data-ttu-id="da538-147">Deselezionato</span><span class="sxs-lookup"><span data-stu-id="da538-147">Unselected</span></span>|<span data-ttu-id="da538-148">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="da538-148">SelectionStates</span></span>|<span data-ttu-id="da538-149">L'elemento non è selezionato.</span><span class="sxs-lookup"><span data-stu-id="da538-149">The item is not selected.</span></span>|  
|<span data-ttu-id="da538-150">Selezionato</span><span class="sxs-lookup"><span data-stu-id="da538-150">Selected</span></span>|<span data-ttu-id="da538-151">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="da538-151">SelectionStates</span></span>|<span data-ttu-id="da538-152">L'elemento è attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="da538-152">The item is currentlyplate selected.</span></span>|  
|<span data-ttu-id="da538-153">SelectedUnfocused</span><span class="sxs-lookup"><span data-stu-id="da538-153">SelectedUnfocused</span></span>|<span data-ttu-id="da538-154">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="da538-154">SelectionStates</span></span>|<span data-ttu-id="da538-155">L'elemento è selezionato, ma non ha uno stato attivo.</span><span class="sxs-lookup"><span data-stu-id="da538-155">The item is selected, but does not have focus.</span></span>|  
|<span data-ttu-id="da538-156">Valido</span><span class="sxs-lookup"><span data-stu-id="da538-156">Valid</span></span>|<span data-ttu-id="da538-157">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="da538-157">ValidationStates</span></span>|<span data-ttu-id="da538-158">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="da538-158">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="da538-159">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="da538-159">InvalidFocused</span></span>|<span data-ttu-id="da538-160">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="da538-160">ValidationStates</span></span>|<span data-ttu-id="da538-161">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="da538-161">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="da538-162">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="da538-162">InvalidUnfocused</span></span>|<span data-ttu-id="da538-163">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="da538-163">ValidationStates</span></span>|<span data-ttu-id="da538-164">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="da538-164">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="listbox-controltemplate-example"></a><span data-ttu-id="da538-165">Esempio di ControlTemplate ListBox</span><span class="sxs-lookup"><span data-stu-id="da538-165">ListBox ControlTemplate Example</span></span>  
 <span data-ttu-id="da538-166">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.ListBoxItem> controlli.</span><span class="sxs-lookup"><span data-stu-id="da538-166">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ListBox> and <xref:System.Windows.Controls.ListBoxItem> controls.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
 <span data-ttu-id="da538-167">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="da538-167">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="da538-168">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="da538-168">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da538-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da538-169">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="da538-170">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="da538-170">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="da538-171">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="da538-171">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="da538-172">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="da538-172">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="da538-173">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="da538-173">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
