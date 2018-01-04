---
title: Stili e modelli di TextBox
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d4fdb652876f2df049b71c18b0b79b7b435da8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="53b70-102">Stili e modelli di TextBox</span><span class="sxs-lookup"><span data-stu-id="53b70-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="53b70-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="53b70-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="53b70-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="53b70-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="53b70-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="53b70-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="53b70-106">Parti del controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="53b70-106">TextBox Parts</span></span>  
 <span data-ttu-id="53b70-107">La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="53b70-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="53b70-108">Parte</span><span class="sxs-lookup"><span data-stu-id="53b70-108">Part</span></span>|<span data-ttu-id="53b70-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="53b70-109">Type</span></span>|<span data-ttu-id="53b70-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53b70-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="53b70-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="53b70-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="53b70-112">Un elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="53b70-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="53b70-113">Il testo del <xref:System.Windows.Controls.TextBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="53b70-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="53b70-114">Stati di casella di testo</span><span class="sxs-lookup"><span data-stu-id="53b70-114">TextBox States</span></span>  
 <span data-ttu-id="53b70-115">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="53b70-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="53b70-116">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="53b70-116">VisualState Name</span></span>|<span data-ttu-id="53b70-117">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="53b70-117">VisualStateGroup Name</span></span>|<span data-ttu-id="53b70-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53b70-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="53b70-119">Normale</span><span class="sxs-lookup"><span data-stu-id="53b70-119">Normal</span></span>|<span data-ttu-id="53b70-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="53b70-120">CommonStates</span></span>|<span data-ttu-id="53b70-121">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="53b70-121">The default state.</span></span>|  
|<span data-ttu-id="53b70-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="53b70-122">MouseOver</span></span>|<span data-ttu-id="53b70-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="53b70-123">CommonStates</span></span>|<span data-ttu-id="53b70-124">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="53b70-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="53b70-125">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="53b70-125">Disabled</span></span>|<span data-ttu-id="53b70-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="53b70-126">CommonStates</span></span>|<span data-ttu-id="53b70-127">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="53b70-127">The control is disabled.</span></span>|  
|<span data-ttu-id="53b70-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="53b70-128">ReadOnly</span></span>|<span data-ttu-id="53b70-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="53b70-129">CommonStates</span></span>|<span data-ttu-id="53b70-130">L'utente non è possibile modificare il testo di <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="53b70-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="53b70-131">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="53b70-131">Focused</span></span>|<span data-ttu-id="53b70-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="53b70-132">FocusStates</span></span>|<span data-ttu-id="53b70-133">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="53b70-133">The control has focus.</span></span>|  
|<span data-ttu-id="53b70-134">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="53b70-134">Unfocused</span></span>|<span data-ttu-id="53b70-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="53b70-135">FocusStates</span></span>|<span data-ttu-id="53b70-136">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="53b70-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="53b70-137">Valido</span><span class="sxs-lookup"><span data-stu-id="53b70-137">Valid</span></span>|<span data-ttu-id="53b70-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="53b70-138">ValidationStates</span></span>|<span data-ttu-id="53b70-139">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="53b70-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="53b70-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="53b70-140">InvalidFocused</span></span>|<span data-ttu-id="53b70-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="53b70-141">ValidationStates</span></span>|<span data-ttu-id="53b70-142">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="53b70-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="53b70-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="53b70-143">InvalidUnfocused</span></span>|<span data-ttu-id="53b70-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="53b70-144">ValidationStates</span></span>|<span data-ttu-id="53b70-145">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="53b70-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="53b70-146">Esempio di ControlTemplate del controllo casella di testo</span><span class="sxs-lookup"><span data-stu-id="53b70-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="53b70-147">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="53b70-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="53b70-148">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="53b70-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="53b70-149">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="53b70-149">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b70-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53b70-150">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="53b70-151">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="53b70-151">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="53b70-152">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="53b70-152">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="53b70-153">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="53b70-153">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="53b70-154">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="53b70-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
