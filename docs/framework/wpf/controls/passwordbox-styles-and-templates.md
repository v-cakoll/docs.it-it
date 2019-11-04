---
title: Stili e modelli di PasswordBox
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 227ccbda8d570868258508935a5d95f0f40663ab
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458831"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="ee35d-102">Stili e modelli di PasswordBox</span><span class="sxs-lookup"><span data-stu-id="ee35d-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="ee35d-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="ee35d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="ee35d-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="ee35d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ee35d-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ee35d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="ee35d-106">Parti PasswordBox</span><span class="sxs-lookup"><span data-stu-id="ee35d-106">PasswordBox Parts</span></span>

<span data-ttu-id="ee35d-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="ee35d-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="ee35d-108">Parte</span><span class="sxs-lookup"><span data-stu-id="ee35d-108">Part</span></span>|<span data-ttu-id="ee35d-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="ee35d-109">Type</span></span>|<span data-ttu-id="ee35d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee35d-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="ee35d-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="ee35d-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="ee35d-112">Elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="ee35d-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="ee35d-113">Il testo dell'<xref:System.Windows.Controls.PasswordBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="ee35d-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="ee35d-114">Stati di PasswordBox</span><span class="sxs-lookup"><span data-stu-id="ee35d-114">PasswordBox States</span></span>

<span data-ttu-id="ee35d-115">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="ee35d-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="ee35d-116">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="ee35d-116">VisualState Name</span></span>|<span data-ttu-id="ee35d-117">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="ee35d-117">VisualStateGroup Name</span></span>|<span data-ttu-id="ee35d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee35d-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="ee35d-119">Normale</span><span class="sxs-lookup"><span data-stu-id="ee35d-119">Normal</span></span>|<span data-ttu-id="ee35d-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ee35d-120">CommonStates</span></span>|<span data-ttu-id="ee35d-121">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="ee35d-121">The default state.</span></span>|
|<span data-ttu-id="ee35d-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ee35d-122">MouseOver</span></span>|<span data-ttu-id="ee35d-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ee35d-123">CommonStates</span></span>|<span data-ttu-id="ee35d-124">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="ee35d-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="ee35d-125">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="ee35d-125">Disabled</span></span>|<span data-ttu-id="ee35d-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ee35d-126">CommonStates</span></span>|<span data-ttu-id="ee35d-127">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="ee35d-127">The control is disabled.</span></span>|
|<span data-ttu-id="ee35d-128">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="ee35d-128">Focused</span></span>|<span data-ttu-id="ee35d-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ee35d-129">FocusStates</span></span>|<span data-ttu-id="ee35d-130">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="ee35d-130">The control has focus.</span></span>|
|<span data-ttu-id="ee35d-131">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="ee35d-131">Unfocused</span></span>|<span data-ttu-id="ee35d-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ee35d-132">FocusStates</span></span>|<span data-ttu-id="ee35d-133">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="ee35d-133">The control does not have focus.</span></span>|
|<span data-ttu-id="ee35d-134">Valido</span><span class="sxs-lookup"><span data-stu-id="ee35d-134">Valid</span></span>|<span data-ttu-id="ee35d-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ee35d-135">ValidationStates</span></span>|<span data-ttu-id="ee35d-136">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="ee35d-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="ee35d-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ee35d-137">InvalidFocused</span></span>|<span data-ttu-id="ee35d-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ee35d-138">ValidationStates</span></span>|<span data-ttu-id="ee35d-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="ee35d-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="ee35d-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ee35d-140">InvalidUnfocused</span></span>|<span data-ttu-id="ee35d-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ee35d-141">ValidationStates</span></span>|<span data-ttu-id="ee35d-142">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="ee35d-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="ee35d-143">Esempio di ControlTemplate PasswordBox</span><span class="sxs-lookup"><span data-stu-id="ee35d-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="ee35d-144">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="ee35d-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="ee35d-145">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="ee35d-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="ee35d-146">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="ee35d-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="ee35d-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee35d-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ee35d-148">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="ee35d-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ee35d-149">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="ee35d-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ee35d-150">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="ee35d-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ee35d-151">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ee35d-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
