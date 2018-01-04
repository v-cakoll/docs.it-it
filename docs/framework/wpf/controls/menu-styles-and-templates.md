---
title: Stili e modelli di Menu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3b93de0089db58ed0a91aad4150432f8e7a1019
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="8481f-102">Stili e modelli di Menu</span><span class="sxs-lookup"><span data-stu-id="8481f-102">Menu Styles and Templates</span></span>
<span data-ttu-id="8481f-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.Menu> controllo.</span><span class="sxs-lookup"><span data-stu-id="8481f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="8481f-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="8481f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8481f-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="8481f-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="8481f-106">Parti di menu</span><span class="sxs-lookup"><span data-stu-id="8481f-106">Menu Parts</span></span>  
 <span data-ttu-id="8481f-107">Il <xref:System.Windows.Controls.Menu> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="8481f-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="8481f-108">Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.Menu>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="8481f-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="8481f-109">(Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.Menu>; <xref:System.Windows.Controls.ScrollViewer> Abilita lo scorrimento all'interno del controllo).</span><span class="sxs-lookup"><span data-stu-id="8481f-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="8481f-110">Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="8481f-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="8481f-111">Stati dei menu</span><span class="sxs-lookup"><span data-stu-id="8481f-111">Menu States</span></span>  
 <span data-ttu-id="8481f-112">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Menu> controllo.</span><span class="sxs-lookup"><span data-stu-id="8481f-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="8481f-113">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="8481f-113">VisualState Name</span></span>|<span data-ttu-id="8481f-114">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8481f-114">VisualStateGroup Name</span></span>|<span data-ttu-id="8481f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8481f-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8481f-116">Valido</span><span class="sxs-lookup"><span data-stu-id="8481f-116">Valid</span></span>|<span data-ttu-id="8481f-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8481f-117">ValidationStates</span></span>|<span data-ttu-id="8481f-118">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="8481f-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8481f-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8481f-119">InvalidFocused</span></span>|<span data-ttu-id="8481f-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8481f-120">ValidationStates</span></span>|<span data-ttu-id="8481f-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="8481f-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8481f-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8481f-122">InvalidUnfocused</span></span>|<span data-ttu-id="8481f-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8481f-123">ValidationStates</span></span>|<span data-ttu-id="8481f-124">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="8481f-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="8481f-125">Parti di MenuItem</span><span class="sxs-lookup"><span data-stu-id="8481f-125">MenuItem Parts</span></span>  
 <span data-ttu-id="8481f-126">La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.Menu> controllo.</span><span class="sxs-lookup"><span data-stu-id="8481f-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="8481f-127">Parte</span><span class="sxs-lookup"><span data-stu-id="8481f-127">Part</span></span>|<span data-ttu-id="8481f-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="8481f-128">Type</span></span>|<span data-ttu-id="8481f-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8481f-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8481f-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="8481f-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="8481f-131">L'area del sottomenu.</span><span class="sxs-lookup"><span data-stu-id="8481f-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="8481f-132">Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.MenuItem>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="8481f-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="8481f-133">(Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.MenuItem>; <xref:System.Windows.Controls.ScrollViewer> Abilita lo scorrimento all'interno del controllo).</span><span class="sxs-lookup"><span data-stu-id="8481f-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="8481f-134">Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="8481f-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="8481f-135">Stati di MenuItem</span><span class="sxs-lookup"><span data-stu-id="8481f-135">MenuItem States</span></span>  
 <span data-ttu-id="8481f-136">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.MenuItem> controllo.</span><span class="sxs-lookup"><span data-stu-id="8481f-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="8481f-137">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="8481f-137">VisualState Name</span></span>|<span data-ttu-id="8481f-138">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8481f-138">VisualStateGroup Name</span></span>|<span data-ttu-id="8481f-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8481f-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8481f-140">Valido</span><span class="sxs-lookup"><span data-stu-id="8481f-140">Valid</span></span>|<span data-ttu-id="8481f-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8481f-141">ValidationStates</span></span>|<span data-ttu-id="8481f-142">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="8481f-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8481f-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8481f-143">InvalidFocused</span></span>|<span data-ttu-id="8481f-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8481f-144">ValidationStates</span></span>|<span data-ttu-id="8481f-145">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="8481f-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8481f-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8481f-146">InvalidUnfocused</span></span>|<span data-ttu-id="8481f-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8481f-147">ValidationStates</span></span>|<span data-ttu-id="8481f-148">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="8481f-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="8481f-149">Menu e un esempio di ControlTemplate del controllo MenuItem</span><span class="sxs-lookup"><span data-stu-id="8481f-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="8481f-150">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Menu> controllo.</span><span class="sxs-lookup"><span data-stu-id="8481f-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="8481f-151">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.MenuItem> controllo.</span><span class="sxs-lookup"><span data-stu-id="8481f-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="8481f-152">L'esempio seguente definisce il `MenuScrollViewer`, che viene utilizzato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="8481f-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="8481f-153">Il <xref:System.Windows.Controls.ControlTemplate> negli esempi viene utilizzato uno o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="8481f-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8481f-154">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="8481f-154">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8481f-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8481f-155">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="8481f-156">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="8481f-156">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="8481f-157">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="8481f-157">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="8481f-158">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="8481f-158">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="8481f-159">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="8481f-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
