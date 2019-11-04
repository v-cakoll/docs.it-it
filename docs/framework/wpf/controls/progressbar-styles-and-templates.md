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
ms.openlocfilehash: 3a1bea39ba9b6d2cff9937a3fee1d1de41daf16b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459878"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="e6dec-102">Stili e modelli di ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e6dec-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="e6dec-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="e6dec-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="e6dec-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="e6dec-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e6dec-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="e6dec-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="e6dec-106">Parti ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e6dec-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="e6dec-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="e6dec-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="e6dec-108">Parte</span><span class="sxs-lookup"><span data-stu-id="e6dec-108">Part</span></span>|<span data-ttu-id="e6dec-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="e6dec-109">Type</span></span>|<span data-ttu-id="e6dec-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6dec-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e6dec-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="e6dec-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="e6dec-112">Oggetto che indica lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="e6dec-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="e6dec-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="e6dec-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="e6dec-114">Oggetto che definisce il percorso dell'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="e6dec-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="e6dec-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="e6dec-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="e6dec-116">Oggetto che abbellisce l'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="e6dec-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="e6dec-117">Stati ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e6dec-117">ProgressBar States</span></span>  
 <span data-ttu-id="e6dec-118">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="e6dec-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="e6dec-119">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="e6dec-119">VisualState Name</span></span>|<span data-ttu-id="e6dec-120">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e6dec-120">VisualStateGroup Name</span></span>|<span data-ttu-id="e6dec-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6dec-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="e6dec-122">Determinato</span><span class="sxs-lookup"><span data-stu-id="e6dec-122">Determinate</span></span>|<span data-ttu-id="e6dec-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e6dec-123">CommonStates</span></span>|<span data-ttu-id="e6dec-124"><xref:System.Windows.Controls.ProgressBar> segnala lo stato di avanzamento in base alla proprietà <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6dec-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="e6dec-125">Indeterminato</span><span class="sxs-lookup"><span data-stu-id="e6dec-125">Indeterminate</span></span>|<span data-ttu-id="e6dec-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e6dec-126">CommonStates</span></span>|<span data-ttu-id="e6dec-127"><xref:System.Windows.Controls.ProgressBar> segnala lo stato di avanzamento generico con un modello ripetuto.</span><span class="sxs-lookup"><span data-stu-id="e6dec-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="e6dec-128">Valido</span><span class="sxs-lookup"><span data-stu-id="e6dec-128">Valid</span></span>|<span data-ttu-id="e6dec-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e6dec-129">ValidationStates</span></span>|<span data-ttu-id="e6dec-130">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="e6dec-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e6dec-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e6dec-131">InvalidFocused</span></span>|<span data-ttu-id="e6dec-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e6dec-132">ValidationStates</span></span>|<span data-ttu-id="e6dec-133">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="e6dec-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e6dec-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e6dec-134">InvalidUnfocused</span></span>|<span data-ttu-id="e6dec-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e6dec-135">ValidationStates</span></span>|<span data-ttu-id="e6dec-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="e6dec-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="e6dec-137">Esempio di ControlTemplate di ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e6dec-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="e6dec-138">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="e6dec-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="e6dec-139">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="e6dec-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e6dec-140">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e6dec-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6dec-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6dec-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e6dec-142">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="e6dec-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e6dec-143">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="e6dec-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e6dec-144">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="e6dec-144">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e6dec-145">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e6dec-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
