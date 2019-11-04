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
ms.openlocfilehash: f30a0abb3e4252737e513b531b8d5f49a0d47f0b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458450"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="b9c8c-102">Stili e modelli di ScrollBar</span><span class="sxs-lookup"><span data-stu-id="b9c8c-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="b9c8c-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="b9c8c-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b9c8c-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="b9c8c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="b9c8c-106">Parti della barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="b9c8c-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="b9c8c-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="b9c8c-108">Parte</span><span class="sxs-lookup"><span data-stu-id="b9c8c-108">Part</span></span>|<span data-ttu-id="b9c8c-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="b9c8c-109">Type</span></span>|<span data-ttu-id="b9c8c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9c8c-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b9c8c-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="b9c8c-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="b9c8c-112">Contenitore per l'elemento che indica la posizione del <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="b9c8c-113">Stati ScrollBar</span><span class="sxs-lookup"><span data-stu-id="b9c8c-113">ScrollBar States</span></span>  
 <span data-ttu-id="b9c8c-114">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="b9c8c-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="b9c8c-115">VisualState Name</span></span>|<span data-ttu-id="b9c8c-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b9c8c-116">VisualStateGroup Name</span></span>|<span data-ttu-id="b9c8c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9c8c-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="b9c8c-118">Normale</span><span class="sxs-lookup"><span data-stu-id="b9c8c-118">Normal</span></span>|<span data-ttu-id="b9c8c-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b9c8c-119">CommonStates</span></span>|<span data-ttu-id="b9c8c-120">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-120">The default state.</span></span>|  
|<span data-ttu-id="b9c8c-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="b9c8c-121">MouseOver</span></span>|<span data-ttu-id="b9c8c-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b9c8c-122">CommonStates</span></span>|<span data-ttu-id="b9c8c-123">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="b9c8c-124">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="b9c8c-124">Disabled</span></span>|<span data-ttu-id="b9c8c-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b9c8c-125">CommonStates</span></span>|<span data-ttu-id="b9c8c-126">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-126">The control is disabled.</span></span>|  
|<span data-ttu-id="b9c8c-127">Valido</span><span class="sxs-lookup"><span data-stu-id="b9c8c-127">Valid</span></span>|<span data-ttu-id="b9c8c-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b9c8c-128">ValidationStates</span></span>|<span data-ttu-id="b9c8c-129">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b9c8c-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b9c8c-130">InvalidFocused</span></span>|<span data-ttu-id="b9c8c-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b9c8c-131">ValidationStates</span></span>|<span data-ttu-id="b9c8c-132">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="b9c8c-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b9c8c-133">InvalidUnfocused</span></span>|<span data-ttu-id="b9c8c-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b9c8c-134">ValidationStates</span></span>|<span data-ttu-id="b9c8c-135">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="b9c8c-136">Esempio di ControlTemplate ScrollBar</span><span class="sxs-lookup"><span data-stu-id="b9c8c-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="b9c8c-137">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="b9c8c-138">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b9c8c-139">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b9c8c-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c8c-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9c8c-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b9c8c-141">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="b9c8c-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b9c8c-142">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="b9c8c-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b9c8c-143">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="b9c8c-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="b9c8c-144">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b9c8c-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
