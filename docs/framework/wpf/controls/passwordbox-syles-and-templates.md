---
title: Stili e modelli di PasswordBox
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 17a9292ef6aeba157780be5ec87d67725eb833a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="passwordbox-syles-and-templates"></a><span data-ttu-id="6b7cf-102">Stili e modelli di PasswordBox</span><span class="sxs-lookup"><span data-stu-id="6b7cf-102">PasswordBox Syles and Templates</span></span>
<span data-ttu-id="6b7cf-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="6b7cf-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6b7cf-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="6b7cf-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="passwordbox-parts"></a><span data-ttu-id="6b7cf-106">Parti del controllo PasswordBox</span><span class="sxs-lookup"><span data-stu-id="6b7cf-106">PasswordBox Parts</span></span>  
 <span data-ttu-id="6b7cf-107">La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="6b7cf-108">Parte</span><span class="sxs-lookup"><span data-stu-id="6b7cf-108">Part</span></span>|<span data-ttu-id="6b7cf-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="6b7cf-109">Type</span></span>|<span data-ttu-id="6b7cf-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b7cf-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6b7cf-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="6b7cf-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="6b7cf-112">Un elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="6b7cf-113">Il testo del <xref:System.Windows.Controls.PasswordBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|  
  
## <a name="passwordbox-states"></a><span data-ttu-id="6b7cf-114">Stati del controllo PasswordBox</span><span class="sxs-lookup"><span data-stu-id="6b7cf-114">PasswordBox States</span></span>  
 <span data-ttu-id="6b7cf-115">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="6b7cf-116">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="6b7cf-116">VisualState Name</span></span>|<span data-ttu-id="6b7cf-117">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="6b7cf-117">VisualStateGroup Name</span></span>|<span data-ttu-id="6b7cf-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b7cf-118">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6b7cf-119">Normale</span><span class="sxs-lookup"><span data-stu-id="6b7cf-119">Normal</span></span>|<span data-ttu-id="6b7cf-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6b7cf-120">CommonStates</span></span>|<span data-ttu-id="6b7cf-121">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-121">The default state.</span></span>|  
|<span data-ttu-id="6b7cf-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="6b7cf-122">MouseOver</span></span>|<span data-ttu-id="6b7cf-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6b7cf-123">CommonStates</span></span>|<span data-ttu-id="6b7cf-124">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="6b7cf-125">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="6b7cf-125">Disabled</span></span>|<span data-ttu-id="6b7cf-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6b7cf-126">CommonStates</span></span>|<span data-ttu-id="6b7cf-127">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-127">The control is disabled.</span></span>|  
|<span data-ttu-id="6b7cf-128">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="6b7cf-128">Focused</span></span>|<span data-ttu-id="6b7cf-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6b7cf-129">FocusStates</span></span>|<span data-ttu-id="6b7cf-130">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-130">The control has focus.</span></span>|  
|<span data-ttu-id="6b7cf-131">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="6b7cf-131">Unfocused</span></span>|<span data-ttu-id="6b7cf-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6b7cf-132">FocusStates</span></span>|<span data-ttu-id="6b7cf-133">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-133">The control does not have focus.</span></span>|  
|<span data-ttu-id="6b7cf-134">Valido</span><span class="sxs-lookup"><span data-stu-id="6b7cf-134">Valid</span></span>|<span data-ttu-id="6b7cf-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6b7cf-135">ValidationStates</span></span>|<span data-ttu-id="6b7cf-136">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="6b7cf-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6b7cf-137">InvalidFocused</span></span>|<span data-ttu-id="6b7cf-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6b7cf-138">ValidationStates</span></span>|<span data-ttu-id="6b7cf-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="6b7cf-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6b7cf-140">InvalidUnfocused</span></span>|<span data-ttu-id="6b7cf-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6b7cf-141">ValidationStates</span></span>|<span data-ttu-id="6b7cf-142">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="6b7cf-143">Esempio di ControlTemplate del controllo PasswordBox</span><span class="sxs-lookup"><span data-stu-id="6b7cf-143">PasswordBox ControlTemplate Example</span></span>  
 <span data-ttu-id="6b7cf-144">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#PasswordBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]  
  
 <span data-ttu-id="6b7cf-145">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="6b7cf-145">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="6b7cf-146">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="6b7cf-146">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7cf-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b7cf-147">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="6b7cf-148">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="6b7cf-148">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="6b7cf-149">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="6b7cf-149">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="6b7cf-150">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="6b7cf-150">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="6b7cf-151">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="6b7cf-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
