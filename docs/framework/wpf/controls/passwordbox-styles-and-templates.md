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
ms.openlocfilehash: 4ba90182468466773644c7375059f0cc01675b33
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283470"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="0414f-102">Stili e modelli di PasswordBox</span><span class="sxs-lookup"><span data-stu-id="0414f-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="0414f-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="0414f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="0414f-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="0414f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0414f-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="0414f-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="0414f-106">Parti PasswordBox</span><span class="sxs-lookup"><span data-stu-id="0414f-106">PasswordBox Parts</span></span>

<span data-ttu-id="0414f-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="0414f-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="0414f-108">Parte</span><span class="sxs-lookup"><span data-stu-id="0414f-108">Part</span></span>|<span data-ttu-id="0414f-109">Type</span><span class="sxs-lookup"><span data-stu-id="0414f-109">Type</span></span>|<span data-ttu-id="0414f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0414f-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="0414f-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="0414f-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="0414f-112">Elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="0414f-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="0414f-113">Il testo dell'<xref:System.Windows.Controls.PasswordBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="0414f-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="0414f-114">Stati di PasswordBox</span><span class="sxs-lookup"><span data-stu-id="0414f-114">PasswordBox States</span></span>

<span data-ttu-id="0414f-115">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="0414f-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="0414f-116">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="0414f-116">VisualState Name</span></span>|<span data-ttu-id="0414f-117">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="0414f-117">VisualStateGroup Name</span></span>|<span data-ttu-id="0414f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0414f-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="0414f-119">Normale</span><span class="sxs-lookup"><span data-stu-id="0414f-119">Normal</span></span>|<span data-ttu-id="0414f-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0414f-120">CommonStates</span></span>|<span data-ttu-id="0414f-121">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="0414f-121">The default state.</span></span>|
|<span data-ttu-id="0414f-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0414f-122">MouseOver</span></span>|<span data-ttu-id="0414f-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0414f-123">CommonStates</span></span>|<span data-ttu-id="0414f-124">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="0414f-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="0414f-125">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="0414f-125">Disabled</span></span>|<span data-ttu-id="0414f-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0414f-126">CommonStates</span></span>|<span data-ttu-id="0414f-127">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="0414f-127">The control is disabled.</span></span>|
|<span data-ttu-id="0414f-128">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="0414f-128">Focused</span></span>|<span data-ttu-id="0414f-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0414f-129">FocusStates</span></span>|<span data-ttu-id="0414f-130">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0414f-130">The control has focus.</span></span>|
|<span data-ttu-id="0414f-131">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="0414f-131">Unfocused</span></span>|<span data-ttu-id="0414f-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0414f-132">FocusStates</span></span>|<span data-ttu-id="0414f-133">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0414f-133">The control does not have focus.</span></span>|
|<span data-ttu-id="0414f-134">Valido</span><span class="sxs-lookup"><span data-stu-id="0414f-134">Valid</span></span>|<span data-ttu-id="0414f-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0414f-135">ValidationStates</span></span>|<span data-ttu-id="0414f-136">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="0414f-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="0414f-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0414f-137">InvalidFocused</span></span>|<span data-ttu-id="0414f-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0414f-138">ValidationStates</span></span>|<span data-ttu-id="0414f-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0414f-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="0414f-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0414f-140">InvalidUnfocused</span></span>|<span data-ttu-id="0414f-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0414f-141">ValidationStates</span></span>|<span data-ttu-id="0414f-142">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0414f-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="0414f-143">Esempio di ControlTemplate PasswordBox</span><span class="sxs-lookup"><span data-stu-id="0414f-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="0414f-144">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="0414f-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="0414f-145">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="0414f-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="0414f-146">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="0414f-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="0414f-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0414f-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0414f-148">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="0414f-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0414f-149">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="0414f-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0414f-150">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="0414f-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="0414f-151">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="0414f-151">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
