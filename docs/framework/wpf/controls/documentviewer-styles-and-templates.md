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
ms.openlocfilehash: 7ac68e8666a0de5cf683e3c4186d7805168dadb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581006"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="20747-102">Stili e modelli di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="20747-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="20747-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="20747-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="20747-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="20747-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="20747-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="20747-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="20747-106">Parti di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="20747-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="20747-107">La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="20747-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="20747-108">Parte</span><span class="sxs-lookup"><span data-stu-id="20747-108">Part</span></span>|<span data-ttu-id="20747-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="20747-109">Type</span></span>|<span data-ttu-id="20747-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20747-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="20747-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="20747-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="20747-112">Il contenuto e l'area di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="20747-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="20747-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="20747-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="20747-114">Casella di ricerca nella parte inferiore per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="20747-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="20747-115">Stati di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="20747-115">DocumentViewer States</span></span>  
 <span data-ttu-id="20747-116">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="20747-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="20747-117">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="20747-117">VisualState Name</span></span>|<span data-ttu-id="20747-118">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="20747-118">VisualStateGroup Name</span></span>|<span data-ttu-id="20747-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20747-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="20747-120">Valido</span><span class="sxs-lookup"><span data-stu-id="20747-120">Valid</span></span>|<span data-ttu-id="20747-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="20747-121">ValidationStates</span></span>|<span data-ttu-id="20747-122">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="20747-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="20747-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="20747-123">InvalidFocused</span></span>|<span data-ttu-id="20747-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="20747-124">ValidationStates</span></span>|<span data-ttu-id="20747-125">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="20747-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="20747-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="20747-126">InvalidUnfocused</span></span>|<span data-ttu-id="20747-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="20747-127">ValidationStates</span></span>|<span data-ttu-id="20747-128">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="20747-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="20747-129">Esempio di ControlTemplate DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="20747-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="20747-130">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="20747-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="20747-131">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="20747-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="20747-132">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="20747-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20747-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20747-133">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="20747-134">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="20747-134">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="20747-135">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="20747-135">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="20747-136">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="20747-136">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="20747-137">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="20747-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
