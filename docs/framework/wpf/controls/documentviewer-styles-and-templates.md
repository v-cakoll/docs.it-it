---
title: Stili e modelli di DocumentViewer
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: ac1dc4f74a8e8f3ad2e84c6d50239ec827306c28
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283524"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="51a58-102">Stili e modelli di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="51a58-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="51a58-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="51a58-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="51a58-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="51a58-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="51a58-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="51a58-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="51a58-106">Parti di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="51a58-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="51a58-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="51a58-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="51a58-108">Parte</span><span class="sxs-lookup"><span data-stu-id="51a58-108">Part</span></span>|<span data-ttu-id="51a58-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="51a58-109">Type</span></span>|<span data-ttu-id="51a58-110">description</span><span class="sxs-lookup"><span data-stu-id="51a58-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="51a58-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="51a58-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="51a58-112">Il contenuto e l'area di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="51a58-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="51a58-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="51a58-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="51a58-114">Casella di ricerca nella parte inferiore per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="51a58-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="51a58-115">Stati di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="51a58-115">DocumentViewer States</span></span>  
 <span data-ttu-id="51a58-116">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="51a58-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="51a58-117">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="51a58-117">VisualState Name</span></span>|<span data-ttu-id="51a58-118">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="51a58-118">VisualStateGroup Name</span></span>|<span data-ttu-id="51a58-119">description</span><span class="sxs-lookup"><span data-stu-id="51a58-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="51a58-120">Valido</span><span class="sxs-lookup"><span data-stu-id="51a58-120">Valid</span></span>|<span data-ttu-id="51a58-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="51a58-121">ValidationStates</span></span>|<span data-ttu-id="51a58-122">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="51a58-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="51a58-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="51a58-123">InvalidFocused</span></span>|<span data-ttu-id="51a58-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="51a58-124">ValidationStates</span></span>|<span data-ttu-id="51a58-125">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="51a58-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="51a58-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="51a58-126">InvalidUnfocused</span></span>|<span data-ttu-id="51a58-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="51a58-127">ValidationStates</span></span>|<span data-ttu-id="51a58-128">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="51a58-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="51a58-129">Esempio di ControlTemplate di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="51a58-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="51a58-130">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="51a58-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="51a58-131">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="51a58-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="51a58-132">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="51a58-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51a58-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51a58-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="51a58-134">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="51a58-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="51a58-135">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="51a58-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="51a58-136">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="51a58-136">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="51a58-137">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="51a58-137">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
