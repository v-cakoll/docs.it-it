---
title: Stili e modelli di StatusBar
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 843c9003edbe94115719a63a968eda3833515a85
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283379"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="b7913-102">Stili e modelli di StatusBar</span><span class="sxs-lookup"><span data-stu-id="b7913-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="b7913-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="b7913-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="b7913-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="b7913-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b7913-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="b7913-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="b7913-106">Parti StatusBar</span><span class="sxs-lookup"><span data-stu-id="b7913-106">StatusBar Parts</span></span>  
 <span data-ttu-id="b7913-107">Il controllo <xref:System.Windows.Controls.Primitives.StatusBar> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="b7913-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="b7913-108">Stati di StatusBar</span><span class="sxs-lookup"><span data-stu-id="b7913-108">StatusBar States</span></span>  
 <span data-ttu-id="b7913-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="b7913-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="b7913-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="b7913-110">VisualState Name</span></span>|<span data-ttu-id="b7913-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b7913-111">VisualStateGroup Name</span></span>|<span data-ttu-id="b7913-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7913-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b7913-113">Valido</span><span class="sxs-lookup"><span data-stu-id="b7913-113">Valid</span></span>|<span data-ttu-id="b7913-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b7913-114">ValidationStates</span></span>|<span data-ttu-id="b7913-115">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="b7913-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b7913-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b7913-116">InvalidFocused</span></span>|<span data-ttu-id="b7913-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b7913-117">ValidationStates</span></span>|<span data-ttu-id="b7913-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="b7913-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b7913-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b7913-119">InvalidUnfocused</span></span>|<span data-ttu-id="b7913-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b7913-120">ValidationStates</span></span>|<span data-ttu-id="b7913-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="b7913-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="b7913-122">Parti StatusBarItem</span><span class="sxs-lookup"><span data-stu-id="b7913-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="b7913-123">Il controllo <xref:System.Windows.Controls.Primitives.StatusBarItem> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="b7913-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="b7913-124">Stati di StatusBar</span><span class="sxs-lookup"><span data-stu-id="b7913-124">StatusBar States</span></span>  
 <span data-ttu-id="b7913-125">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.StatusBarItem>.</span><span class="sxs-lookup"><span data-stu-id="b7913-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="b7913-126">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="b7913-126">VisualState Name</span></span>|<span data-ttu-id="b7913-127">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b7913-127">VisualStateGroup Name</span></span>|<span data-ttu-id="b7913-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7913-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b7913-129">Valido</span><span class="sxs-lookup"><span data-stu-id="b7913-129">Valid</span></span>|<span data-ttu-id="b7913-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b7913-130">ValidationStates</span></span>|<span data-ttu-id="b7913-131">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="b7913-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b7913-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b7913-132">InvalidFocused</span></span>|<span data-ttu-id="b7913-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b7913-133">ValidationStates</span></span>|<span data-ttu-id="b7913-134">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="b7913-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b7913-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b7913-135">InvalidUnfocused</span></span>|<span data-ttu-id="b7913-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b7913-136">ValidationStates</span></span>|<span data-ttu-id="b7913-137">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="b7913-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="b7913-138">Esempio di ControlTemplate StatusBar</span><span class="sxs-lookup"><span data-stu-id="b7913-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="b7913-139">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="b7913-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="b7913-140">Il <xref:System.Windows.Controls.ControlTemplate> utilizza una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="b7913-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b7913-141">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b7913-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7913-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7913-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b7913-143">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="b7913-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b7913-144">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="b7913-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b7913-145">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="b7913-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="b7913-146">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="b7913-146">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
