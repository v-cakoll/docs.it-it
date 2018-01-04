---
title: Stili e modelli di Frame
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1b69ffb0eff114252383e682d6c200d88503a80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="14ada-102">Stili e modelli di Frame</span><span class="sxs-lookup"><span data-stu-id="14ada-102">Frame Styles and Templates</span></span>
<span data-ttu-id="14ada-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="14ada-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="14ada-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="14ada-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="14ada-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="14ada-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="14ada-106">Parti di frame</span><span class="sxs-lookup"><span data-stu-id="14ada-106">Frame Parts</span></span>  
 <span data-ttu-id="14ada-107">La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="14ada-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="14ada-108">Parte</span><span class="sxs-lookup"><span data-stu-id="14ada-108">Part</span></span>|<span data-ttu-id="14ada-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="14ada-109">Type</span></span>|<span data-ttu-id="14ada-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14ada-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="14ada-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="14ada-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="14ada-112">L'area del contenuto.</span><span class="sxs-lookup"><span data-stu-id="14ada-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="14ada-113">Stati di frame</span><span class="sxs-lookup"><span data-stu-id="14ada-113">Frame States</span></span>  
 <span data-ttu-id="14ada-114">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="14ada-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="14ada-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="14ada-115">VisualState Name</span></span>|<span data-ttu-id="14ada-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="14ada-116">VisualStateGroup Name</span></span>|<span data-ttu-id="14ada-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14ada-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="14ada-118">Valido</span><span class="sxs-lookup"><span data-stu-id="14ada-118">Valid</span></span>|<span data-ttu-id="14ada-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14ada-119">ValidationStates</span></span>|<span data-ttu-id="14ada-120">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="14ada-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="14ada-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="14ada-121">InvalidFocused</span></span>|<span data-ttu-id="14ada-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14ada-122">ValidationStates</span></span>|<span data-ttu-id="14ada-123">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="14ada-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="14ada-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="14ada-124">InvalidUnfocused</span></span>|<span data-ttu-id="14ada-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14ada-125">ValidationStates</span></span>|<span data-ttu-id="14ada-126">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="14ada-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="14ada-127">Esempio di ControlTemplate frame</span><span class="sxs-lookup"><span data-stu-id="14ada-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="14ada-128">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="14ada-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="14ada-129">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="14ada-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="14ada-130">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="14ada-130">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14ada-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14ada-131">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="14ada-132">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="14ada-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="14ada-133">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="14ada-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="14ada-134">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="14ada-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="14ada-135">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="14ada-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
