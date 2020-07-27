---
title: Stili e modelli di TextBox
description: Informazioni sugli stili e i modelli per il controllo TextBox Windows Presentation Foundation. Modificare il ControlTemplate per dare al controllo un aspetto univoco.
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 0e15fd40f5590ee46da49cc6c0d5fb30e051f7e4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164725"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="ae56d-104">Stili e modelli di TextBox</span><span class="sxs-lookup"><span data-stu-id="ae56d-104">TextBox Styles and Templates</span></span>
<span data-ttu-id="ae56d-105">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="ae56d-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="ae56d-106">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="ae56d-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ae56d-107">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="ae56d-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="ae56d-108">Parti casella di testo</span><span class="sxs-lookup"><span data-stu-id="ae56d-108">TextBox Parts</span></span>  
 <span data-ttu-id="ae56d-109">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="ae56d-109">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="ae56d-110">Parte</span><span class="sxs-lookup"><span data-stu-id="ae56d-110">Part</span></span>|<span data-ttu-id="ae56d-111">Type</span><span class="sxs-lookup"><span data-stu-id="ae56d-111">Type</span></span>|<span data-ttu-id="ae56d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae56d-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ae56d-113">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="ae56d-113">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="ae56d-114">Elemento visivo che può contenere un oggetto <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="ae56d-114">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="ae56d-115">Il testo di <xref:System.Windows.Controls.TextBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="ae56d-115">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="ae56d-116">Stati TextBox</span><span class="sxs-lookup"><span data-stu-id="ae56d-116">TextBox States</span></span>  
 <span data-ttu-id="ae56d-117">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="ae56d-117">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="ae56d-118">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="ae56d-118">VisualState Name</span></span>|<span data-ttu-id="ae56d-119">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="ae56d-119">VisualStateGroup Name</span></span>|<span data-ttu-id="ae56d-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae56d-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="ae56d-121">Normale</span><span class="sxs-lookup"><span data-stu-id="ae56d-121">Normal</span></span>|<span data-ttu-id="ae56d-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ae56d-122">CommonStates</span></span>|<span data-ttu-id="ae56d-123">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="ae56d-123">The default state.</span></span>|  
|<span data-ttu-id="ae56d-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ae56d-124">MouseOver</span></span>|<span data-ttu-id="ae56d-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ae56d-125">CommonStates</span></span>|<span data-ttu-id="ae56d-126">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="ae56d-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ae56d-127">Disabled</span><span class="sxs-lookup"><span data-stu-id="ae56d-127">Disabled</span></span>|<span data-ttu-id="ae56d-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ae56d-128">CommonStates</span></span>|<span data-ttu-id="ae56d-129">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="ae56d-129">The control is disabled.</span></span>|  
|<span data-ttu-id="ae56d-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="ae56d-130">ReadOnly</span></span>|<span data-ttu-id="ae56d-131">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ae56d-131">CommonStates</span></span>|<span data-ttu-id="ae56d-132">L'utente non può modificare il testo in <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="ae56d-132">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="ae56d-133">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="ae56d-133">Focused</span></span>|<span data-ttu-id="ae56d-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ae56d-134">FocusStates</span></span>|<span data-ttu-id="ae56d-135">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="ae56d-135">The control has focus.</span></span>|  
|<span data-ttu-id="ae56d-136">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="ae56d-136">Unfocused</span></span>|<span data-ttu-id="ae56d-137">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ae56d-137">FocusStates</span></span>|<span data-ttu-id="ae56d-138">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="ae56d-138">The control does not have focus.</span></span>|  
|<span data-ttu-id="ae56d-139">Valido</span><span class="sxs-lookup"><span data-stu-id="ae56d-139">Valid</span></span>|<span data-ttu-id="ae56d-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ae56d-140">ValidationStates</span></span>|<span data-ttu-id="ae56d-141">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="ae56d-141">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ae56d-142">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ae56d-142">InvalidFocused</span></span>|<span data-ttu-id="ae56d-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ae56d-143">ValidationStates</span></span>|<span data-ttu-id="ae56d-144">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="ae56d-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ae56d-145">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ae56d-145">InvalidUnfocused</span></span>|<span data-ttu-id="ae56d-146">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ae56d-146">ValidationStates</span></span>|<span data-ttu-id="ae56d-147">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="ae56d-147">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="ae56d-148">Esempio di ControlTemplate TextBox</span><span class="sxs-lookup"><span data-stu-id="ae56d-148">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="ae56d-149">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="ae56d-149">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="ae56d-150">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="ae56d-150">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ae56d-151">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="ae56d-151">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae56d-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae56d-152">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ae56d-153">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="ae56d-153">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ae56d-154">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="ae56d-154">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ae56d-155">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="ae56d-155">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ae56d-156">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="ae56d-156">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
