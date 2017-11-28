---
title: Stili e modelli di ScrollViewer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ac02896708744bc9b1c2d017da4e6f56ac32b53a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="b891a-102">Stili e modelli di ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="b891a-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="b891a-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="b891a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="b891a-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="b891a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b891a-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="b891a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="b891a-106">Parti del controllo ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="b891a-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="b891a-107">La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="b891a-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="b891a-108">Parte</span><span class="sxs-lookup"><span data-stu-id="b891a-108">Part</span></span>|<span data-ttu-id="b891a-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="b891a-109">Type</span></span>|<span data-ttu-id="b891a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b891a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b891a-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="b891a-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="b891a-112">Il segnaposto di contenuto di <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="b891a-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="b891a-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="b891a-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="b891a-114">Il <xref:System.Windows.Controls.Primitives.ScrollBar> consente di scorrere orizzontalmente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b891a-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="b891a-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="b891a-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="b891a-116">Il <xref:System.Windows.Controls.Primitives.ScrollBar> consente di scorrere verticalmente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b891a-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="b891a-117">Stati del controllo ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="b891a-117">ScrollViewer States</span></span>  
 <span data-ttu-id="b891a-118">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="b891a-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="b891a-119">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="b891a-119">VisualState Name</span></span>|<span data-ttu-id="b891a-120">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b891a-120">VisualStateGroup Name</span></span>|<span data-ttu-id="b891a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b891a-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b891a-122">Valido</span><span class="sxs-lookup"><span data-stu-id="b891a-122">Valid</span></span>|<span data-ttu-id="b891a-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b891a-123">ValidationStates</span></span>|<span data-ttu-id="b891a-124">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="b891a-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b891a-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b891a-125">InvalidFocused</span></span>|<span data-ttu-id="b891a-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b891a-126">ValidationStates</span></span>|<span data-ttu-id="b891a-127">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="b891a-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b891a-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b891a-128">InvalidUnfocused</span></span>|<span data-ttu-id="b891a-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b891a-129">ValidationStates</span></span>|<span data-ttu-id="b891a-130">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="b891a-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="b891a-131">Esempio di ControlTemplate del controllo ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="b891a-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="b891a-132">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="b891a-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="b891a-133">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="b891a-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b891a-134">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="b891a-134">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b891a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b891a-135">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="b891a-136">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="b891a-136">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="b891a-137">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="b891a-137">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="b891a-138">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="b891a-138">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="b891a-139">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b891a-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
