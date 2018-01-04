---
title: Stili e modelli di NavigationWindow
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b638d43fb59506572e2ccddd9da7188639bff279
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="87e1c-102">Stili e modelli di NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="87e1c-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="87e1c-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Navigation.NavigationWindow> controllo.</span><span class="sxs-lookup"><span data-stu-id="87e1c-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="87e1c-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="87e1c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="87e1c-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="87e1c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="87e1c-106">Parti di NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="87e1c-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="87e1c-107">La tabella seguente elenca le parti denominate la <xref:System.Windows.Navigation.NavigationWindow> controllo.</span><span class="sxs-lookup"><span data-stu-id="87e1c-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="87e1c-108">Parte</span><span class="sxs-lookup"><span data-stu-id="87e1c-108">Part</span></span>|<span data-ttu-id="87e1c-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="87e1c-109">Type</span></span>|<span data-ttu-id="87e1c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87e1c-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="87e1c-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="87e1c-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="87e1c-112">L'area per il contenuto.</span><span class="sxs-lookup"><span data-stu-id="87e1c-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="87e1c-113">Stati di NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="87e1c-113">NavigationWindow States</span></span>  
 <span data-ttu-id="87e1c-114">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Navigation.NavigationWindow> controllo.</span><span class="sxs-lookup"><span data-stu-id="87e1c-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="87e1c-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="87e1c-115">VisualState Name</span></span>|<span data-ttu-id="87e1c-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="87e1c-116">VisualStateGroup Name</span></span>|<span data-ttu-id="87e1c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87e1c-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="87e1c-118">Valido</span><span class="sxs-lookup"><span data-stu-id="87e1c-118">Valid</span></span>|<span data-ttu-id="87e1c-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="87e1c-119">ValidationStates</span></span>|<span data-ttu-id="87e1c-120">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="87e1c-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="87e1c-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="87e1c-121">InvalidFocused</span></span>|<span data-ttu-id="87e1c-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="87e1c-122">ValidationStates</span></span>|<span data-ttu-id="87e1c-123">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="87e1c-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="87e1c-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="87e1c-124">InvalidUnfocused</span></span>|<span data-ttu-id="87e1c-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="87e1c-125">ValidationStates</span></span>|<span data-ttu-id="87e1c-126">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="87e1c-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="87e1c-127">Esempio di ControlTemplate NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="87e1c-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="87e1c-128">Anche se in questo esempio contiene tutti gli elementi definiti nel <xref:System.Windows.Controls.ControlTemplate> di un <xref:System.Windows.Navigation.NavigationWindow> per impostazione predefinita, i valori specifici devono essere considerati come esempi.</span><span class="sxs-lookup"><span data-stu-id="87e1c-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="87e1c-129">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="87e1c-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="87e1c-130">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="87e1c-130">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e1c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87e1c-131">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="87e1c-132">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="87e1c-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="87e1c-133">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="87e1c-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="87e1c-134">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="87e1c-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="87e1c-135">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="87e1c-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
