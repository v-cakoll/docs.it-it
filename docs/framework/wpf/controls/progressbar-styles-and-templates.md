---
title: Stili e modelli di ProgressBar
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 6551701e86dd6abcd42f143f146c7bdadfeabbcf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283446"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="fb272-102">Stili e modelli di ProgressBar</span><span class="sxs-lookup"><span data-stu-id="fb272-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="fb272-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="fb272-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="fb272-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="fb272-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fb272-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="fb272-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="fb272-106">Parti ProgressBar</span><span class="sxs-lookup"><span data-stu-id="fb272-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="fb272-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="fb272-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="fb272-108">Parte</span><span class="sxs-lookup"><span data-stu-id="fb272-108">Part</span></span>|<span data-ttu-id="fb272-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="fb272-109">Type</span></span>|<span data-ttu-id="fb272-110">description</span><span class="sxs-lookup"><span data-stu-id="fb272-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fb272-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="fb272-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="fb272-112">Oggetto che indica lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="fb272-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="fb272-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="fb272-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="fb272-114">Oggetto che definisce il percorso dell'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="fb272-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="fb272-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="fb272-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="fb272-116">Oggetto che abbellisce l'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="fb272-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="fb272-117">Stati ProgressBar</span><span class="sxs-lookup"><span data-stu-id="fb272-117">ProgressBar States</span></span>  
 <span data-ttu-id="fb272-118">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="fb272-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="fb272-119">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="fb272-119">VisualState Name</span></span>|<span data-ttu-id="fb272-120">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="fb272-120">VisualStateGroup Name</span></span>|<span data-ttu-id="fb272-121">description</span><span class="sxs-lookup"><span data-stu-id="fb272-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="fb272-122">Determinato</span><span class="sxs-lookup"><span data-stu-id="fb272-122">Determinate</span></span>|<span data-ttu-id="fb272-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fb272-123">CommonStates</span></span>|<span data-ttu-id="fb272-124"><xref:System.Windows.Controls.ProgressBar> segnala lo stato di avanzamento in base alla proprietà <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb272-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="fb272-125">Indeterminato</span><span class="sxs-lookup"><span data-stu-id="fb272-125">Indeterminate</span></span>|<span data-ttu-id="fb272-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fb272-126">CommonStates</span></span>|<span data-ttu-id="fb272-127"><xref:System.Windows.Controls.ProgressBar> segnala lo stato di avanzamento generico con un modello ripetuto.</span><span class="sxs-lookup"><span data-stu-id="fb272-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="fb272-128">Valido</span><span class="sxs-lookup"><span data-stu-id="fb272-128">Valid</span></span>|<span data-ttu-id="fb272-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fb272-129">ValidationStates</span></span>|<span data-ttu-id="fb272-130">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="fb272-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fb272-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fb272-131">InvalidFocused</span></span>|<span data-ttu-id="fb272-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fb272-132">ValidationStates</span></span>|<span data-ttu-id="fb272-133">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="fb272-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fb272-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fb272-134">InvalidUnfocused</span></span>|<span data-ttu-id="fb272-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fb272-135">ValidationStates</span></span>|<span data-ttu-id="fb272-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="fb272-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="fb272-137">Esempio di ControlTemplate di ProgressBar</span><span class="sxs-lookup"><span data-stu-id="fb272-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="fb272-138">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="fb272-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="fb272-139">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="fb272-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fb272-140">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="fb272-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb272-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb272-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fb272-142">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="fb272-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fb272-143">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="fb272-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fb272-144">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="fb272-144">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="fb272-145">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="fb272-145">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
