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
ms.openlocfilehash: 64b5b66f7f32ea31b51b4da990ceede4078c27cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177723"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="e2ef3-102">Stili e modelli di StatusBar</span><span class="sxs-lookup"><span data-stu-id="e2ef3-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="e2ef3-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.Primitives.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="e2ef3-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e2ef3-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="e2ef3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="e2ef3-106">Parti di StatusBar</span><span class="sxs-lookup"><span data-stu-id="e2ef3-106">StatusBar Parts</span></span>  
 <span data-ttu-id="e2ef3-107">Il <xref:System.Windows.Controls.Primitives.StatusBar> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="e2ef3-108">Stati di StatusBar</span><span class="sxs-lookup"><span data-stu-id="e2ef3-108">StatusBar States</span></span>  
 <span data-ttu-id="e2ef3-109">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="e2ef3-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="e2ef3-110">VisualState Name</span></span>|<span data-ttu-id="e2ef3-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e2ef3-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e2ef3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2ef3-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e2ef3-113">Valido</span><span class="sxs-lookup"><span data-stu-id="e2ef3-113">Valid</span></span>|<span data-ttu-id="e2ef3-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e2ef3-114">ValidationStates</span></span>|<span data-ttu-id="e2ef3-115">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e2ef3-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e2ef3-116">InvalidFocused</span></span>|<span data-ttu-id="e2ef3-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e2ef3-117">ValidationStates</span></span>|<span data-ttu-id="e2ef3-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e2ef3-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e2ef3-119">InvalidUnfocused</span></span>|<span data-ttu-id="e2ef3-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e2ef3-120">ValidationStates</span></span>|<span data-ttu-id="e2ef3-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="e2ef3-122">StatusBarItem parti</span><span class="sxs-lookup"><span data-stu-id="e2ef3-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="e2ef3-123">Il <xref:System.Windows.Controls.Primitives.StatusBarItem> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="e2ef3-124">Stati di StatusBar</span><span class="sxs-lookup"><span data-stu-id="e2ef3-124">StatusBar States</span></span>  
 <span data-ttu-id="e2ef3-125">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.StatusBarItem> controllo.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="e2ef3-126">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="e2ef3-126">VisualState Name</span></span>|<span data-ttu-id="e2ef3-127">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e2ef3-127">VisualStateGroup Name</span></span>|<span data-ttu-id="e2ef3-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2ef3-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e2ef3-129">Valido</span><span class="sxs-lookup"><span data-stu-id="e2ef3-129">Valid</span></span>|<span data-ttu-id="e2ef3-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e2ef3-130">ValidationStates</span></span>|<span data-ttu-id="e2ef3-131">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e2ef3-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e2ef3-132">InvalidFocused</span></span>|<span data-ttu-id="e2ef3-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e2ef3-133">ValidationStates</span></span>|<span data-ttu-id="e2ef3-134">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e2ef3-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e2ef3-135">InvalidUnfocused</span></span>|<span data-ttu-id="e2ef3-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e2ef3-136">ValidationStates</span></span>|<span data-ttu-id="e2ef3-137">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="e2ef3-138">Esempio di ControlTemplate StatusBar</span><span class="sxs-lookup"><span data-stu-id="e2ef3-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="e2ef3-139">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="e2ef3-140">Il <xref:System.Windows.Controls.ControlTemplate> utilizza uno o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e2ef3-141">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e2ef3-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ef3-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2ef3-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e2ef3-143">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="e2ef3-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e2ef3-144">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="e2ef3-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e2ef3-145">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="e2ef3-145">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="e2ef3-146">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e2ef3-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
