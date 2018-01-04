---
title: Stili e modelli di RadioButton
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05b5f2124e6d8817b03171af5308c116e9339ecb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="radiobutton-styles-and-templates"></a><span data-ttu-id="a38bf-102">Stili e modelli di RadioButton</span><span class="sxs-lookup"><span data-stu-id="a38bf-102">RadioButton Styles and Templates</span></span>
<span data-ttu-id="a38bf-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.RadioButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="a38bf-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.RadioButton> control.</span></span> <span data-ttu-id="a38bf-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="a38bf-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a38bf-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a38bf-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="radiobutton-parts"></a><span data-ttu-id="a38bf-106">Parti del controllo RadioButton</span><span class="sxs-lookup"><span data-stu-id="a38bf-106">RadioButton Parts</span></span>  
 <span data-ttu-id="a38bf-107">Il <xref:System.Windows.Controls.RadioButton> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="a38bf-107">The <xref:System.Windows.Controls.RadioButton> control does not have any named parts.</span></span>  
  
## <a name="radiobutton-states"></a><span data-ttu-id="a38bf-108">Stati di RadioButton</span><span class="sxs-lookup"><span data-stu-id="a38bf-108">RadioButton States</span></span>  
 <span data-ttu-id="a38bf-109">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.RadioButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="a38bf-109">The following table lists the visual states for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
|<span data-ttu-id="a38bf-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="a38bf-110">VisualState Name</span></span>|<span data-ttu-id="a38bf-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a38bf-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a38bf-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a38bf-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="a38bf-113">Normale</span><span class="sxs-lookup"><span data-stu-id="a38bf-113">Normal</span></span>|<span data-ttu-id="a38bf-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-114">CommonStates</span></span>|<span data-ttu-id="a38bf-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="a38bf-115">The default state.</span></span>|  
|<span data-ttu-id="a38bf-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a38bf-116">MouseOver</span></span>|<span data-ttu-id="a38bf-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-117">CommonStates</span></span>|<span data-ttu-id="a38bf-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="a38bf-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="a38bf-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="a38bf-119">Pressed</span></span>|<span data-ttu-id="a38bf-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-120">CommonStates</span></span>|<span data-ttu-id="a38bf-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="a38bf-121">The control is pressed.</span></span>|  
|<span data-ttu-id="a38bf-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="a38bf-122">Disabled</span></span>|<span data-ttu-id="a38bf-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-123">CommonStates</span></span>|<span data-ttu-id="a38bf-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="a38bf-124">The control is disabled.</span></span>|  
|<span data-ttu-id="a38bf-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="a38bf-125">Focused</span></span>|<span data-ttu-id="a38bf-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-126">FocusStates</span></span>|<span data-ttu-id="a38bf-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a38bf-127">The control has focus.</span></span>|  
|<span data-ttu-id="a38bf-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="a38bf-128">Unfocused</span></span>|<span data-ttu-id="a38bf-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-129">FocusStates</span></span>|<span data-ttu-id="a38bf-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a38bf-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="a38bf-131">Selezionato con segno di spunta</span><span class="sxs-lookup"><span data-stu-id="a38bf-131">Checked</span></span>|<span data-ttu-id="a38bf-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-132">CheckStates</span></span>|<span data-ttu-id="a38bf-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="a38bf-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="a38bf-134">non è selezionata</span><span class="sxs-lookup"><span data-stu-id="a38bf-134">Unchecked</span></span>|<span data-ttu-id="a38bf-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-135">CheckStates</span></span>|<span data-ttu-id="a38bf-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="a38bf-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="a38bf-137">Indeterminato</span><span class="sxs-lookup"><span data-stu-id="a38bf-137">Indeterminate</span></span>|<span data-ttu-id="a38bf-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-138">CheckStates</span></span>|<span data-ttu-id="a38bf-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>è `true`, e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `null`.</span><span class="sxs-lookup"><span data-stu-id="a38bf-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="a38bf-140">Valido</span><span class="sxs-lookup"><span data-stu-id="a38bf-140">Valid</span></span>|<span data-ttu-id="a38bf-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-141">ValidationStates</span></span>|<span data-ttu-id="a38bf-142">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="a38bf-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a38bf-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a38bf-143">InvalidFocused</span></span>|<span data-ttu-id="a38bf-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-144">ValidationStates</span></span>|<span data-ttu-id="a38bf-145">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a38bf-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a38bf-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a38bf-146">InvalidUnfocused</span></span>|<span data-ttu-id="a38bf-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a38bf-147">ValidationStates</span></span>|<span data-ttu-id="a38bf-148">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="a38bf-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="radiobutton-controltemplate-example"></a><span data-ttu-id="a38bf-149">Esempio di ControlTemplate del controllo RadioButton</span><span class="sxs-lookup"><span data-stu-id="a38bf-149">RadioButton ControlTemplate Example</span></span>  
 <span data-ttu-id="a38bf-150">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.RadioButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="a38bf-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 <span data-ttu-id="a38bf-151">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="a38bf-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a38bf-152">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="a38bf-152">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38bf-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a38bf-153">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="a38bf-154">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="a38bf-154">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="a38bf-155">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="a38bf-155">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="a38bf-156">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="a38bf-156">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a38bf-157">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a38bf-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
