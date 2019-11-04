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
ms.openlocfilehash: 9c6a8ad0a954d244fb693e25965ab52dda114068
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459854"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="bf2f6-102">Stili e modelli di RepeatButton</span><span class="sxs-lookup"><span data-stu-id="bf2f6-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="bf2f6-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="bf2f6-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bf2f6-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="bf2f6-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="bf2f6-106">Parti RepeatButton</span><span class="sxs-lookup"><span data-stu-id="bf2f6-106">RepeatButton Parts</span></span>

<span data-ttu-id="bf2f6-107">Il controllo <xref:System.Windows.Controls.Primitives.RepeatButton> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="bf2f6-108">Stati di RepeatButton</span><span class="sxs-lookup"><span data-stu-id="bf2f6-108">RepeatButton States</span></span>

<span data-ttu-id="bf2f6-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="bf2f6-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="bf2f6-110">VisualState Name</span></span>|<span data-ttu-id="bf2f6-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="bf2f6-111">VisualStateGroup Name</span></span>|<span data-ttu-id="bf2f6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf2f6-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="bf2f6-113">Normale</span><span class="sxs-lookup"><span data-stu-id="bf2f6-113">Normal</span></span>|<span data-ttu-id="bf2f6-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bf2f6-114">CommonStates</span></span>|<span data-ttu-id="bf2f6-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-115">The default state.</span></span>|
|<span data-ttu-id="bf2f6-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="bf2f6-116">MouseOver</span></span>|<span data-ttu-id="bf2f6-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bf2f6-117">CommonStates</span></span>|<span data-ttu-id="bf2f6-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="bf2f6-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="bf2f6-119">Pressed</span></span>|<span data-ttu-id="bf2f6-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bf2f6-120">CommonStates</span></span>|<span data-ttu-id="bf2f6-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-121">The control is pressed.</span></span>|
|<span data-ttu-id="bf2f6-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="bf2f6-122">Disabled</span></span>|<span data-ttu-id="bf2f6-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bf2f6-123">CommonStates</span></span>|<span data-ttu-id="bf2f6-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-124">The control is disabled.</span></span>|
|<span data-ttu-id="bf2f6-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="bf2f6-125">Focused</span></span>|<span data-ttu-id="bf2f6-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="bf2f6-126">FocusStates</span></span>|<span data-ttu-id="bf2f6-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-127">The control has focus.</span></span>|
|<span data-ttu-id="bf2f6-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="bf2f6-128">Unfocused</span></span>|<span data-ttu-id="bf2f6-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="bf2f6-129">FocusStates</span></span>|<span data-ttu-id="bf2f6-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-130">The control does not have focus.</span></span>|
|<span data-ttu-id="bf2f6-131">Valido</span><span class="sxs-lookup"><span data-stu-id="bf2f6-131">Valid</span></span>|<span data-ttu-id="bf2f6-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bf2f6-132">ValidationStates</span></span>|<span data-ttu-id="bf2f6-133">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="bf2f6-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bf2f6-134">InvalidFocused</span></span>|<span data-ttu-id="bf2f6-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bf2f6-135">ValidationStates</span></span>|<span data-ttu-id="bf2f6-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="bf2f6-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bf2f6-137">InvalidUnfocused</span></span>|<span data-ttu-id="bf2f6-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bf2f6-138">ValidationStates</span></span>|<span data-ttu-id="bf2f6-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="bf2f6-140">Esempio di ControlTemplate RepeatButton</span><span class="sxs-lookup"><span data-stu-id="bf2f6-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="bf2f6-141">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="bf2f6-142">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="bf2f6-143">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="bf2f6-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="bf2f6-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf2f6-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="bf2f6-145">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="bf2f6-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="bf2f6-146">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="bf2f6-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="bf2f6-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="bf2f6-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="bf2f6-148">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="bf2f6-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
