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
ms.openlocfilehash: 7f5cfd1c0715c7f9610f85201cd40a3973a2be64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="826da-102">Stili e modelli di TextBox</span><span class="sxs-lookup"><span data-stu-id="826da-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="826da-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="826da-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="826da-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="826da-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="826da-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="826da-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="826da-106">Parti del controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="826da-106">TextBox Parts</span></span>  
 <span data-ttu-id="826da-107">La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="826da-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="826da-108">Parte</span><span class="sxs-lookup"><span data-stu-id="826da-108">Part</span></span>|<span data-ttu-id="826da-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="826da-109">Type</span></span>|<span data-ttu-id="826da-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="826da-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="826da-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="826da-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="826da-112">Un elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="826da-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="826da-113">Il testo del <xref:System.Windows.Controls.TextBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="826da-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="826da-114">Stati di casella di testo</span><span class="sxs-lookup"><span data-stu-id="826da-114">TextBox States</span></span>  
 <span data-ttu-id="826da-115">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="826da-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="826da-116">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="826da-116">VisualState Name</span></span>|<span data-ttu-id="826da-117">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="826da-117">VisualStateGroup Name</span></span>|<span data-ttu-id="826da-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="826da-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="826da-119">Normale</span><span class="sxs-lookup"><span data-stu-id="826da-119">Normal</span></span>|<span data-ttu-id="826da-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="826da-120">CommonStates</span></span>|<span data-ttu-id="826da-121">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="826da-121">The default state.</span></span>|  
|<span data-ttu-id="826da-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="826da-122">MouseOver</span></span>|<span data-ttu-id="826da-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="826da-123">CommonStates</span></span>|<span data-ttu-id="826da-124">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="826da-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="826da-125">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="826da-125">Disabled</span></span>|<span data-ttu-id="826da-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="826da-126">CommonStates</span></span>|<span data-ttu-id="826da-127">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="826da-127">The control is disabled.</span></span>|  
|<span data-ttu-id="826da-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="826da-128">ReadOnly</span></span>|<span data-ttu-id="826da-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="826da-129">CommonStates</span></span>|<span data-ttu-id="826da-130">L'utente non è possibile modificare il testo di <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="826da-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="826da-131">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="826da-131">Focused</span></span>|<span data-ttu-id="826da-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="826da-132">FocusStates</span></span>|<span data-ttu-id="826da-133">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="826da-133">The control has focus.</span></span>|  
|<span data-ttu-id="826da-134">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="826da-134">Unfocused</span></span>|<span data-ttu-id="826da-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="826da-135">FocusStates</span></span>|<span data-ttu-id="826da-136">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="826da-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="826da-137">Valido</span><span class="sxs-lookup"><span data-stu-id="826da-137">Valid</span></span>|<span data-ttu-id="826da-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="826da-138">ValidationStates</span></span>|<span data-ttu-id="826da-139">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="826da-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="826da-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="826da-140">InvalidFocused</span></span>|<span data-ttu-id="826da-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="826da-141">ValidationStates</span></span>|<span data-ttu-id="826da-142">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="826da-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="826da-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="826da-143">InvalidUnfocused</span></span>|<span data-ttu-id="826da-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="826da-144">ValidationStates</span></span>|<span data-ttu-id="826da-145">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="826da-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="826da-146">Esempio di ControlTemplate del controllo casella di testo</span><span class="sxs-lookup"><span data-stu-id="826da-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="826da-147">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="826da-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="826da-148">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="826da-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="826da-149">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="826da-149">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="826da-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="826da-150">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="826da-151">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="826da-151">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="826da-152">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="826da-152">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="826da-153">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="826da-153">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="826da-154">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="826da-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
