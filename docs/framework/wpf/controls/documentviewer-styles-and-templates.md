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
ms.openlocfilehash: 4e91a640b36e4793567c9e728fd71ec8ce596743
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158418"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="b82c2-102">Stili e modelli di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="b82c2-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="b82c2-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="b82c2-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="b82c2-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="b82c2-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b82c2-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="b82c2-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="b82c2-106">Parti di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="b82c2-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="b82c2-107">La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="b82c2-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="b82c2-108">Parte</span><span class="sxs-lookup"><span data-stu-id="b82c2-108">Part</span></span>|<span data-ttu-id="b82c2-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="b82c2-109">Type</span></span>|<span data-ttu-id="b82c2-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b82c2-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b82c2-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="b82c2-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="b82c2-112">Il contenuto e l'area di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="b82c2-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="b82c2-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="b82c2-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="b82c2-114">Casella di ricerca nella parte inferiore per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b82c2-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="b82c2-115">Stati di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="b82c2-115">DocumentViewer States</span></span>  
 <span data-ttu-id="b82c2-116">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="b82c2-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="b82c2-117">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="b82c2-117">VisualState Name</span></span>|<span data-ttu-id="b82c2-118">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b82c2-118">VisualStateGroup Name</span></span>|<span data-ttu-id="b82c2-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b82c2-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b82c2-120">Valido</span><span class="sxs-lookup"><span data-stu-id="b82c2-120">Valid</span></span>|<span data-ttu-id="b82c2-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b82c2-121">ValidationStates</span></span>|<span data-ttu-id="b82c2-122">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="b82c2-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b82c2-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b82c2-123">InvalidFocused</span></span>|<span data-ttu-id="b82c2-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b82c2-124">ValidationStates</span></span>|<span data-ttu-id="b82c2-125">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="b82c2-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b82c2-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b82c2-126">InvalidUnfocused</span></span>|<span data-ttu-id="b82c2-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b82c2-127">ValidationStates</span></span>|<span data-ttu-id="b82c2-128">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="b82c2-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="b82c2-129">Esempio di ControlTemplate DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="b82c2-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="b82c2-130">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="b82c2-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="b82c2-131">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="b82c2-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b82c2-132">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b82c2-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b82c2-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b82c2-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b82c2-134">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="b82c2-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b82c2-135">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="b82c2-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b82c2-136">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="b82c2-136">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="b82c2-137">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b82c2-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
