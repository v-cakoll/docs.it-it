---
title: Stili e modelli di ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 016556fb825ddf60af7dc572d6fda7323b9bb09d
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671974"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="df740-102">Stili e modelli di ScrollBar</span><span class="sxs-lookup"><span data-stu-id="df740-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="df740-103">In questo argomento vengono descritti gli stili e i <xref:System.Windows.Controls.Primitives.ScrollBar> modelli per il controllo.</span><span class="sxs-lookup"><span data-stu-id="df740-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="df740-104">È possibile modificare l'impostazione <xref:System.Windows.Controls.ControlTemplate> predefinita per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="df740-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="df740-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="df740-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="df740-106">Parti della barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="df740-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="df740-107">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.Primitives.ScrollBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="df740-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="df740-108">Parte</span><span class="sxs-lookup"><span data-stu-id="df740-108">Part</span></span>|<span data-ttu-id="df740-109">Type</span><span class="sxs-lookup"><span data-stu-id="df740-109">Type</span></span>|<span data-ttu-id="df740-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df740-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="df740-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="df740-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="df740-112">Contenitore per l'elemento che indica la posizione dell'oggetto <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="df740-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="df740-113">Stati ScrollBar</span><span class="sxs-lookup"><span data-stu-id="df740-113">ScrollBar States</span></span>  
 <span data-ttu-id="df740-114">Nella tabella seguente sono elencati gli Stati di visualizzazione <xref:System.Windows.Controls.Primitives.ScrollBar> per il controllo.</span><span class="sxs-lookup"><span data-stu-id="df740-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="df740-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="df740-115">VisualState Name</span></span>|<span data-ttu-id="df740-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="df740-116">VisualStateGroup Name</span></span>|<span data-ttu-id="df740-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df740-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="df740-118">Normale</span><span class="sxs-lookup"><span data-stu-id="df740-118">Normal</span></span>|<span data-ttu-id="df740-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="df740-119">CommonStates</span></span>|<span data-ttu-id="df740-120">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="df740-120">The default state.</span></span>|  
|<span data-ttu-id="df740-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="df740-121">MouseOver</span></span>|<span data-ttu-id="df740-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="df740-122">CommonStates</span></span>|<span data-ttu-id="df740-123">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="df740-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="df740-124">Disabled</span><span class="sxs-lookup"><span data-stu-id="df740-124">Disabled</span></span>|<span data-ttu-id="df740-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="df740-125">CommonStates</span></span>|<span data-ttu-id="df740-126">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="df740-126">The control is disabled.</span></span>|  
|<span data-ttu-id="df740-127">Valido</span><span class="sxs-lookup"><span data-stu-id="df740-127">Valid</span></span>|<span data-ttu-id="df740-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="df740-128">ValidationStates</span></span>|<span data-ttu-id="df740-129">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="df740-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="df740-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="df740-130">InvalidFocused</span></span>|<span data-ttu-id="df740-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="df740-131">ValidationStates</span></span>|<span data-ttu-id="df740-132">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="df740-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="df740-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="df740-133">InvalidUnfocused</span></span>|<span data-ttu-id="df740-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="df740-134">ValidationStates</span></span>|<span data-ttu-id="df740-135">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="df740-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="df740-136">Esempio di ControlTemplate ScrollBar</span><span class="sxs-lookup"><span data-stu-id="df740-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="df740-137">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> oggetto per <xref:System.Windows.Controls.Primitives.ScrollBar> il controllo.</span><span class="sxs-lookup"><span data-stu-id="df740-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="df740-138">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="df740-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="df740-139">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="df740-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df740-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df740-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="df740-141">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="df740-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="df740-142">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="df740-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="df740-143">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="df740-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="df740-144">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="df740-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
