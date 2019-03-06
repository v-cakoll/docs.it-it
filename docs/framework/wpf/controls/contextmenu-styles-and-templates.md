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
ms.openlocfilehash: be26156d74f3a3509bf150e5611512172f08a14e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369068"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="df8ce-102">Stili e modelli di ContextMenu</span><span class="sxs-lookup"><span data-stu-id="df8ce-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="df8ce-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.ContextMenu> controllo.</span><span class="sxs-lookup"><span data-stu-id="df8ce-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="df8ce-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="df8ce-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="df8ce-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="df8ce-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="df8ce-106">Parti del menu di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="df8ce-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="df8ce-107">Il <xref:System.Windows.Controls.ContextMenu> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="df8ce-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="df8ce-108">Quando si crea una <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.ContextMenu>, il modello potrebbe contenere un' <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="df8ce-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="df8ce-109">(Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.ContextMenu>; i <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).</span><span class="sxs-lookup"><span data-stu-id="df8ce-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="df8ce-110">Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario dare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="df8ce-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="df8ce-111">Stati di ContextMenu</span><span class="sxs-lookup"><span data-stu-id="df8ce-111">ContextMenu States</span></span>  
 <span data-ttu-id="df8ce-112">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.ContextMenu> controllo.</span><span class="sxs-lookup"><span data-stu-id="df8ce-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="df8ce-113">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="df8ce-113">VisualState Name</span></span>|<span data-ttu-id="df8ce-114">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="df8ce-114">VisualStateGroup Name</span></span>|<span data-ttu-id="df8ce-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df8ce-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="df8ce-116">Valido</span><span class="sxs-lookup"><span data-stu-id="df8ce-116">Valid</span></span>|<span data-ttu-id="df8ce-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="df8ce-117">ValidationStates</span></span>|<span data-ttu-id="df8ce-118">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="df8ce-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="df8ce-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="df8ce-119">InvalidFocused</span></span>|<span data-ttu-id="df8ce-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="df8ce-120">ValidationStates</span></span>|<span data-ttu-id="df8ce-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="df8ce-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="df8ce-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="df8ce-122">InvalidUnfocused</span></span>|<span data-ttu-id="df8ce-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="df8ce-123">ValidationStates</span></span>|<span data-ttu-id="df8ce-124">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="df8ce-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="df8ce-125">Esempio di ControlTemplate ContextMenu</span><span class="sxs-lookup"><span data-stu-id="df8ce-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="df8ce-126">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ContextMenu> controllo.</span><span class="sxs-lookup"><span data-stu-id="df8ce-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="df8ce-127">Il <xref:System.Windows.Controls.ControlTemplate> Usa le risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="df8ce-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="df8ce-128">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="df8ce-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df8ce-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df8ce-129">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="df8ce-130">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="df8ce-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="df8ce-131">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="df8ce-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="df8ce-132">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="df8ce-132">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="df8ce-133">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="df8ce-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
