---
title: Stili e modelli di ToolTip
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec946e7982983519a317ee1936e8584eef63479c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="0571e-102">Stili e modelli di ToolTip</span><span class="sxs-lookup"><span data-stu-id="0571e-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="0571e-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.ToolTip> controllo.</span><span class="sxs-lookup"><span data-stu-id="0571e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="0571e-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="0571e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0571e-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="0571e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="0571e-106">Parti della descrizione comando</span><span class="sxs-lookup"><span data-stu-id="0571e-106">ToolTip Parts</span></span>  
 <span data-ttu-id="0571e-107">Il <xref:System.Windows.Controls.ToolTip> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="0571e-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="0571e-108">Stati del controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="0571e-108">ToolTip States</span></span>  
 <span data-ttu-id="0571e-109">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.ToolTip> controllo.</span><span class="sxs-lookup"><span data-stu-id="0571e-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="0571e-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="0571e-110">VisualState Name</span></span>|<span data-ttu-id="0571e-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="0571e-111">VisualStateGroup Name</span></span>|<span data-ttu-id="0571e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0571e-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0571e-113">Chiuso</span><span class="sxs-lookup"><span data-stu-id="0571e-113">Closed</span></span>|<span data-ttu-id="0571e-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="0571e-114">OpenStates</span></span>|<span data-ttu-id="0571e-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="0571e-115">The default state.</span></span>|  
|<span data-ttu-id="0571e-116">Apri</span><span class="sxs-lookup"><span data-stu-id="0571e-116">Open</span></span>|<span data-ttu-id="0571e-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="0571e-117">OpenStates</span></span>|<span data-ttu-id="0571e-118">Il <xref:System.Windows.Controls.ToolTip> è visibile.</span><span class="sxs-lookup"><span data-stu-id="0571e-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="0571e-119">Valido</span><span class="sxs-lookup"><span data-stu-id="0571e-119">Valid</span></span>|<span data-ttu-id="0571e-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0571e-120">ValidationStates</span></span>|<span data-ttu-id="0571e-121">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="0571e-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0571e-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0571e-122">InvalidFocused</span></span>|<span data-ttu-id="0571e-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0571e-123">ValidationStates</span></span>|<span data-ttu-id="0571e-124">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0571e-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0571e-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0571e-125">InvalidUnfocused</span></span>|<span data-ttu-id="0571e-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0571e-126">ValidationStates</span></span>|<span data-ttu-id="0571e-127">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="0571e-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="0571e-128">Esempio di ControlTemplate del controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="0571e-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="0571e-129">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ToolTip> controllo.</span><span class="sxs-lookup"><span data-stu-id="0571e-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="0571e-130">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="0571e-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0571e-131">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="0571e-131">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0571e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0571e-132">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="0571e-133">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="0571e-133">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="0571e-134">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="0571e-134">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="0571e-135">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="0571e-135">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="0571e-136">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="0571e-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
