---
title: Stili e modelli di ContextMenu
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: fa192e20ea84e96c9f85ff84e16c63b7f56c8a98
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283548"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="c5271-102">Stili e modelli di ContextMenu</span><span class="sxs-lookup"><span data-stu-id="c5271-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="c5271-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="c5271-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="c5271-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="c5271-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c5271-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="c5271-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="c5271-106">Parti ContextMenu</span><span class="sxs-lookup"><span data-stu-id="c5271-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="c5271-107">Il controllo <xref:System.Windows.Controls.ContextMenu> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="c5271-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="c5271-108">Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per una <xref:System.Windows.Controls.ContextMenu>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di una <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="c5271-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="c5271-109">Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento del <xref:System.Windows.Controls.ContextMenu>. il <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo.</span><span class="sxs-lookup"><span data-stu-id="c5271-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="c5271-110">Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> il nome `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="c5271-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="c5271-111">Stati ContextMenu</span><span class="sxs-lookup"><span data-stu-id="c5271-111">ContextMenu States</span></span>  
 <span data-ttu-id="c5271-112">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="c5271-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="c5271-113">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="c5271-113">VisualState Name</span></span>|<span data-ttu-id="c5271-114">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="c5271-114">VisualStateGroup Name</span></span>|<span data-ttu-id="c5271-115">description</span><span class="sxs-lookup"><span data-stu-id="c5271-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c5271-116">Valido</span><span class="sxs-lookup"><span data-stu-id="c5271-116">Valid</span></span>|<span data-ttu-id="c5271-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c5271-117">ValidationStates</span></span>|<span data-ttu-id="c5271-118">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="c5271-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="c5271-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c5271-119">InvalidFocused</span></span>|<span data-ttu-id="c5271-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c5271-120">ValidationStates</span></span>|<span data-ttu-id="c5271-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="c5271-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="c5271-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c5271-122">InvalidUnfocused</span></span>|<span data-ttu-id="c5271-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c5271-123">ValidationStates</span></span>|<span data-ttu-id="c5271-124">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="c5271-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="c5271-125">Esempio di ControlTemplate ContextMenu</span><span class="sxs-lookup"><span data-stu-id="c5271-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="c5271-126">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="c5271-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="c5271-127">Il <xref:System.Windows.Controls.ControlTemplate> utilizza le risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="c5271-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="c5271-128">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="c5271-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5271-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5271-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="c5271-130">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="c5271-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="c5271-131">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="c5271-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="c5271-132">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="c5271-132">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="c5271-133">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="c5271-133">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
