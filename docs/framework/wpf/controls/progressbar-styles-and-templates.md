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
ms.openlocfilehash: f948cf2b4f4cd2a4cb73b0cd5fc754240c850b83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099417"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="547e4-102">Stili e modelli di ProgressBar</span><span class="sxs-lookup"><span data-stu-id="547e4-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="547e4-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="547e4-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="547e4-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="547e4-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="547e4-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="547e4-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="547e4-106">Parti del controllo ProgressBar</span><span class="sxs-lookup"><span data-stu-id="547e4-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="547e4-107">La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="547e4-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="547e4-108">Parte</span><span class="sxs-lookup"><span data-stu-id="547e4-108">Part</span></span>|<span data-ttu-id="547e4-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="547e4-109">Type</span></span>|<span data-ttu-id="547e4-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="547e4-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="547e4-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="547e4-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="547e4-112">Oggetto che indica lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="547e4-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="547e4-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="547e4-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="547e4-114">Oggetto che definisce il percorso dell'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="547e4-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="547e4-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="547e4-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="547e4-116">Oggetto che abbellisce l'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="547e4-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="547e4-117">Stati del controllo ProgressBar</span><span class="sxs-lookup"><span data-stu-id="547e4-117">ProgressBar States</span></span>  
 <span data-ttu-id="547e4-118">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="547e4-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="547e4-119">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="547e4-119">VisualState Name</span></span>|<span data-ttu-id="547e4-120">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="547e4-120">VisualStateGroup Name</span></span>|<span data-ttu-id="547e4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="547e4-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="547e4-122">Indicatore</span><span class="sxs-lookup"><span data-stu-id="547e4-122">Determinate</span></span>|<span data-ttu-id="547e4-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="547e4-123">CommonStates</span></span>|<xref:System.Windows.Controls.ProgressBar> <span data-ttu-id="547e4-124">segnala lo stato di base di <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="547e4-124">reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="547e4-125">Indeterminato</span><span class="sxs-lookup"><span data-stu-id="547e4-125">Indeterminate</span></span>|<span data-ttu-id="547e4-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="547e4-126">CommonStates</span></span>|<xref:System.Windows.Controls.ProgressBar> <span data-ttu-id="547e4-127">segnala lo stato di avanzamento generico con un motivo ripetuto.</span><span class="sxs-lookup"><span data-stu-id="547e4-127">reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="547e4-128">Valido</span><span class="sxs-lookup"><span data-stu-id="547e4-128">Valid</span></span>|<span data-ttu-id="547e4-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="547e4-129">ValidationStates</span></span>|<span data-ttu-id="547e4-130">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="547e4-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="547e4-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="547e4-131">InvalidFocused</span></span>|<span data-ttu-id="547e4-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="547e4-132">ValidationStates</span></span>|<span data-ttu-id="547e4-133">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="547e4-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="547e4-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="547e4-134">InvalidUnfocused</span></span>|<span data-ttu-id="547e4-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="547e4-135">ValidationStates</span></span>|<span data-ttu-id="547e4-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="547e4-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="547e4-137">Esempio di ControlTemplate ProgressBar</span><span class="sxs-lookup"><span data-stu-id="547e4-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="547e4-138">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="547e4-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="547e4-139">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="547e4-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="547e4-140">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="547e4-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="547e4-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="547e4-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="547e4-142">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="547e4-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="547e4-143">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="547e4-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="547e4-144">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="547e4-144">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="547e4-145">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="547e4-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
