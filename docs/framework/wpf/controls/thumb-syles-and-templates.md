---
title: Stili e modelli di Thumb
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: e987932e00be09fdf5ac34bb2bfb24a890368a15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596384"
---
# <a name="thumb-syles-and-templates"></a><span data-ttu-id="79cf9-102">Stili e modelli di Thumb</span><span class="sxs-lookup"><span data-stu-id="79cf9-102">Thumb Syles and Templates</span></span>
<span data-ttu-id="79cf9-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.Primitives.Thumb> controllo.</span><span class="sxs-lookup"><span data-stu-id="79cf9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="79cf9-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="79cf9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="79cf9-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="79cf9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="thumb-parts"></a><span data-ttu-id="79cf9-106">Parti di Thumb</span><span class="sxs-lookup"><span data-stu-id="79cf9-106">Thumb Parts</span></span>  
 <span data-ttu-id="79cf9-107">Il <xref:System.Windows.Controls.Primitives.Thumb> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="79cf9-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>  
  
## <a name="thumb-states"></a><span data-ttu-id="79cf9-108">Stati di Thumb</span><span class="sxs-lookup"><span data-stu-id="79cf9-108">Thumb States</span></span>  
 <span data-ttu-id="79cf9-109">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.Thumb> controllo.</span><span class="sxs-lookup"><span data-stu-id="79cf9-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
|<span data-ttu-id="79cf9-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="79cf9-110">VisualState Name</span></span>|<span data-ttu-id="79cf9-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="79cf9-111">VisualStateGroup Name</span></span>|<span data-ttu-id="79cf9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79cf9-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="79cf9-113">Normale</span><span class="sxs-lookup"><span data-stu-id="79cf9-113">Normal</span></span>|<span data-ttu-id="79cf9-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="79cf9-114">CommonStates</span></span>|<span data-ttu-id="79cf9-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="79cf9-115">The default state.</span></span>|  
|<span data-ttu-id="79cf9-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="79cf9-116">MouseOver</span></span>|<span data-ttu-id="79cf9-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="79cf9-117">CommonStates</span></span>|<span data-ttu-id="79cf9-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="79cf9-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="79cf9-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="79cf9-119">Pressed</span></span>|<span data-ttu-id="79cf9-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="79cf9-120">CommonStates</span></span>|<span data-ttu-id="79cf9-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="79cf9-121">The control is pressed.</span></span>|  
|<span data-ttu-id="79cf9-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="79cf9-122">Disabled</span></span>|<span data-ttu-id="79cf9-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="79cf9-123">CommonStates</span></span>|<span data-ttu-id="79cf9-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="79cf9-124">The control is disabled.</span></span>|  
|<span data-ttu-id="79cf9-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="79cf9-125">Focused</span></span>|<span data-ttu-id="79cf9-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="79cf9-126">FocusStates</span></span>|<span data-ttu-id="79cf9-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="79cf9-127">The control has focus.</span></span>|  
|<span data-ttu-id="79cf9-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="79cf9-128">Unfocused</span></span>|<span data-ttu-id="79cf9-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="79cf9-129">FocusStates</span></span>|<span data-ttu-id="79cf9-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="79cf9-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="79cf9-131">Valido</span><span class="sxs-lookup"><span data-stu-id="79cf9-131">Valid</span></span>|<span data-ttu-id="79cf9-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="79cf9-132">ValidationStates</span></span>|<span data-ttu-id="79cf9-133">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="79cf9-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="79cf9-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="79cf9-134">InvalidFocused</span></span>|<span data-ttu-id="79cf9-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="79cf9-135">ValidationStates</span></span>|<span data-ttu-id="79cf9-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="79cf9-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="79cf9-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="79cf9-137">InvalidUnfocused</span></span>|<span data-ttu-id="79cf9-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="79cf9-138">ValidationStates</span></span>|<span data-ttu-id="79cf9-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="79cf9-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="thumb-controltemplate-example"></a><span data-ttu-id="79cf9-140">Esempio di ControlTemplate Thumb</span><span class="sxs-lookup"><span data-stu-id="79cf9-140">Thumb ControlTemplate Example</span></span>  
 <span data-ttu-id="79cf9-141">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.Thumb> controllo.</span><span class="sxs-lookup"><span data-stu-id="79cf9-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]  
  
 <span data-ttu-id="79cf9-142">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="79cf9-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="79cf9-143">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="79cf9-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79cf9-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79cf9-144">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="79cf9-145">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="79cf9-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="79cf9-146">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="79cf9-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="79cf9-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="79cf9-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="79cf9-148">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="79cf9-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
