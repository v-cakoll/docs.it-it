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
ms.openlocfilehash: c2114a02016db96d898a394b6892b6d3042d81ff
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458242"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="a1b0a-102">Stili e modelli di Thumb</span><span class="sxs-lookup"><span data-stu-id="a1b0a-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="a1b0a-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="a1b0a-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a1b0a-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a1b0a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="a1b0a-106">Parti Thumb</span><span class="sxs-lookup"><span data-stu-id="a1b0a-106">Thumb Parts</span></span>

<span data-ttu-id="a1b0a-107">Il controllo <xref:System.Windows.Controls.Primitives.Thumb> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="a1b0a-108">Stati Thumb</span><span class="sxs-lookup"><span data-stu-id="a1b0a-108">Thumb States</span></span>

<span data-ttu-id="a1b0a-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="a1b0a-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="a1b0a-110">VisualState Name</span></span>|<span data-ttu-id="a1b0a-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a1b0a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a1b0a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1b0a-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="a1b0a-113">Normale</span><span class="sxs-lookup"><span data-stu-id="a1b0a-113">Normal</span></span>|<span data-ttu-id="a1b0a-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a1b0a-114">CommonStates</span></span>|<span data-ttu-id="a1b0a-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-115">The default state.</span></span>|
|<span data-ttu-id="a1b0a-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a1b0a-116">MouseOver</span></span>|<span data-ttu-id="a1b0a-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a1b0a-117">CommonStates</span></span>|<span data-ttu-id="a1b0a-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="a1b0a-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="a1b0a-119">Pressed</span></span>|<span data-ttu-id="a1b0a-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a1b0a-120">CommonStates</span></span>|<span data-ttu-id="a1b0a-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-121">The control is pressed.</span></span>|
|<span data-ttu-id="a1b0a-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="a1b0a-122">Disabled</span></span>|<span data-ttu-id="a1b0a-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a1b0a-123">CommonStates</span></span>|<span data-ttu-id="a1b0a-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-124">The control is disabled.</span></span>|
|<span data-ttu-id="a1b0a-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="a1b0a-125">Focused</span></span>|<span data-ttu-id="a1b0a-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a1b0a-126">FocusStates</span></span>|<span data-ttu-id="a1b0a-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-127">The control has focus.</span></span>|
|<span data-ttu-id="a1b0a-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="a1b0a-128">Unfocused</span></span>|<span data-ttu-id="a1b0a-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a1b0a-129">FocusStates</span></span>|<span data-ttu-id="a1b0a-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-130">The control does not have focus.</span></span>|
|<span data-ttu-id="a1b0a-131">Valido</span><span class="sxs-lookup"><span data-stu-id="a1b0a-131">Valid</span></span>|<span data-ttu-id="a1b0a-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a1b0a-132">ValidationStates</span></span>|<span data-ttu-id="a1b0a-133">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="a1b0a-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a1b0a-134">InvalidFocused</span></span>|<span data-ttu-id="a1b0a-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a1b0a-135">ValidationStates</span></span>|<span data-ttu-id="a1b0a-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="a1b0a-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a1b0a-137">InvalidUnfocused</span></span>|<span data-ttu-id="a1b0a-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a1b0a-138">ValidationStates</span></span>|<span data-ttu-id="a1b0a-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="a1b0a-140">Esempio di ControlTemplate Thumb</span><span class="sxs-lookup"><span data-stu-id="a1b0a-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="a1b0a-141">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="a1b0a-142">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="a1b0a-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="a1b0a-143">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a1b0a-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="a1b0a-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1b0a-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a1b0a-145">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="a1b0a-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a1b0a-146">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="a1b0a-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a1b0a-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="a1b0a-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a1b0a-148">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a1b0a-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
