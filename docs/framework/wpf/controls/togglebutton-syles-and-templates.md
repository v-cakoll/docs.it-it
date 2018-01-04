---
title: Stili e modelli di ToggleButton
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c143717b691e79771fbaa55724d9d9748259e3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="togglebutton-syles-and-templates"></a><span data-ttu-id="9814c-102">Stili e modelli di ToggleButton</span><span class="sxs-lookup"><span data-stu-id="9814c-102">ToggleButton Syles and Templates</span></span>
<span data-ttu-id="9814c-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="9814c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="9814c-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="9814c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9814c-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="9814c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="togglebutton-parts"></a><span data-ttu-id="9814c-106">ToggleButton parti</span><span class="sxs-lookup"><span data-stu-id="9814c-106">ToggleButton Parts</span></span>  
 <span data-ttu-id="9814c-107">Il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="9814c-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>  
  
## <a name="togglebutton-states"></a><span data-ttu-id="9814c-108">Stati ToggleButton</span><span class="sxs-lookup"><span data-stu-id="9814c-108">ToggleButton States</span></span>  
 <span data-ttu-id="9814c-109">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="9814c-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
|<span data-ttu-id="9814c-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="9814c-110">VisualState Name</span></span>|<span data-ttu-id="9814c-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="9814c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="9814c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9814c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9814c-113">Normale</span><span class="sxs-lookup"><span data-stu-id="9814c-113">Normal</span></span>|<span data-ttu-id="9814c-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9814c-114">CommonStates</span></span>|<span data-ttu-id="9814c-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="9814c-115">The default state.</span></span>|  
|<span data-ttu-id="9814c-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="9814c-116">MouseOver</span></span>|<span data-ttu-id="9814c-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9814c-117">CommonStates</span></span>|<span data-ttu-id="9814c-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="9814c-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="9814c-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="9814c-119">Pressed</span></span>|<span data-ttu-id="9814c-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9814c-120">CommonStates</span></span>|<span data-ttu-id="9814c-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="9814c-121">The control is pressed.</span></span>|  
|<span data-ttu-id="9814c-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="9814c-122">Disabled</span></span>|<span data-ttu-id="9814c-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9814c-123">CommonStates</span></span>|<span data-ttu-id="9814c-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="9814c-124">The control is disabled.</span></span>|  
|<span data-ttu-id="9814c-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="9814c-125">Focused</span></span>|<span data-ttu-id="9814c-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9814c-126">FocusStates</span></span>|<span data-ttu-id="9814c-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="9814c-127">The control has focus.</span></span>|  
|<span data-ttu-id="9814c-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="9814c-128">Unfocused</span></span>|<span data-ttu-id="9814c-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9814c-129">FocusStates</span></span>|<span data-ttu-id="9814c-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="9814c-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="9814c-131">Selezionato con segno di spunta</span><span class="sxs-lookup"><span data-stu-id="9814c-131">Checked</span></span>|<span data-ttu-id="9814c-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="9814c-132">CheckStates</span></span>|<span data-ttu-id="9814c-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="9814c-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="9814c-134">non è selezionata</span><span class="sxs-lookup"><span data-stu-id="9814c-134">Unchecked</span></span>|<span data-ttu-id="9814c-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="9814c-135">CheckStates</span></span>|<span data-ttu-id="9814c-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="9814c-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="9814c-137">Indeterminato</span><span class="sxs-lookup"><span data-stu-id="9814c-137">Indeterminate</span></span>|<span data-ttu-id="9814c-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="9814c-138">CheckStates</span></span>|<span data-ttu-id="9814c-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>è `true`, e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `null`.</span><span class="sxs-lookup"><span data-stu-id="9814c-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="9814c-140">Valido</span><span class="sxs-lookup"><span data-stu-id="9814c-140">Valid</span></span>|<span data-ttu-id="9814c-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9814c-141">ValidationStates</span></span>|<span data-ttu-id="9814c-142">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="9814c-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9814c-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9814c-143">InvalidFocused</span></span>|<span data-ttu-id="9814c-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9814c-144">ValidationStates</span></span>|<span data-ttu-id="9814c-145">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="9814c-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9814c-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9814c-146">InvalidUnfocused</span></span>|<span data-ttu-id="9814c-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9814c-147">ValidationStates</span></span>|<span data-ttu-id="9814c-148">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="9814c-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9814c-149">Se lo stato di visualizzazione indeterminato non esiste nel modello di controllo, lo stato di visualizzazione non è selezionato verrà utilizzato come stato di visualizzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="9814c-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>  
  
## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="9814c-150">Esempio di ControlTemplate ToggleButton</span><span class="sxs-lookup"><span data-stu-id="9814c-150">ToggleButton ControlTemplate Example</span></span>  
 <span data-ttu-id="9814c-151">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="9814c-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToggleButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]  
  
 <span data-ttu-id="9814c-152">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="9814c-152">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9814c-153">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="9814c-153">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9814c-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9814c-154">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="9814c-155">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="9814c-155">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="9814c-156">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="9814c-156">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="9814c-157">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="9814c-157">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="9814c-158">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="9814c-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
