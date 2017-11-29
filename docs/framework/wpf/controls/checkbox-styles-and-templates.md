---
title: Stili e modelli di CheckBox
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], CheckBox
- templates [WPF], CheckBox
- parts [WPF], CheckBox
- ControlTemplate [WPF], CheckBox
- CheckBox [WPF], styles and templates
- styles [WPF], CheckBox
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c901d710e96cd111104b9fef2219b157377adc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="60211-102">Stili e modelli di CheckBox</span><span class="sxs-lookup"><span data-stu-id="60211-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="60211-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.CheckBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="60211-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="60211-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="60211-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="60211-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="60211-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="60211-106">Parti di casella di controllo</span><span class="sxs-lookup"><span data-stu-id="60211-106">CheckBox Parts</span></span>  
 <span data-ttu-id="60211-107">Il <xref:System.Windows.Controls.CheckBox> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="60211-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="60211-108">Stati di casella di controllo</span><span class="sxs-lookup"><span data-stu-id="60211-108">CheckBox States</span></span>  
 <span data-ttu-id="60211-109">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.CheckBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="60211-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="60211-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="60211-110">VisualState Name</span></span>|<span data-ttu-id="60211-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="60211-111">VisualStateGroup Name</span></span>|<span data-ttu-id="60211-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60211-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="60211-113">Normale</span><span class="sxs-lookup"><span data-stu-id="60211-113">Normal</span></span>|<span data-ttu-id="60211-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="60211-114">CommonStates</span></span>|<span data-ttu-id="60211-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="60211-115">The default state.</span></span>|  
|<span data-ttu-id="60211-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="60211-116">MouseOver</span></span>|<span data-ttu-id="60211-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="60211-117">CommonStates</span></span>|<span data-ttu-id="60211-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="60211-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="60211-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="60211-119">Pressed</span></span>|<span data-ttu-id="60211-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="60211-120">CommonStates</span></span>|<span data-ttu-id="60211-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="60211-121">The control is pressed.</span></span>|  
|<span data-ttu-id="60211-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="60211-122">Disabled</span></span>|<span data-ttu-id="60211-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="60211-123">CommonStates</span></span>|<span data-ttu-id="60211-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="60211-124">The control is disabled.</span></span>|  
|<span data-ttu-id="60211-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="60211-125">Focused</span></span>|<span data-ttu-id="60211-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="60211-126">FocusStates</span></span>|<span data-ttu-id="60211-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="60211-127">The control has focus.</span></span>|  
|<span data-ttu-id="60211-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="60211-128">Unfocused</span></span>|<span data-ttu-id="60211-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="60211-129">FocusStates</span></span>|<span data-ttu-id="60211-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="60211-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="60211-131">Selezionato con segno di spunta</span><span class="sxs-lookup"><span data-stu-id="60211-131">Checked</span></span>|<span data-ttu-id="60211-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="60211-132">CheckStates</span></span>|<span data-ttu-id="60211-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="60211-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="60211-134">non è selezionata</span><span class="sxs-lookup"><span data-stu-id="60211-134">Unchecked</span></span>|<span data-ttu-id="60211-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="60211-135">CheckStates</span></span>|<span data-ttu-id="60211-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="60211-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="60211-137">Indeterminato</span><span class="sxs-lookup"><span data-stu-id="60211-137">Indeterminate</span></span>|<span data-ttu-id="60211-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="60211-138">CheckStates</span></span>|<span data-ttu-id="60211-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>è `true`, e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `null`.</span><span class="sxs-lookup"><span data-stu-id="60211-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="60211-140">Valido</span><span class="sxs-lookup"><span data-stu-id="60211-140">Valid</span></span>|<span data-ttu-id="60211-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="60211-141">ValidationStates</span></span>|<span data-ttu-id="60211-142">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="60211-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="60211-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="60211-143">InvalidUnfocused</span></span>|<span data-ttu-id="60211-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="60211-144">ValidationStates</span></span>|<span data-ttu-id="60211-145">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="60211-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="60211-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="60211-146">InvalidFocused</span></span>|<span data-ttu-id="60211-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="60211-147">ValidationStates</span></span>|<span data-ttu-id="60211-148">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="60211-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="60211-149">Esempio di ControlTemplate del controllo casella di controllo</span><span class="sxs-lookup"><span data-stu-id="60211-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="60211-150">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.CheckBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="60211-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="60211-151">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="60211-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="60211-152">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="60211-152">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60211-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60211-153">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="60211-154">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="60211-154">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="60211-155">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="60211-155">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="60211-156">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="60211-156">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="60211-157">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="60211-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
