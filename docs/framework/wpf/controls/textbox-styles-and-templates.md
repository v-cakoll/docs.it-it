---
title: Stili e modelli di TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 41e390c261836909240cc146a48729d48c4a410e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283693"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="21f21-102">Stili e modelli di TextBox</span><span class="sxs-lookup"><span data-stu-id="21f21-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="21f21-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="21f21-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="21f21-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="21f21-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="21f21-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="21f21-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="21f21-106">Parti casella di testo</span><span class="sxs-lookup"><span data-stu-id="21f21-106">TextBox Parts</span></span>  
 <span data-ttu-id="21f21-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="21f21-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="21f21-108">Parte</span><span class="sxs-lookup"><span data-stu-id="21f21-108">Part</span></span>|<span data-ttu-id="21f21-109">Type</span><span class="sxs-lookup"><span data-stu-id="21f21-109">Type</span></span>|<span data-ttu-id="21f21-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21f21-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="21f21-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="21f21-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="21f21-112">Elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="21f21-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="21f21-113">Il testo dell'<xref:System.Windows.Controls.TextBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="21f21-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="21f21-114">Stati TextBox</span><span class="sxs-lookup"><span data-stu-id="21f21-114">TextBox States</span></span>  
 <span data-ttu-id="21f21-115">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="21f21-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="21f21-116">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="21f21-116">VisualState Name</span></span>|<span data-ttu-id="21f21-117">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="21f21-117">VisualStateGroup Name</span></span>|<span data-ttu-id="21f21-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21f21-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="21f21-119">Normale</span><span class="sxs-lookup"><span data-stu-id="21f21-119">Normal</span></span>|<span data-ttu-id="21f21-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="21f21-120">CommonStates</span></span>|<span data-ttu-id="21f21-121">Stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="21f21-121">The default state.</span></span>|  
|<span data-ttu-id="21f21-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="21f21-122">MouseOver</span></span>|<span data-ttu-id="21f21-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="21f21-123">CommonStates</span></span>|<span data-ttu-id="21f21-124">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="21f21-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="21f21-125">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="21f21-125">Disabled</span></span>|<span data-ttu-id="21f21-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="21f21-126">CommonStates</span></span>|<span data-ttu-id="21f21-127">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="21f21-127">The control is disabled.</span></span>|  
|<span data-ttu-id="21f21-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="21f21-128">ReadOnly</span></span>|<span data-ttu-id="21f21-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="21f21-129">CommonStates</span></span>|<span data-ttu-id="21f21-130">L'utente non può modificare il testo nel <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="21f21-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="21f21-131">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="21f21-131">Focused</span></span>|<span data-ttu-id="21f21-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="21f21-132">FocusStates</span></span>|<span data-ttu-id="21f21-133">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="21f21-133">The control has focus.</span></span>|  
|<span data-ttu-id="21f21-134">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="21f21-134">Unfocused</span></span>|<span data-ttu-id="21f21-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="21f21-135">FocusStates</span></span>|<span data-ttu-id="21f21-136">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="21f21-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="21f21-137">Valido</span><span class="sxs-lookup"><span data-stu-id="21f21-137">Valid</span></span>|<span data-ttu-id="21f21-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="21f21-138">ValidationStates</span></span>|<span data-ttu-id="21f21-139">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="21f21-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="21f21-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="21f21-140">InvalidFocused</span></span>|<span data-ttu-id="21f21-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="21f21-141">ValidationStates</span></span>|<span data-ttu-id="21f21-142">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="21f21-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="21f21-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="21f21-143">InvalidUnfocused</span></span>|<span data-ttu-id="21f21-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="21f21-144">ValidationStates</span></span>|<span data-ttu-id="21f21-145">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="21f21-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="21f21-146">Esempio di ControlTemplate TextBox</span><span class="sxs-lookup"><span data-stu-id="21f21-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="21f21-147">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="21f21-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="21f21-148">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="21f21-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="21f21-149">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="21f21-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f21-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21f21-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="21f21-151">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="21f21-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="21f21-152">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="21f21-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="21f21-153">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="21f21-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="21f21-154">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="21f21-154">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
