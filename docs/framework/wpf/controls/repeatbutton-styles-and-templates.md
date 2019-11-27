---
title: Stili e modelli di RepeatButton
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 8585e98536fd908daa11f21da395cab44924d612
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283420"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="93a6b-102">Stili e modelli di RepeatButton</span><span class="sxs-lookup"><span data-stu-id="93a6b-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="93a6b-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="93a6b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="93a6b-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="93a6b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="93a6b-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="93a6b-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="93a6b-106">Parti RepeatButton</span><span class="sxs-lookup"><span data-stu-id="93a6b-106">RepeatButton Parts</span></span>

<span data-ttu-id="93a6b-107">Il controllo <xref:System.Windows.Controls.Primitives.RepeatButton> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="93a6b-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="93a6b-108">Stati di RepeatButton</span><span class="sxs-lookup"><span data-stu-id="93a6b-108">RepeatButton States</span></span>

<span data-ttu-id="93a6b-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="93a6b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="93a6b-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="93a6b-110">VisualState Name</span></span>|<span data-ttu-id="93a6b-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="93a6b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="93a6b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93a6b-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="93a6b-113">Normale</span><span class="sxs-lookup"><span data-stu-id="93a6b-113">Normal</span></span>|<span data-ttu-id="93a6b-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="93a6b-114">CommonStates</span></span>|<span data-ttu-id="93a6b-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="93a6b-115">The default state.</span></span>|
|<span data-ttu-id="93a6b-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="93a6b-116">MouseOver</span></span>|<span data-ttu-id="93a6b-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="93a6b-117">CommonStates</span></span>|<span data-ttu-id="93a6b-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="93a6b-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="93a6b-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="93a6b-119">Pressed</span></span>|<span data-ttu-id="93a6b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="93a6b-120">CommonStates</span></span>|<span data-ttu-id="93a6b-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="93a6b-121">The control is pressed.</span></span>|
|<span data-ttu-id="93a6b-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="93a6b-122">Disabled</span></span>|<span data-ttu-id="93a6b-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="93a6b-123">CommonStates</span></span>|<span data-ttu-id="93a6b-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="93a6b-124">The control is disabled.</span></span>|
|<span data-ttu-id="93a6b-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="93a6b-125">Focused</span></span>|<span data-ttu-id="93a6b-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="93a6b-126">FocusStates</span></span>|<span data-ttu-id="93a6b-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="93a6b-127">The control has focus.</span></span>|
|<span data-ttu-id="93a6b-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="93a6b-128">Unfocused</span></span>|<span data-ttu-id="93a6b-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="93a6b-129">FocusStates</span></span>|<span data-ttu-id="93a6b-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="93a6b-130">The control does not have focus.</span></span>|
|<span data-ttu-id="93a6b-131">Valido</span><span class="sxs-lookup"><span data-stu-id="93a6b-131">Valid</span></span>|<span data-ttu-id="93a6b-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="93a6b-132">ValidationStates</span></span>|<span data-ttu-id="93a6b-133">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="93a6b-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="93a6b-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="93a6b-134">InvalidFocused</span></span>|<span data-ttu-id="93a6b-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="93a6b-135">ValidationStates</span></span>|<span data-ttu-id="93a6b-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="93a6b-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="93a6b-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="93a6b-137">InvalidUnfocused</span></span>|<span data-ttu-id="93a6b-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="93a6b-138">ValidationStates</span></span>|<span data-ttu-id="93a6b-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="93a6b-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="93a6b-140">Esempio di ControlTemplate RepeatButton</span><span class="sxs-lookup"><span data-stu-id="93a6b-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="93a6b-141">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="93a6b-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="93a6b-142">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="93a6b-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="93a6b-143">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="93a6b-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="93a6b-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93a6b-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="93a6b-145">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="93a6b-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="93a6b-146">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="93a6b-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="93a6b-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="93a6b-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="93a6b-148">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="93a6b-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
