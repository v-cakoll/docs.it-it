---
title: ToggleButton stili e modelli
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: 46fd7d07c3904ee752ae3f467f65af4b0c031c84
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509510"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="6290b-102">ToggleButton stili e modelli</span><span class="sxs-lookup"><span data-stu-id="6290b-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="6290b-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="6290b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="6290b-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="6290b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6290b-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="6290b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="6290b-106">Parti di ToggleButton</span><span class="sxs-lookup"><span data-stu-id="6290b-106">ToggleButton Parts</span></span>

<span data-ttu-id="6290b-107">Il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="6290b-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="6290b-108">Stati di ToggleButton</span><span class="sxs-lookup"><span data-stu-id="6290b-108">ToggleButton States</span></span>

<span data-ttu-id="6290b-109">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="6290b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="6290b-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="6290b-110">VisualState Name</span></span>|<span data-ttu-id="6290b-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="6290b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="6290b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6290b-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="6290b-113">Normale</span><span class="sxs-lookup"><span data-stu-id="6290b-113">Normal</span></span>|<span data-ttu-id="6290b-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6290b-114">CommonStates</span></span>|<span data-ttu-id="6290b-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="6290b-115">The default state.</span></span>|
|<span data-ttu-id="6290b-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="6290b-116">MouseOver</span></span>|<span data-ttu-id="6290b-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6290b-117">CommonStates</span></span>|<span data-ttu-id="6290b-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="6290b-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="6290b-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="6290b-119">Pressed</span></span>|<span data-ttu-id="6290b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6290b-120">CommonStates</span></span>|<span data-ttu-id="6290b-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="6290b-121">The control is pressed.</span></span>|
|<span data-ttu-id="6290b-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="6290b-122">Disabled</span></span>|<span data-ttu-id="6290b-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6290b-123">CommonStates</span></span>|<span data-ttu-id="6290b-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="6290b-124">The control is disabled.</span></span>|
|<span data-ttu-id="6290b-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="6290b-125">Focused</span></span>|<span data-ttu-id="6290b-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6290b-126">FocusStates</span></span>|<span data-ttu-id="6290b-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="6290b-127">The control has focus.</span></span>|
|<span data-ttu-id="6290b-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="6290b-128">Unfocused</span></span>|<span data-ttu-id="6290b-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6290b-129">FocusStates</span></span>|<span data-ttu-id="6290b-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="6290b-130">The control does not have focus.</span></span>|
|<span data-ttu-id="6290b-131">Selezionato con segno di spunta</span><span class="sxs-lookup"><span data-stu-id="6290b-131">Checked</span></span>|<span data-ttu-id="6290b-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="6290b-132">CheckStates</span></span>|<span data-ttu-id="6290b-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="6290b-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="6290b-134">unchecked</span><span class="sxs-lookup"><span data-stu-id="6290b-134">Unchecked</span></span>|<span data-ttu-id="6290b-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="6290b-135">CheckStates</span></span>|<span data-ttu-id="6290b-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="6290b-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="6290b-137">Indeterminato</span><span class="sxs-lookup"><span data-stu-id="6290b-137">Indeterminate</span></span>|<span data-ttu-id="6290b-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="6290b-138">CheckStates</span></span>|<span data-ttu-id="6290b-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> viene `true`, e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `null`.</span><span class="sxs-lookup"><span data-stu-id="6290b-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="6290b-140">Valido</span><span class="sxs-lookup"><span data-stu-id="6290b-140">Valid</span></span>|<span data-ttu-id="6290b-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6290b-141">ValidationStates</span></span>|<span data-ttu-id="6290b-142">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="6290b-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="6290b-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6290b-143">InvalidFocused</span></span>|<span data-ttu-id="6290b-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6290b-144">ValidationStates</span></span>|<span data-ttu-id="6290b-145">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="6290b-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="6290b-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6290b-146">InvalidUnfocused</span></span>|<span data-ttu-id="6290b-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6290b-147">ValidationStates</span></span>|<span data-ttu-id="6290b-148">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="6290b-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="6290b-149">Se lo stato di visualizzazione indeterminato non esiste nel modello di controllo, quindi lo stato di visualizzazione non controllato da utilizzare come stato di visualizzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="6290b-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="6290b-150">Esempio di ControlTemplate ToggleButton</span><span class="sxs-lookup"><span data-stu-id="6290b-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="6290b-151">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="6290b-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="6290b-152">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="6290b-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="6290b-153">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="6290b-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="6290b-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6290b-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="6290b-155">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="6290b-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="6290b-156">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="6290b-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="6290b-157">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="6290b-157">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="6290b-158">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="6290b-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
