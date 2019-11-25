---
title: Stili e modelli di ScrollViewer
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: b54dcacf55a750d7c1253db20147d18de47d027e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283401"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="79363-102">Stili e modelli di ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="79363-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="79363-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="79363-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="79363-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="79363-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="79363-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="79363-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="79363-106">Parti ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="79363-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="79363-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="79363-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="79363-108">Parte</span><span class="sxs-lookup"><span data-stu-id="79363-108">Part</span></span>|<span data-ttu-id="79363-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="79363-109">Type</span></span>|<span data-ttu-id="79363-110">description</span><span class="sxs-lookup"><span data-stu-id="79363-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="79363-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="79363-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="79363-112">Segnaposto per il contenuto nel <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="79363-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="79363-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="79363-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="79363-114"><xref:System.Windows.Controls.Primitives.ScrollBar> utilizzato per scorrere il contenuto orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="79363-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="79363-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="79363-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="79363-116"><xref:System.Windows.Controls.Primitives.ScrollBar> utilizzato per scorrere il contenuto verticalmente.</span><span class="sxs-lookup"><span data-stu-id="79363-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="79363-117">Stati di ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="79363-117">ScrollViewer States</span></span>  
 <span data-ttu-id="79363-118">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="79363-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="79363-119">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="79363-119">VisualState Name</span></span>|<span data-ttu-id="79363-120">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="79363-120">VisualStateGroup Name</span></span>|<span data-ttu-id="79363-121">description</span><span class="sxs-lookup"><span data-stu-id="79363-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="79363-122">Valido</span><span class="sxs-lookup"><span data-stu-id="79363-122">Valid</span></span>|<span data-ttu-id="79363-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="79363-123">ValidationStates</span></span>|<span data-ttu-id="79363-124">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="79363-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="79363-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="79363-125">InvalidFocused</span></span>|<span data-ttu-id="79363-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="79363-126">ValidationStates</span></span>|<span data-ttu-id="79363-127">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="79363-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="79363-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="79363-128">InvalidUnfocused</span></span>|<span data-ttu-id="79363-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="79363-129">ValidationStates</span></span>|<span data-ttu-id="79363-130">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="79363-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="79363-131">Esempio di ControlTemplate ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="79363-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="79363-132">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="79363-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="79363-133">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="79363-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="79363-134">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="79363-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79363-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79363-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="79363-136">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="79363-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="79363-137">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="79363-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="79363-138">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="79363-138">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="79363-139">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="79363-139">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
