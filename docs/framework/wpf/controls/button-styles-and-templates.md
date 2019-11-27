---
title: Stili e modelli di Button
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: ef9f85848ebdda9dc4ae15d0f54847eacd46e24d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283587"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="a2cf3-102">Stili e modelli di Button</span><span class="sxs-lookup"><span data-stu-id="a2cf3-102">Button Styles and Templates</span></span>
<span data-ttu-id="a2cf3-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="a2cf3-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a2cf3-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="a2cf3-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="a2cf3-106">Parti del pulsante</span><span class="sxs-lookup"><span data-stu-id="a2cf3-106">Button Parts</span></span>  
 <span data-ttu-id="a2cf3-107">Il controllo <xref:System.Windows.Controls.Button> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="a2cf3-108">Stati del pulsante</span><span class="sxs-lookup"><span data-stu-id="a2cf3-108">Button States</span></span>  
 <span data-ttu-id="a2cf3-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="a2cf3-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="a2cf3-110">VisualState Name</span></span>|<span data-ttu-id="a2cf3-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a2cf3-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a2cf3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2cf3-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a2cf3-113">Normale</span><span class="sxs-lookup"><span data-stu-id="a2cf3-113">Normal</span></span>|<span data-ttu-id="a2cf3-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a2cf3-114">CommonStates</span></span>|<span data-ttu-id="a2cf3-115">Stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-115">The default state.</span></span>|  
|<span data-ttu-id="a2cf3-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a2cf3-116">MouseOver</span></span>|<span data-ttu-id="a2cf3-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a2cf3-117">CommonStates</span></span>|<span data-ttu-id="a2cf3-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="a2cf3-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="a2cf3-119">Pressed</span></span>|<span data-ttu-id="a2cf3-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a2cf3-120">CommonStates</span></span>|<span data-ttu-id="a2cf3-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-121">The control is pressed.</span></span>|  
|<span data-ttu-id="a2cf3-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="a2cf3-122">Disabled</span></span>|<span data-ttu-id="a2cf3-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a2cf3-123">CommonStates</span></span>|<span data-ttu-id="a2cf3-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-124">The control is disabled.</span></span>|  
|<span data-ttu-id="a2cf3-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="a2cf3-125">Focused</span></span>|<span data-ttu-id="a2cf3-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a2cf3-126">FocusStates</span></span>|<span data-ttu-id="a2cf3-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-127">The control has focus.</span></span>|  
|<span data-ttu-id="a2cf3-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="a2cf3-128">Unfocused</span></span>|<span data-ttu-id="a2cf3-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a2cf3-129">FocusStates</span></span>|<span data-ttu-id="a2cf3-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="a2cf3-131">Valido</span><span class="sxs-lookup"><span data-stu-id="a2cf3-131">Valid</span></span>|<span data-ttu-id="a2cf3-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2cf3-132">ValidationStates</span></span>|<span data-ttu-id="a2cf3-133">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a2cf3-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a2cf3-134">InvalidFocused</span></span>|<span data-ttu-id="a2cf3-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2cf3-135">ValidationStates</span></span>|<span data-ttu-id="a2cf3-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="a2cf3-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a2cf3-137">InvalidUnfocused</span></span>|<span data-ttu-id="a2cf3-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2cf3-138">ValidationStates</span></span>|<span data-ttu-id="a2cf3-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="a2cf3-140">Esempio di ControlTemplate Button</span><span class="sxs-lookup"><span data-stu-id="a2cf3-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="a2cf3-141">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="a2cf3-142">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="a2cf3-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a2cf3-143">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a2cf3-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2cf3-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2cf3-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a2cf3-145">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="a2cf3-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a2cf3-146">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="a2cf3-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a2cf3-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="a2cf3-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a2cf3-148">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="a2cf3-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
