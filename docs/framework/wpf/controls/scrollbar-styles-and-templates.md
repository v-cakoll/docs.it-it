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
ms.openlocfilehash: 926fc3373bb40eb12462dcead278d458cefad7cf
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457577"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="a4b2d-102">Stili e modelli di ScrollBar</span><span class="sxs-lookup"><span data-stu-id="a4b2d-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="a4b2d-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.Primitives.ScrollBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="a4b2d-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a4b2d-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a4b2d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="a4b2d-106">Parti di ScrollBar</span><span class="sxs-lookup"><span data-stu-id="a4b2d-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="a4b2d-107">La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.Primitives.ScrollBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="a4b2d-108">Parte</span><span class="sxs-lookup"><span data-stu-id="a4b2d-108">Part</span></span>|<span data-ttu-id="a4b2d-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="a4b2d-109">Type</span></span>|<span data-ttu-id="a4b2d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4b2d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a4b2d-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="a4b2d-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="a4b2d-112">Il contenitore per l'elemento che indica la posizione del <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="a4b2d-113">Stati del controllo ScrollBar</span><span class="sxs-lookup"><span data-stu-id="a4b2d-113">ScrollBar States</span></span>  
 <span data-ttu-id="a4b2d-114">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Primitives.ScrollBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="a4b2d-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="a4b2d-115">VisualState Name</span></span>|<span data-ttu-id="a4b2d-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a4b2d-116">VisualStateGroup Name</span></span>|<span data-ttu-id="a4b2d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4b2d-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="a4b2d-118">Normale</span><span class="sxs-lookup"><span data-stu-id="a4b2d-118">Normal</span></span>|<span data-ttu-id="a4b2d-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4b2d-119">CommonStates</span></span>|<span data-ttu-id="a4b2d-120">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-120">The default state.</span></span>|  
|<span data-ttu-id="a4b2d-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a4b2d-121">MouseOver</span></span>|<span data-ttu-id="a4b2d-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4b2d-122">CommonStates</span></span>|<span data-ttu-id="a4b2d-123">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="a4b2d-124">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="a4b2d-124">Disabled</span></span>|<span data-ttu-id="a4b2d-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4b2d-125">CommonStates</span></span>|<span data-ttu-id="a4b2d-126">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-126">The control is disabled.</span></span>|  
|<span data-ttu-id="a4b2d-127">Valido</span><span class="sxs-lookup"><span data-stu-id="a4b2d-127">Valid</span></span>|<span data-ttu-id="a4b2d-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4b2d-128">ValidationStates</span></span>|<span data-ttu-id="a4b2d-129">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a4b2d-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a4b2d-130">InvalidFocused</span></span>|<span data-ttu-id="a4b2d-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4b2d-131">ValidationStates</span></span>|<span data-ttu-id="a4b2d-132">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a4b2d-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a4b2d-133">InvalidUnfocused</span></span>|<span data-ttu-id="a4b2d-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4b2d-134">ValidationStates</span></span>|<span data-ttu-id="a4b2d-135">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="a4b2d-136">Esempio di ControlTemplate del controllo barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="a4b2d-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="a4b2d-137">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.ScrollBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="a4b2d-138">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="a4b2d-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a4b2d-139">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a4b2d-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b2d-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4b2d-140">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="a4b2d-141">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="a4b2d-141">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="a4b2d-142">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="a4b2d-142">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="a4b2d-143">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="a4b2d-143">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a4b2d-144">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a4b2d-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
