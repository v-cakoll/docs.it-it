---
title: Stili e modelli di ToggleButton
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805919"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="04ce2-102">Stili e modelli di ToggleButton</span><span class="sxs-lookup"><span data-stu-id="04ce2-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="04ce2-103">In questo argomento vengono descritti <xref:System.Windows.Controls.Primitives.ToggleButton> gli stili e i modelli per il controllo.</span><span class="sxs-lookup"><span data-stu-id="04ce2-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="04ce2-104">È possibile modificare <xref:System.Windows.Controls.ControlTemplate> l'impostazione predefinita per conferire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="04ce2-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="04ce2-105">Per ulteriori informazioni, vedere [Creare un modello per un controllo.](../../../desktop-wpf/themes/how-to-create-apply-template.md)</span><span class="sxs-lookup"><span data-stu-id="04ce2-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="04ce2-106">Parti ToggleButton</span><span class="sxs-lookup"><span data-stu-id="04ce2-106">ToggleButton Parts</span></span>

<span data-ttu-id="04ce2-107">Il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="04ce2-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="04ce2-108">Stati ToggleButtonToggleButton States</span><span class="sxs-lookup"><span data-stu-id="04ce2-108">ToggleButton States</span></span>

<span data-ttu-id="04ce2-109">Nella tabella seguente sono elencati gli stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="04ce2-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="04ce2-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="04ce2-110">VisualState Name</span></span>|<span data-ttu-id="04ce2-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="04ce2-111">VisualStateGroup Name</span></span>|<span data-ttu-id="04ce2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04ce2-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="04ce2-113">Normale</span><span class="sxs-lookup"><span data-stu-id="04ce2-113">Normal</span></span>|<span data-ttu-id="04ce2-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-114">CommonStates</span></span>|<span data-ttu-id="04ce2-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="04ce2-115">The default state.</span></span>|
|<span data-ttu-id="04ce2-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="04ce2-116">MouseOver</span></span>|<span data-ttu-id="04ce2-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-117">CommonStates</span></span>|<span data-ttu-id="04ce2-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="04ce2-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="04ce2-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="04ce2-119">Pressed</span></span>|<span data-ttu-id="04ce2-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-120">CommonStates</span></span>|<span data-ttu-id="04ce2-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="04ce2-121">The control is pressed.</span></span>|
|<span data-ttu-id="04ce2-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="04ce2-122">Disabled</span></span>|<span data-ttu-id="04ce2-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-123">CommonStates</span></span>|<span data-ttu-id="04ce2-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="04ce2-124">The control is disabled.</span></span>|
|<span data-ttu-id="04ce2-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="04ce2-125">Focused</span></span>|<span data-ttu-id="04ce2-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-126">FocusStates</span></span>|<span data-ttu-id="04ce2-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="04ce2-127">The control has focus.</span></span>|
|<span data-ttu-id="04ce2-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="04ce2-128">Unfocused</span></span>|<span data-ttu-id="04ce2-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-129">FocusStates</span></span>|<span data-ttu-id="04ce2-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="04ce2-130">The control does not have focus.</span></span>|
|<span data-ttu-id="04ce2-131">Selezionato</span><span class="sxs-lookup"><span data-stu-id="04ce2-131">Checked</span></span>|<span data-ttu-id="04ce2-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-132">CheckStates</span></span>|<span data-ttu-id="04ce2-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="04ce2-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="04ce2-134">Non selezionato</span><span class="sxs-lookup"><span data-stu-id="04ce2-134">Unchecked</span></span>|<span data-ttu-id="04ce2-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-135">CheckStates</span></span>|<span data-ttu-id="04ce2-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="04ce2-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="04ce2-137">Indeterminato</span><span class="sxs-lookup"><span data-stu-id="04ce2-137">Indeterminate</span></span>|<span data-ttu-id="04ce2-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-138">CheckStates</span></span>|<span data-ttu-id="04ce2-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> è `true` e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `null`.</span><span class="sxs-lookup"><span data-stu-id="04ce2-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="04ce2-140">Valido</span><span class="sxs-lookup"><span data-stu-id="04ce2-140">Valid</span></span>|<span data-ttu-id="04ce2-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-141">ValidationStates</span></span>|<span data-ttu-id="04ce2-142">Il controllo <xref:System.Windows.Controls.Validation> utilizza la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> classe e `false`la proprietà associata è .</span><span class="sxs-lookup"><span data-stu-id="04ce2-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="04ce2-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="04ce2-143">InvalidFocused</span></span>|<span data-ttu-id="04ce2-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-144">ValidationStates</span></span>|<span data-ttu-id="04ce2-145">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="04ce2-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="04ce2-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="04ce2-146">InvalidUnfocused</span></span>|<span data-ttu-id="04ce2-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04ce2-147">ValidationStates</span></span>|<span data-ttu-id="04ce2-148">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="04ce2-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="04ce2-149">Se lo stato di visualizzazione Indeterminato non esiste nel modello di controllo, lo stato di visualizzazione Unchecked verrà usato come stato di visualizzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="04ce2-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="04ce2-150">Esempio di controllo ToggleButtonToggleButton ControlTemplate Example</span><span class="sxs-lookup"><span data-stu-id="04ce2-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="04ce2-151">Nell'esempio seguente viene <xref:System.Windows.Controls.ControlTemplate> illustrato <xref:System.Windows.Controls.Primitives.ToggleButton> come definire un per il controllo.</span><span class="sxs-lookup"><span data-stu-id="04ce2-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="04ce2-152">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="04ce2-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="04ce2-153">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="04ce2-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="04ce2-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04ce2-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="04ce2-155">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="04ce2-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="04ce2-156">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="04ce2-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="04ce2-157">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="04ce2-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="04ce2-158">Creare un modello per un controlloCreate a template for a control</span><span class="sxs-lookup"><span data-stu-id="04ce2-158">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
