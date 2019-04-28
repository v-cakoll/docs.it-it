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
ms.openlocfilehash: ccc89e0e0c8977398ed162b246ff6cdede3b8351
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790871"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="46eeb-102">Stili e modelli di TextBox</span><span class="sxs-lookup"><span data-stu-id="46eeb-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="46eeb-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="46eeb-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="46eeb-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="46eeb-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="46eeb-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="46eeb-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="46eeb-106">Parti del controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="46eeb-106">TextBox Parts</span></span>  
 <span data-ttu-id="46eeb-107">La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="46eeb-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="46eeb-108">Parte</span><span class="sxs-lookup"><span data-stu-id="46eeb-108">Part</span></span>|<span data-ttu-id="46eeb-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="46eeb-109">Type</span></span>|<span data-ttu-id="46eeb-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46eeb-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="46eeb-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="46eeb-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="46eeb-112">Un elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="46eeb-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="46eeb-113">Il testo del <xref:System.Windows.Controls.TextBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="46eeb-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="46eeb-114">Gli stati nella casella di testo</span><span class="sxs-lookup"><span data-stu-id="46eeb-114">TextBox States</span></span>  
 <span data-ttu-id="46eeb-115">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="46eeb-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="46eeb-116">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="46eeb-116">VisualState Name</span></span>|<span data-ttu-id="46eeb-117">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="46eeb-117">VisualStateGroup Name</span></span>|<span data-ttu-id="46eeb-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46eeb-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="46eeb-119">Normale</span><span class="sxs-lookup"><span data-stu-id="46eeb-119">Normal</span></span>|<span data-ttu-id="46eeb-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="46eeb-120">CommonStates</span></span>|<span data-ttu-id="46eeb-121">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="46eeb-121">The default state.</span></span>|  
|<span data-ttu-id="46eeb-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="46eeb-122">MouseOver</span></span>|<span data-ttu-id="46eeb-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="46eeb-123">CommonStates</span></span>|<span data-ttu-id="46eeb-124">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="46eeb-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="46eeb-125">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="46eeb-125">Disabled</span></span>|<span data-ttu-id="46eeb-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="46eeb-126">CommonStates</span></span>|<span data-ttu-id="46eeb-127">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="46eeb-127">The control is disabled.</span></span>|  
|<span data-ttu-id="46eeb-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="46eeb-128">ReadOnly</span></span>|<span data-ttu-id="46eeb-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="46eeb-129">CommonStates</span></span>|<span data-ttu-id="46eeb-130">L'utente non è possibile modificare il testo nel <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="46eeb-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="46eeb-131">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="46eeb-131">Focused</span></span>|<span data-ttu-id="46eeb-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="46eeb-132">FocusStates</span></span>|<span data-ttu-id="46eeb-133">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="46eeb-133">The control has focus.</span></span>|  
|<span data-ttu-id="46eeb-134">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="46eeb-134">Unfocused</span></span>|<span data-ttu-id="46eeb-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="46eeb-135">FocusStates</span></span>|<span data-ttu-id="46eeb-136">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="46eeb-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="46eeb-137">Valido</span><span class="sxs-lookup"><span data-stu-id="46eeb-137">Valid</span></span>|<span data-ttu-id="46eeb-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46eeb-138">ValidationStates</span></span>|<span data-ttu-id="46eeb-139">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="46eeb-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="46eeb-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="46eeb-140">InvalidFocused</span></span>|<span data-ttu-id="46eeb-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46eeb-141">ValidationStates</span></span>|<span data-ttu-id="46eeb-142">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="46eeb-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="46eeb-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="46eeb-143">InvalidUnfocused</span></span>|<span data-ttu-id="46eeb-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46eeb-144">ValidationStates</span></span>|<span data-ttu-id="46eeb-145">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="46eeb-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="46eeb-146">Esempio di ControlTemplate nella casella di testo</span><span class="sxs-lookup"><span data-stu-id="46eeb-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="46eeb-147">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="46eeb-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="46eeb-148">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="46eeb-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="46eeb-149">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="46eeb-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46eeb-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46eeb-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="46eeb-151">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="46eeb-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="46eeb-152">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="46eeb-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="46eeb-153">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="46eeb-153">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="46eeb-154">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="46eeb-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
