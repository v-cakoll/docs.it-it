---
title: Stili e modelli di Frame
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 89f4fc21637d20ca226507463093bc6bae2241fc
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460319"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="49e23-102">Stili e modelli di Frame</span><span class="sxs-lookup"><span data-stu-id="49e23-102">Frame Styles and Templates</span></span>
<span data-ttu-id="49e23-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="49e23-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="49e23-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="49e23-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="49e23-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="49e23-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="49e23-106">Parti cornice</span><span class="sxs-lookup"><span data-stu-id="49e23-106">Frame Parts</span></span>  
 <span data-ttu-id="49e23-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="49e23-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="49e23-108">Parte</span><span class="sxs-lookup"><span data-stu-id="49e23-108">Part</span></span>|<span data-ttu-id="49e23-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="49e23-109">Type</span></span>|<span data-ttu-id="49e23-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49e23-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="49e23-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="49e23-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="49e23-112">Area del contenuto.</span><span class="sxs-lookup"><span data-stu-id="49e23-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="49e23-113">Stati frame</span><span class="sxs-lookup"><span data-stu-id="49e23-113">Frame States</span></span>  
 <span data-ttu-id="49e23-114">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="49e23-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="49e23-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="49e23-115">VisualState Name</span></span>|<span data-ttu-id="49e23-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="49e23-116">VisualStateGroup Name</span></span>|<span data-ttu-id="49e23-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49e23-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="49e23-118">Valido</span><span class="sxs-lookup"><span data-stu-id="49e23-118">Valid</span></span>|<span data-ttu-id="49e23-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="49e23-119">ValidationStates</span></span>|<span data-ttu-id="49e23-120">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="49e23-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="49e23-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="49e23-121">InvalidFocused</span></span>|<span data-ttu-id="49e23-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="49e23-122">ValidationStates</span></span>|<span data-ttu-id="49e23-123">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="49e23-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="49e23-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="49e23-124">InvalidUnfocused</span></span>|<span data-ttu-id="49e23-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="49e23-125">ValidationStates</span></span>|<span data-ttu-id="49e23-126">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="49e23-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="49e23-127">Esempio di ControlTemplate frame</span><span class="sxs-lookup"><span data-stu-id="49e23-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="49e23-128">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="49e23-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="49e23-129">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="49e23-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="49e23-130">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="49e23-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e23-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49e23-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="49e23-132">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="49e23-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="49e23-133">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="49e23-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="49e23-134">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="49e23-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="49e23-135">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="49e23-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
