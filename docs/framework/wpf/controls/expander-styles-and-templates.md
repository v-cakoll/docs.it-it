---
title: Stili e modelli di Expander
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Expander
- ControlTemplate [WPF], Expander
- templates [WPF], Expander
- Expander [WPF], styles and templates
- states [WPF], Expander
- parts [WPF], Expander
ms.assetid: da2e5a1c-5230-4c21-98a5-59c7895facd7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 04225458e9889c511b7aaa359239512e316cbb26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="060ca-102">Stili e modelli di Expander</span><span class="sxs-lookup"><span data-stu-id="060ca-102">Expander Styles and Templates</span></span>
<span data-ttu-id="060ca-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.Expander> controllo.</span><span class="sxs-lookup"><span data-stu-id="060ca-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="060ca-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="060ca-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="060ca-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="060ca-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="060ca-106">Parti di Expander</span><span class="sxs-lookup"><span data-stu-id="060ca-106">Expander Parts</span></span>  
 <span data-ttu-id="060ca-107">Il <xref:System.Windows.Controls.Expander> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="060ca-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="060ca-108">Stati di Expander</span><span class="sxs-lookup"><span data-stu-id="060ca-108">Expander States</span></span>  
 <span data-ttu-id="060ca-109">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Expander> controllo.</span><span class="sxs-lookup"><span data-stu-id="060ca-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="060ca-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="060ca-110">VisualState Name</span></span>|<span data-ttu-id="060ca-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="060ca-111">VisualStateGroup Name</span></span>|<span data-ttu-id="060ca-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="060ca-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="060ca-113">Normale</span><span class="sxs-lookup"><span data-stu-id="060ca-113">Normal</span></span>|<span data-ttu-id="060ca-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="060ca-114">CommonStates</span></span>|<span data-ttu-id="060ca-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="060ca-115">The default state.</span></span>|  
|<span data-ttu-id="060ca-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="060ca-116">MouseOver</span></span>|<span data-ttu-id="060ca-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="060ca-117">CommonStates</span></span>|<span data-ttu-id="060ca-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="060ca-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="060ca-119">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="060ca-119">Disabled</span></span>|<span data-ttu-id="060ca-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="060ca-120">CommonStates</span></span>|<span data-ttu-id="060ca-121">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="060ca-121">The control is disabled.</span></span>|  
|<span data-ttu-id="060ca-122">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="060ca-122">Focused</span></span>|<span data-ttu-id="060ca-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="060ca-123">FocusStates</span></span>|<span data-ttu-id="060ca-124">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="060ca-124">The control has focus.</span></span>|  
|<span data-ttu-id="060ca-125">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="060ca-125">Unfocused</span></span>|<span data-ttu-id="060ca-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="060ca-126">FocusStates</span></span>|<span data-ttu-id="060ca-127">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="060ca-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="060ca-128">Espanso</span><span class="sxs-lookup"><span data-stu-id="060ca-128">Expanded</span></span>|<span data-ttu-id="060ca-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="060ca-129">ExpansionStates</span></span>|<span data-ttu-id="060ca-130">Il controllo è espanso.</span><span class="sxs-lookup"><span data-stu-id="060ca-130">The control is expanded.</span></span>|  
|<span data-ttu-id="060ca-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="060ca-131">Collapsed</span></span>|<span data-ttu-id="060ca-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="060ca-132">ExpansionStates</span></span>|<span data-ttu-id="060ca-133">Il controllo non è stato espanso.</span><span class="sxs-lookup"><span data-stu-id="060ca-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="060ca-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="060ca-134">ExpandDown</span></span>|<span data-ttu-id="060ca-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="060ca-135">ExpandDirectionStates</span></span>|<span data-ttu-id="060ca-136">Il controllo si espande verso il basso.</span><span class="sxs-lookup"><span data-stu-id="060ca-136">The control expands down.</span></span>|  
|<span data-ttu-id="060ca-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="060ca-137">ExpandUp</span></span>|<span data-ttu-id="060ca-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="060ca-138">ExpandDirectionStates</span></span>|<span data-ttu-id="060ca-139">Il controllo si espande backup.</span><span class="sxs-lookup"><span data-stu-id="060ca-139">The control expands up.</span></span>|  
|<span data-ttu-id="060ca-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="060ca-140">ExpandLeft</span></span>|<span data-ttu-id="060ca-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="060ca-141">ExpandDirectionStates</span></span>|<span data-ttu-id="060ca-142">Il controllo si espande verso sinistra.</span><span class="sxs-lookup"><span data-stu-id="060ca-142">The control expands left.</span></span>|  
|<span data-ttu-id="060ca-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="060ca-143">ExpandRight</span></span>|<span data-ttu-id="060ca-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="060ca-144">ExpandDirectionStates</span></span>|<span data-ttu-id="060ca-145">Il controllo si espande verso destra.</span><span class="sxs-lookup"><span data-stu-id="060ca-145">The control expands right.</span></span>|  
|<span data-ttu-id="060ca-146">Valido</span><span class="sxs-lookup"><span data-stu-id="060ca-146">Valid</span></span>|<span data-ttu-id="060ca-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="060ca-147">ValidationStates</span></span>|<span data-ttu-id="060ca-148">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="060ca-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="060ca-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="060ca-149">InvalidFocused</span></span>|<span data-ttu-id="060ca-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="060ca-150">ValidationStates</span></span>|<span data-ttu-id="060ca-151">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="060ca-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="060ca-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="060ca-152">InvalidUnfocused</span></span>|<span data-ttu-id="060ca-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="060ca-153">ValidationStates</span></span>|<span data-ttu-id="060ca-154">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="060ca-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="060ca-155">Esempio di ControlTemplate Expander</span><span class="sxs-lookup"><span data-stu-id="060ca-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="060ca-156">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Expander> controllo.</span><span class="sxs-lookup"><span data-stu-id="060ca-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="060ca-157">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="060ca-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="060ca-158">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="060ca-158">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="060ca-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="060ca-159">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="060ca-160">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="060ca-160">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="060ca-161">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="060ca-161">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="060ca-162">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="060ca-162">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="060ca-163">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="060ca-163">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
