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
ms.openlocfilehash: 464e2ff88b6e311470f6afe107d770922d9a395d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689234"
---
# <a name="passwordbox-syles-and-templates"></a><span data-ttu-id="93cff-102">Stili e modelli di PasswordBox</span><span class="sxs-lookup"><span data-stu-id="93cff-102">PasswordBox Syles and Templates</span></span>
<span data-ttu-id="93cff-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="93cff-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="93cff-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="93cff-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="93cff-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="93cff-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="passwordbox-parts"></a><span data-ttu-id="93cff-106">Parti del controllo PasswordBox</span><span class="sxs-lookup"><span data-stu-id="93cff-106">PasswordBox Parts</span></span>  
 <span data-ttu-id="93cff-107">La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="93cff-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="93cff-108">Parte</span><span class="sxs-lookup"><span data-stu-id="93cff-108">Part</span></span>|<span data-ttu-id="93cff-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="93cff-109">Type</span></span>|<span data-ttu-id="93cff-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93cff-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="93cff-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="93cff-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="93cff-112">Un elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="93cff-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="93cff-113">Il testo del <xref:System.Windows.Controls.PasswordBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="93cff-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|  
  
## <a name="passwordbox-states"></a><span data-ttu-id="93cff-114">Stati del controllo PasswordBox</span><span class="sxs-lookup"><span data-stu-id="93cff-114">PasswordBox States</span></span>  
 <span data-ttu-id="93cff-115">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="93cff-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="93cff-116">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="93cff-116">VisualState Name</span></span>|<span data-ttu-id="93cff-117">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="93cff-117">VisualStateGroup Name</span></span>|<span data-ttu-id="93cff-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93cff-118">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="93cff-119">Normale</span><span class="sxs-lookup"><span data-stu-id="93cff-119">Normal</span></span>|<span data-ttu-id="93cff-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="93cff-120">CommonStates</span></span>|<span data-ttu-id="93cff-121">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="93cff-121">The default state.</span></span>|  
|<span data-ttu-id="93cff-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="93cff-122">MouseOver</span></span>|<span data-ttu-id="93cff-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="93cff-123">CommonStates</span></span>|<span data-ttu-id="93cff-124">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="93cff-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="93cff-125">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="93cff-125">Disabled</span></span>|<span data-ttu-id="93cff-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="93cff-126">CommonStates</span></span>|<span data-ttu-id="93cff-127">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="93cff-127">The control is disabled.</span></span>|  
|<span data-ttu-id="93cff-128">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="93cff-128">Focused</span></span>|<span data-ttu-id="93cff-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="93cff-129">FocusStates</span></span>|<span data-ttu-id="93cff-130">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="93cff-130">The control has focus.</span></span>|  
|<span data-ttu-id="93cff-131">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="93cff-131">Unfocused</span></span>|<span data-ttu-id="93cff-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="93cff-132">FocusStates</span></span>|<span data-ttu-id="93cff-133">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="93cff-133">The control does not have focus.</span></span>|  
|<span data-ttu-id="93cff-134">Valido</span><span class="sxs-lookup"><span data-stu-id="93cff-134">Valid</span></span>|<span data-ttu-id="93cff-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="93cff-135">ValidationStates</span></span>|<span data-ttu-id="93cff-136">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="93cff-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="93cff-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="93cff-137">InvalidFocused</span></span>|<span data-ttu-id="93cff-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="93cff-138">ValidationStates</span></span>|<span data-ttu-id="93cff-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="93cff-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="93cff-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="93cff-140">InvalidUnfocused</span></span>|<span data-ttu-id="93cff-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="93cff-141">ValidationStates</span></span>|<span data-ttu-id="93cff-142">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="93cff-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="93cff-143">Esempio di ControlTemplate PasswordBox</span><span class="sxs-lookup"><span data-stu-id="93cff-143">PasswordBox ControlTemplate Example</span></span>  
 <span data-ttu-id="93cff-144">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="93cff-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#PasswordBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]  
  
 <span data-ttu-id="93cff-145">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="93cff-145">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="93cff-146">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="93cff-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93cff-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93cff-147">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="93cff-148">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="93cff-148">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="93cff-149">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="93cff-149">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="93cff-150">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="93cff-150">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="93cff-151">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="93cff-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
