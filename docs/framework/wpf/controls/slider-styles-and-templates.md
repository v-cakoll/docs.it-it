---
title: Stili e modelli di Slider
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: f533142d5ba202bd4aaf628487eaaa2a18a535d0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283381"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="0a2d6-102">Stili e modelli di Slider</span><span class="sxs-lookup"><span data-stu-id="0a2d6-102">Slider Styles and Templates</span></span>
<span data-ttu-id="0a2d6-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="0a2d6-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0a2d6-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="0a2d6-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="0a2d6-106">Parti del dispositivo di scorrimento</span><span class="sxs-lookup"><span data-stu-id="0a2d6-106">Slider Parts</span></span>  
 <span data-ttu-id="0a2d6-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="0a2d6-108">Parte</span><span class="sxs-lookup"><span data-stu-id="0a2d6-108">Part</span></span>|<span data-ttu-id="0a2d6-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="0a2d6-109">Type</span></span>|<span data-ttu-id="0a2d6-110">description</span><span class="sxs-lookup"><span data-stu-id="0a2d6-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0a2d6-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="0a2d6-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="0a2d6-112">Contenitore per l'elemento che indica la posizione del <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="0a2d6-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="0a2d6-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="0a2d6-114">Elemento che visualizza un intervallo di selezione lungo il <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="0a2d6-115">L'intervallo di selezione è visibile solo se la proprietà <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="0a2d6-116">Stati del dispositivo di scorrimento</span><span class="sxs-lookup"><span data-stu-id="0a2d6-116">Slider States</span></span>  
 <span data-ttu-id="0a2d6-117">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="0a2d6-118">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="0a2d6-118">VisualState Name</span></span>|<span data-ttu-id="0a2d6-119">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="0a2d6-119">VisualStateGroup Name</span></span>|<span data-ttu-id="0a2d6-120">description</span><span class="sxs-lookup"><span data-stu-id="0a2d6-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="0a2d6-121">Normale</span><span class="sxs-lookup"><span data-stu-id="0a2d6-121">Normal</span></span>|<span data-ttu-id="0a2d6-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0a2d6-122">CommonStates</span></span>|<span data-ttu-id="0a2d6-123">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-123">The default state.</span></span>|  
|<span data-ttu-id="0a2d6-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0a2d6-124">MouseOver</span></span>|<span data-ttu-id="0a2d6-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0a2d6-125">CommonStates</span></span>|<span data-ttu-id="0a2d6-126">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="0a2d6-127">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="0a2d6-127">Disabled</span></span>|<span data-ttu-id="0a2d6-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0a2d6-128">CommonStates</span></span>|<span data-ttu-id="0a2d6-129">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-129">The control is disabled.</span></span>|  
|<span data-ttu-id="0a2d6-130">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="0a2d6-130">Focused</span></span>|<span data-ttu-id="0a2d6-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0a2d6-131">FocusStates</span></span>|<span data-ttu-id="0a2d6-132">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-132">The control has focus.</span></span>|  
|<span data-ttu-id="0a2d6-133">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="0a2d6-133">Unfocused</span></span>|<span data-ttu-id="0a2d6-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0a2d6-134">FocusStates</span></span>|<span data-ttu-id="0a2d6-135">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="0a2d6-136">Valido</span><span class="sxs-lookup"><span data-stu-id="0a2d6-136">Valid</span></span>|<span data-ttu-id="0a2d6-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0a2d6-137">ValidationStates</span></span>|<span data-ttu-id="0a2d6-138">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0a2d6-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0a2d6-139">InvalidFocused</span></span>|<span data-ttu-id="0a2d6-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0a2d6-140">ValidationStates</span></span>|<span data-ttu-id="0a2d6-141">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0a2d6-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0a2d6-142">InvalidUnfocused</span></span>|<span data-ttu-id="0a2d6-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0a2d6-143">ValidationStates</span></span>|<span data-ttu-id="0a2d6-144">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="0a2d6-145">Esempio di ControlTemplate Slider</span><span class="sxs-lookup"><span data-stu-id="0a2d6-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="0a2d6-146">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="0a2d6-147">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="0a2d6-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0a2d6-148">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="0a2d6-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a2d6-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a2d6-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0a2d6-150">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="0a2d6-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0a2d6-151">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="0a2d6-151">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0a2d6-152">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="0a2d6-152">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="0a2d6-153">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="0a2d6-153">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
