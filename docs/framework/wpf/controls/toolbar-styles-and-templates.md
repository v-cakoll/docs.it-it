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
ms.openlocfilehash: 022581c6ef154874e563513a719fc8590a13b30a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655686"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="a6598-102">Stili e modelli di ToolBar</span><span class="sxs-lookup"><span data-stu-id="a6598-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="a6598-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="a6598-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="a6598-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="a6598-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a6598-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a6598-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="a6598-106">Parti della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="a6598-106">ToolBar Parts</span></span>  
 <span data-ttu-id="a6598-107">La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="a6598-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="a6598-108">Parte</span><span class="sxs-lookup"><span data-stu-id="a6598-108">Part</span></span>|<span data-ttu-id="a6598-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="a6598-109">Type</span></span>|<span data-ttu-id="a6598-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6598-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a6598-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="a6598-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="a6598-112">L'oggetto che contiene i controlli di <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="a6598-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="a6598-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="a6598-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="a6598-114">Oggetto che contiene i controlli nell'area di overflow del <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="a6598-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="a6598-115">Quando si crea una <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.ToolBar>, il modello potrebbe contenere un' <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="a6598-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="a6598-116">(Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.ToolBar>; i <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).</span><span class="sxs-lookup"><span data-stu-id="a6598-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="a6598-117">Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario dare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="a6598-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="a6598-118">Gli stati della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="a6598-118">ToolBar States</span></span>  
 <span data-ttu-id="a6598-119">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="a6598-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="a6598-120">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="a6598-120">VisualState Name</span></span>|<span data-ttu-id="a6598-121">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a6598-121">VisualStateGroup Name</span></span>|<span data-ttu-id="a6598-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6598-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a6598-123">Valido</span><span class="sxs-lookup"><span data-stu-id="a6598-123">Valid</span></span>|<span data-ttu-id="a6598-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a6598-124">ValidationStates</span></span>|<span data-ttu-id="a6598-125">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="a6598-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a6598-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a6598-126">InvalidFocused</span></span>|<span data-ttu-id="a6598-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a6598-127">ValidationStates</span></span>|<span data-ttu-id="a6598-128">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a6598-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a6598-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a6598-129">InvalidUnfocused</span></span>|<span data-ttu-id="a6598-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a6598-130">ValidationStates</span></span>|<span data-ttu-id="a6598-131">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="a6598-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="a6598-132">Esempio di ControlTemplate della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="a6598-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="a6598-133">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="a6598-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="a6598-134">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="a6598-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a6598-135">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a6598-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6598-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6598-136">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a6598-137">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="a6598-137">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="a6598-138">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="a6598-138">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="a6598-139">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="a6598-139">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="a6598-140">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a6598-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
