---
title: I modelli e stili di RepeatButton
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 86f212326bc707e4b07b8cab8d9a95d4f6ef8920
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509590"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="56bfa-102">I modelli e stili di RepeatButton</span><span class="sxs-lookup"><span data-stu-id="56bfa-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="56bfa-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.Primitives.RepeatButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="56bfa-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="56bfa-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="56bfa-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="56bfa-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="56bfa-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="56bfa-106">Parti di RepeatButton</span><span class="sxs-lookup"><span data-stu-id="56bfa-106">RepeatButton Parts</span></span>

<span data-ttu-id="56bfa-107">Il <xref:System.Windows.Controls.Primitives.RepeatButton> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="56bfa-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="56bfa-108">Stati di RepeatButton</span><span class="sxs-lookup"><span data-stu-id="56bfa-108">RepeatButton States</span></span>

<span data-ttu-id="56bfa-109">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.RepeatButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="56bfa-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="56bfa-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="56bfa-110">VisualState Name</span></span>|<span data-ttu-id="56bfa-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="56bfa-111">VisualStateGroup Name</span></span>|<span data-ttu-id="56bfa-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56bfa-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="56bfa-113">Normale</span><span class="sxs-lookup"><span data-stu-id="56bfa-113">Normal</span></span>|<span data-ttu-id="56bfa-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="56bfa-114">CommonStates</span></span>|<span data-ttu-id="56bfa-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="56bfa-115">The default state.</span></span>|
|<span data-ttu-id="56bfa-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="56bfa-116">MouseOver</span></span>|<span data-ttu-id="56bfa-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="56bfa-117">CommonStates</span></span>|<span data-ttu-id="56bfa-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="56bfa-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="56bfa-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="56bfa-119">Pressed</span></span>|<span data-ttu-id="56bfa-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="56bfa-120">CommonStates</span></span>|<span data-ttu-id="56bfa-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="56bfa-121">The control is pressed.</span></span>|
|<span data-ttu-id="56bfa-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="56bfa-122">Disabled</span></span>|<span data-ttu-id="56bfa-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="56bfa-123">CommonStates</span></span>|<span data-ttu-id="56bfa-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="56bfa-124">The control is disabled.</span></span>|
|<span data-ttu-id="56bfa-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="56bfa-125">Focused</span></span>|<span data-ttu-id="56bfa-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="56bfa-126">FocusStates</span></span>|<span data-ttu-id="56bfa-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="56bfa-127">The control has focus.</span></span>|
|<span data-ttu-id="56bfa-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="56bfa-128">Unfocused</span></span>|<span data-ttu-id="56bfa-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="56bfa-129">FocusStates</span></span>|<span data-ttu-id="56bfa-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="56bfa-130">The control does not have focus.</span></span>|
|<span data-ttu-id="56bfa-131">Valido</span><span class="sxs-lookup"><span data-stu-id="56bfa-131">Valid</span></span>|<span data-ttu-id="56bfa-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="56bfa-132">ValidationStates</span></span>|<span data-ttu-id="56bfa-133">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="56bfa-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="56bfa-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="56bfa-134">InvalidFocused</span></span>|<span data-ttu-id="56bfa-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="56bfa-135">ValidationStates</span></span>|<span data-ttu-id="56bfa-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="56bfa-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="56bfa-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="56bfa-137">InvalidUnfocused</span></span>|<span data-ttu-id="56bfa-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="56bfa-138">ValidationStates</span></span>|<span data-ttu-id="56bfa-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="56bfa-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="56bfa-140">Esempio di ControlTemplate RepeatButton</span><span class="sxs-lookup"><span data-stu-id="56bfa-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="56bfa-141">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.RepeatButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="56bfa-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="56bfa-142">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="56bfa-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="56bfa-143">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="56bfa-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="56bfa-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56bfa-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="56bfa-145">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="56bfa-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="56bfa-146">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="56bfa-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="56bfa-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="56bfa-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="56bfa-148">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="56bfa-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
