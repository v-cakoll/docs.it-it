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
ms.openlocfilehash: 217fa0ff7b8c34de817a269effbf64311bbea7f2
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="00dad-102">Stili e modelli di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="00dad-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="00dad-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="00dad-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="00dad-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="00dad-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="00dad-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="00dad-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="00dad-106">Parti di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="00dad-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="00dad-107">La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="00dad-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="00dad-108">Parte</span><span class="sxs-lookup"><span data-stu-id="00dad-108">Part</span></span>|<span data-ttu-id="00dad-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="00dad-109">Type</span></span>|<span data-ttu-id="00dad-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00dad-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="00dad-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="00dad-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="00dad-112">Il contenuto e l'area di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="00dad-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="00dad-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="00dad-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="00dad-114">La casella di ricerca, nella parte inferiore per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="00dad-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="00dad-115">Stati di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="00dad-115">DocumentViewer States</span></span>  
 <span data-ttu-id="00dad-116">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="00dad-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="00dad-117">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="00dad-117">VisualState Name</span></span>|<span data-ttu-id="00dad-118">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="00dad-118">VisualStateGroup Name</span></span>|<span data-ttu-id="00dad-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00dad-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="00dad-120">Valido</span><span class="sxs-lookup"><span data-stu-id="00dad-120">Valid</span></span>|<span data-ttu-id="00dad-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="00dad-121">ValidationStates</span></span>|<span data-ttu-id="00dad-122">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="00dad-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="00dad-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="00dad-123">InvalidFocused</span></span>|<span data-ttu-id="00dad-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="00dad-124">ValidationStates</span></span>|<span data-ttu-id="00dad-125">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="00dad-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="00dad-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="00dad-126">InvalidUnfocused</span></span>|<span data-ttu-id="00dad-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="00dad-127">ValidationStates</span></span>|<span data-ttu-id="00dad-128">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="00dad-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="00dad-129">Esempio di ControlTemplate DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="00dad-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="00dad-130">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="00dad-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="00dad-131">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="00dad-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="00dad-132">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="00dad-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00dad-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00dad-133">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="00dad-134">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="00dad-134">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="00dad-135">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="00dad-135">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="00dad-136">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="00dad-136">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="00dad-137">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="00dad-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
