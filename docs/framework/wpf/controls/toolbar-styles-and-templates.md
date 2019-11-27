---
title: Stili e modelli di ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: a984311234386cb205d5db35f18a743ca535ff05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283662"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="790ef-102">Stili e modelli di ToolBar</span><span class="sxs-lookup"><span data-stu-id="790ef-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="790ef-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="790ef-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="790ef-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="790ef-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="790ef-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="790ef-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="790ef-106">Parti della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="790ef-106">ToolBar Parts</span></span>  
 <span data-ttu-id="790ef-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="790ef-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="790ef-108">Parte</span><span class="sxs-lookup"><span data-stu-id="790ef-108">Part</span></span>|<span data-ttu-id="790ef-109">Type</span><span class="sxs-lookup"><span data-stu-id="790ef-109">Type</span></span>|<span data-ttu-id="790ef-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="790ef-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="790ef-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="790ef-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="790ef-112">Oggetto che contiene i controlli nella <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="790ef-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="790ef-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="790ef-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="790ef-114">Oggetto che contiene i controlli che si trovano nell'area di overflow del <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="790ef-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="790ef-115">Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per una <xref:System.Windows.Controls.ToolBar>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di una <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="790ef-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="790ef-116">Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento del <xref:System.Windows.Controls.ToolBar>. il <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo.</span><span class="sxs-lookup"><span data-stu-id="790ef-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="790ef-117">Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> il nome `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="790ef-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="790ef-118">Stati della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="790ef-118">ToolBar States</span></span>  
 <span data-ttu-id="790ef-119">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="790ef-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="790ef-120">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="790ef-120">VisualState Name</span></span>|<span data-ttu-id="790ef-121">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="790ef-121">VisualStateGroup Name</span></span>|<span data-ttu-id="790ef-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="790ef-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="790ef-123">Valido</span><span class="sxs-lookup"><span data-stu-id="790ef-123">Valid</span></span>|<span data-ttu-id="790ef-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="790ef-124">ValidationStates</span></span>|<span data-ttu-id="790ef-125">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="790ef-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="790ef-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="790ef-126">InvalidFocused</span></span>|<span data-ttu-id="790ef-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="790ef-127">ValidationStates</span></span>|<span data-ttu-id="790ef-128">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="790ef-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="790ef-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="790ef-129">InvalidUnfocused</span></span>|<span data-ttu-id="790ef-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="790ef-130">ValidationStates</span></span>|<span data-ttu-id="790ef-131">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="790ef-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="790ef-132">Esempio di ControlTemplate della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="790ef-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="790ef-133">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="790ef-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="790ef-134">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="790ef-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="790ef-135">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="790ef-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790ef-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="790ef-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="790ef-137">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="790ef-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="790ef-138">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="790ef-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="790ef-139">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="790ef-139">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="790ef-140">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="790ef-140">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
