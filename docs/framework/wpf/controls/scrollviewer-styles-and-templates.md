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
ms.openlocfilehash: 9c0edfd7ab4772eb9a1f5ecdd3db611fa36bf8d3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226833"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="3e1ae-102">Stili e modelli di ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="3e1ae-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="3e1ae-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="3e1ae-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3e1ae-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="3e1ae-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="3e1ae-106">Parti del controllo ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="3e1ae-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="3e1ae-107">La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="3e1ae-108">Parte</span><span class="sxs-lookup"><span data-stu-id="3e1ae-108">Part</span></span>|<span data-ttu-id="3e1ae-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="3e1ae-109">Type</span></span>|<span data-ttu-id="3e1ae-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e1ae-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3e1ae-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="3e1ae-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="3e1ae-112">Il segnaposto per il contenuto di <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="3e1ae-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="3e1ae-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="3e1ae-114">Il <xref:System.Windows.Controls.Primitives.ScrollBar> consente di scorrere il contenuto in senso orizzontale.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="3e1ae-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="3e1ae-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="3e1ae-116">Il <xref:System.Windows.Controls.Primitives.ScrollBar> consente di scorrere verticalmente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="3e1ae-117">Stati del controllo ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="3e1ae-117">ScrollViewer States</span></span>  
 <span data-ttu-id="3e1ae-118">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="3e1ae-119">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="3e1ae-119">VisualState Name</span></span>|<span data-ttu-id="3e1ae-120">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="3e1ae-120">VisualStateGroup Name</span></span>|<span data-ttu-id="3e1ae-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e1ae-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3e1ae-122">Valido</span><span class="sxs-lookup"><span data-stu-id="3e1ae-122">Valid</span></span>|<span data-ttu-id="3e1ae-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3e1ae-123">ValidationStates</span></span>|<span data-ttu-id="3e1ae-124">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3e1ae-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3e1ae-125">InvalidFocused</span></span>|<span data-ttu-id="3e1ae-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3e1ae-126">ValidationStates</span></span>|<span data-ttu-id="3e1ae-127">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3e1ae-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3e1ae-128">InvalidUnfocused</span></span>|<span data-ttu-id="3e1ae-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3e1ae-129">ValidationStates</span></span>|<span data-ttu-id="3e1ae-130">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="3e1ae-131">Esempio di ControlTemplate ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="3e1ae-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="3e1ae-132">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="3e1ae-133">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="3e1ae-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3e1ae-134">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="3e1ae-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e1ae-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e1ae-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3e1ae-136">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="3e1ae-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3e1ae-137">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="3e1ae-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3e1ae-138">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="3e1ae-138">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="3e1ae-139">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="3e1ae-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
