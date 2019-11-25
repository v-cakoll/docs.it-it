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
ms.openlocfilehash: 7093a78555aefd73f9bb05c0a7b5fab6b66176fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283407"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="01fd7-102">Stili e modelli di ScrollBar</span><span class="sxs-lookup"><span data-stu-id="01fd7-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="01fd7-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="01fd7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="01fd7-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="01fd7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="01fd7-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="01fd7-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="01fd7-106">Parti della barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="01fd7-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="01fd7-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="01fd7-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="01fd7-108">Parte</span><span class="sxs-lookup"><span data-stu-id="01fd7-108">Part</span></span>|<span data-ttu-id="01fd7-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="01fd7-109">Type</span></span>|<span data-ttu-id="01fd7-110">description</span><span class="sxs-lookup"><span data-stu-id="01fd7-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="01fd7-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="01fd7-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="01fd7-112">Contenitore per l'elemento che indica la posizione del <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="01fd7-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="01fd7-113">Stati ScrollBar</span><span class="sxs-lookup"><span data-stu-id="01fd7-113">ScrollBar States</span></span>  
 <span data-ttu-id="01fd7-114">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="01fd7-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="01fd7-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="01fd7-115">VisualState Name</span></span>|<span data-ttu-id="01fd7-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="01fd7-116">VisualStateGroup Name</span></span>|<span data-ttu-id="01fd7-117">description</span><span class="sxs-lookup"><span data-stu-id="01fd7-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="01fd7-118">Normale</span><span class="sxs-lookup"><span data-stu-id="01fd7-118">Normal</span></span>|<span data-ttu-id="01fd7-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="01fd7-119">CommonStates</span></span>|<span data-ttu-id="01fd7-120">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="01fd7-120">The default state.</span></span>|  
|<span data-ttu-id="01fd7-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="01fd7-121">MouseOver</span></span>|<span data-ttu-id="01fd7-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="01fd7-122">CommonStates</span></span>|<span data-ttu-id="01fd7-123">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="01fd7-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="01fd7-124">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="01fd7-124">Disabled</span></span>|<span data-ttu-id="01fd7-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="01fd7-125">CommonStates</span></span>|<span data-ttu-id="01fd7-126">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="01fd7-126">The control is disabled.</span></span>|  
|<span data-ttu-id="01fd7-127">Valido</span><span class="sxs-lookup"><span data-stu-id="01fd7-127">Valid</span></span>|<span data-ttu-id="01fd7-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="01fd7-128">ValidationStates</span></span>|<span data-ttu-id="01fd7-129">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="01fd7-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="01fd7-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="01fd7-130">InvalidFocused</span></span>|<span data-ttu-id="01fd7-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="01fd7-131">ValidationStates</span></span>|<span data-ttu-id="01fd7-132">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="01fd7-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="01fd7-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="01fd7-133">InvalidUnfocused</span></span>|<span data-ttu-id="01fd7-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="01fd7-134">ValidationStates</span></span>|<span data-ttu-id="01fd7-135">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="01fd7-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="01fd7-136">Esempio di ControlTemplate ScrollBar</span><span class="sxs-lookup"><span data-stu-id="01fd7-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="01fd7-137">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="01fd7-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="01fd7-138">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="01fd7-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="01fd7-139">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="01fd7-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01fd7-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01fd7-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="01fd7-141">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="01fd7-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="01fd7-142">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="01fd7-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="01fd7-143">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="01fd7-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="01fd7-144">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="01fd7-144">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
