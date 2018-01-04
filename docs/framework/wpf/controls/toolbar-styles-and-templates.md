---
title: Stili e modelli di ToolBar
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d56858f3785a4d4d49a0781fbf4c19397a3bb375
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="574a7-102">Stili e modelli di ToolBar</span><span class="sxs-lookup"><span data-stu-id="574a7-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="574a7-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="574a7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="574a7-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="574a7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="574a7-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="574a7-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="574a7-106">Parti della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="574a7-106">ToolBar Parts</span></span>  
 <span data-ttu-id="574a7-107">La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="574a7-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="574a7-108">Parte</span><span class="sxs-lookup"><span data-stu-id="574a7-108">Part</span></span>|<span data-ttu-id="574a7-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="574a7-109">Type</span></span>|<span data-ttu-id="574a7-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="574a7-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="574a7-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="574a7-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="574a7-112">L'oggetto che contiene i controlli di <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="574a7-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="574a7-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="574a7-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="574a7-114">L'oggetto che contiene i controlli nell'area di riversamento del <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="574a7-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="574a7-115">Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.ToolBar>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="574a7-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="574a7-116">(Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.ToolBar>; <xref:System.Windows.Controls.ScrollViewer> Abilita lo scorrimento all'interno del controllo).</span><span class="sxs-lookup"><span data-stu-id="574a7-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="574a7-117">Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="574a7-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="574a7-118">Stati della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="574a7-118">ToolBar States</span></span>  
 <span data-ttu-id="574a7-119">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="574a7-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="574a7-120">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="574a7-120">VisualState Name</span></span>|<span data-ttu-id="574a7-121">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="574a7-121">VisualStateGroup Name</span></span>|<span data-ttu-id="574a7-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="574a7-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="574a7-123">Valido</span><span class="sxs-lookup"><span data-stu-id="574a7-123">Valid</span></span>|<span data-ttu-id="574a7-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="574a7-124">ValidationStates</span></span>|<span data-ttu-id="574a7-125">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="574a7-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="574a7-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="574a7-126">InvalidFocused</span></span>|<span data-ttu-id="574a7-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="574a7-127">ValidationStates</span></span>|<span data-ttu-id="574a7-128">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="574a7-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="574a7-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="574a7-129">InvalidUnfocused</span></span>|<span data-ttu-id="574a7-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="574a7-130">ValidationStates</span></span>|<span data-ttu-id="574a7-131">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="574a7-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="574a7-132">Esempio di ControlTemplate del controllo barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="574a7-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="574a7-133">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="574a7-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="574a7-134">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="574a7-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="574a7-135">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="574a7-135">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="574a7-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="574a7-136">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="574a7-137">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="574a7-137">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="574a7-138">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="574a7-138">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="574a7-139">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="574a7-139">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="574a7-140">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="574a7-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
