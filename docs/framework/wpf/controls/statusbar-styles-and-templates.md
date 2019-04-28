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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790962"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="eaef2-102">Stili e modelli di StatusBar</span><span class="sxs-lookup"><span data-stu-id="eaef2-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="eaef2-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.Primitives.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="eaef2-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="eaef2-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="eaef2-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="eaef2-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="eaef2-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="eaef2-106">Parti di StatusBar</span><span class="sxs-lookup"><span data-stu-id="eaef2-106">StatusBar Parts</span></span>  
 <span data-ttu-id="eaef2-107">Il <xref:System.Windows.Controls.Primitives.StatusBar> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="eaef2-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="eaef2-108">Stati di StatusBar</span><span class="sxs-lookup"><span data-stu-id="eaef2-108">StatusBar States</span></span>  
 <span data-ttu-id="eaef2-109">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="eaef2-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="eaef2-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="eaef2-110">VisualState Name</span></span>|<span data-ttu-id="eaef2-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="eaef2-111">VisualStateGroup Name</span></span>|<span data-ttu-id="eaef2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaef2-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="eaef2-113">Valido</span><span class="sxs-lookup"><span data-stu-id="eaef2-113">Valid</span></span>|<span data-ttu-id="eaef2-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eaef2-114">ValidationStates</span></span>|<span data-ttu-id="eaef2-115">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="eaef2-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="eaef2-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="eaef2-116">InvalidFocused</span></span>|<span data-ttu-id="eaef2-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eaef2-117">ValidationStates</span></span>|<span data-ttu-id="eaef2-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="eaef2-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="eaef2-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="eaef2-119">InvalidUnfocused</span></span>|<span data-ttu-id="eaef2-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eaef2-120">ValidationStates</span></span>|<span data-ttu-id="eaef2-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="eaef2-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="eaef2-122">StatusBarItem parti</span><span class="sxs-lookup"><span data-stu-id="eaef2-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="eaef2-123">Il <xref:System.Windows.Controls.Primitives.StatusBarItem> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="eaef2-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="eaef2-124">Stati di StatusBar</span><span class="sxs-lookup"><span data-stu-id="eaef2-124">StatusBar States</span></span>  
 <span data-ttu-id="eaef2-125">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.StatusBarItem> controllo.</span><span class="sxs-lookup"><span data-stu-id="eaef2-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="eaef2-126">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="eaef2-126">VisualState Name</span></span>|<span data-ttu-id="eaef2-127">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="eaef2-127">VisualStateGroup Name</span></span>|<span data-ttu-id="eaef2-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaef2-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="eaef2-129">Valido</span><span class="sxs-lookup"><span data-stu-id="eaef2-129">Valid</span></span>|<span data-ttu-id="eaef2-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eaef2-130">ValidationStates</span></span>|<span data-ttu-id="eaef2-131">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="eaef2-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="eaef2-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="eaef2-132">InvalidFocused</span></span>|<span data-ttu-id="eaef2-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eaef2-133">ValidationStates</span></span>|<span data-ttu-id="eaef2-134">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="eaef2-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="eaef2-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="eaef2-135">InvalidUnfocused</span></span>|<span data-ttu-id="eaef2-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eaef2-136">ValidationStates</span></span>|<span data-ttu-id="eaef2-137">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="eaef2-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="eaef2-138">Esempio di ControlTemplate StatusBar</span><span class="sxs-lookup"><span data-stu-id="eaef2-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="eaef2-139">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="eaef2-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="eaef2-140">Il <xref:System.Windows.Controls.ControlTemplate> utilizza uno o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="eaef2-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="eaef2-141">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="eaef2-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaef2-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eaef2-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="eaef2-143">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="eaef2-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="eaef2-144">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="eaef2-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="eaef2-145">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="eaef2-145">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="eaef2-146">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="eaef2-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
