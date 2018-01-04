---
title: Stili e modelli di GroupBox
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99150de10fcbd45d3617621a916793ad5cfe72db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="b5616-102">Stili e modelli di GroupBox</span><span class="sxs-lookup"><span data-stu-id="b5616-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="b5616-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="b5616-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="b5616-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="b5616-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b5616-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="b5616-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="b5616-106">Parti di GroupBox</span><span class="sxs-lookup"><span data-stu-id="b5616-106">GroupBox Parts</span></span>  
 <span data-ttu-id="b5616-107">Il <xref:System.Windows.Controls.GroupBox> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="b5616-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="b5616-108">Stati di GroupBox</span><span class="sxs-lookup"><span data-stu-id="b5616-108">GroupBox States</span></span>  
 <span data-ttu-id="b5616-109">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="b5616-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="b5616-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="b5616-110">VisualState Name</span></span>|<span data-ttu-id="b5616-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b5616-111">VisualStateGroup Name</span></span>|<span data-ttu-id="b5616-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5616-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b5616-113">Valido</span><span class="sxs-lookup"><span data-stu-id="b5616-113">Valid</span></span>|<span data-ttu-id="b5616-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b5616-114">ValidationStates</span></span>|<span data-ttu-id="b5616-115">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="b5616-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b5616-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b5616-116">InvalidFocused</span></span>|<span data-ttu-id="b5616-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b5616-117">ValidationStates</span></span>|<span data-ttu-id="b5616-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="b5616-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b5616-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b5616-119">InvalidUnfocused</span></span>|<span data-ttu-id="b5616-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b5616-120">ValidationStates</span></span>|<span data-ttu-id="b5616-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="b5616-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="b5616-122">Esempio di ControlTemplate del controllo GroupBox</span><span class="sxs-lookup"><span data-stu-id="b5616-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="b5616-123">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="b5616-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="b5616-124">Il <xref:System.Windows.Controls.ControlTemplate> utilizza uno o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="b5616-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b5616-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="b5616-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5616-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5616-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="b5616-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="b5616-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="b5616-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="b5616-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="b5616-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="b5616-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="b5616-130">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b5616-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
