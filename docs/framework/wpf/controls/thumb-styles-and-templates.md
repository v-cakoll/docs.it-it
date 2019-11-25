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
ms.openlocfilehash: 0d0d88e3b527beacfa5f879027e696aa75b18147
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283687"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="65851-102">Stili e modelli di Thumb</span><span class="sxs-lookup"><span data-stu-id="65851-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="65851-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="65851-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="65851-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="65851-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="65851-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="65851-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="65851-106">Parti Thumb</span><span class="sxs-lookup"><span data-stu-id="65851-106">Thumb Parts</span></span>

<span data-ttu-id="65851-107">Il controllo <xref:System.Windows.Controls.Primitives.Thumb> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="65851-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="65851-108">Stati Thumb</span><span class="sxs-lookup"><span data-stu-id="65851-108">Thumb States</span></span>

<span data-ttu-id="65851-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="65851-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="65851-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="65851-110">VisualState Name</span></span>|<span data-ttu-id="65851-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="65851-111">VisualStateGroup Name</span></span>|<span data-ttu-id="65851-112">description</span><span class="sxs-lookup"><span data-stu-id="65851-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="65851-113">Normale</span><span class="sxs-lookup"><span data-stu-id="65851-113">Normal</span></span>|<span data-ttu-id="65851-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="65851-114">CommonStates</span></span>|<span data-ttu-id="65851-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="65851-115">The default state.</span></span>|
|<span data-ttu-id="65851-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="65851-116">MouseOver</span></span>|<span data-ttu-id="65851-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="65851-117">CommonStates</span></span>|<span data-ttu-id="65851-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="65851-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="65851-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="65851-119">Pressed</span></span>|<span data-ttu-id="65851-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="65851-120">CommonStates</span></span>|<span data-ttu-id="65851-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="65851-121">The control is pressed.</span></span>|
|<span data-ttu-id="65851-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="65851-122">Disabled</span></span>|<span data-ttu-id="65851-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="65851-123">CommonStates</span></span>|<span data-ttu-id="65851-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="65851-124">The control is disabled.</span></span>|
|<span data-ttu-id="65851-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="65851-125">Focused</span></span>|<span data-ttu-id="65851-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="65851-126">FocusStates</span></span>|<span data-ttu-id="65851-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="65851-127">The control has focus.</span></span>|
|<span data-ttu-id="65851-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="65851-128">Unfocused</span></span>|<span data-ttu-id="65851-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="65851-129">FocusStates</span></span>|<span data-ttu-id="65851-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="65851-130">The control does not have focus.</span></span>|
|<span data-ttu-id="65851-131">Valido</span><span class="sxs-lookup"><span data-stu-id="65851-131">Valid</span></span>|<span data-ttu-id="65851-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65851-132">ValidationStates</span></span>|<span data-ttu-id="65851-133">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="65851-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="65851-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="65851-134">InvalidFocused</span></span>|<span data-ttu-id="65851-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65851-135">ValidationStates</span></span>|<span data-ttu-id="65851-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="65851-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="65851-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="65851-137">InvalidUnfocused</span></span>|<span data-ttu-id="65851-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65851-138">ValidationStates</span></span>|<span data-ttu-id="65851-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="65851-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="65851-140">Esempio di ControlTemplate Thumb</span><span class="sxs-lookup"><span data-stu-id="65851-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="65851-141">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="65851-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="65851-142">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="65851-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="65851-143">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="65851-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="65851-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65851-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="65851-145">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="65851-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="65851-146">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="65851-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="65851-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="65851-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="65851-148">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="65851-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
