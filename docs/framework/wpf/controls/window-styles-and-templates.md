---
title: Stili e modelli di Window
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0415bfae8e1065759efaac1a779655444451fa24
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="96205-102">Stili e modelli di Window</span><span class="sxs-lookup"><span data-stu-id="96205-102">Window Styles and Templates</span></span>
<span data-ttu-id="96205-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Window> controllo.</span><span class="sxs-lookup"><span data-stu-id="96205-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="96205-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="96205-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="96205-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="96205-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="96205-106">Elementi di finestra</span><span class="sxs-lookup"><span data-stu-id="96205-106">Window Parts</span></span>  
 <span data-ttu-id="96205-107">Il <xref:System.Windows.Window> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="96205-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="96205-108">Stati della finestra</span><span class="sxs-lookup"><span data-stu-id="96205-108">Window States</span></span>  
 <span data-ttu-id="96205-109">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Window> controllo.</span><span class="sxs-lookup"><span data-stu-id="96205-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="96205-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="96205-110">VisualState Name</span></span>|<span data-ttu-id="96205-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="96205-111">VisualStateGroup Name</span></span>|<span data-ttu-id="96205-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96205-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="96205-113">Valido</span><span class="sxs-lookup"><span data-stu-id="96205-113">Valid</span></span>|<span data-ttu-id="96205-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="96205-114">ValidationStates</span></span>|<span data-ttu-id="96205-115">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="96205-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="96205-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="96205-116">InvalidFocused</span></span>|<span data-ttu-id="96205-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="96205-117">ValidationStates</span></span>|<span data-ttu-id="96205-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="96205-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="96205-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="96205-119">InvalidUnfocused</span></span>|<span data-ttu-id="96205-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="96205-120">ValidationStates</span></span>|<span data-ttu-id="96205-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="96205-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="96205-122">Esempio di ControlTemplate finestra</span><span class="sxs-lookup"><span data-stu-id="96205-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="96205-123">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Window> controllo.</span><span class="sxs-lookup"><span data-stu-id="96205-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="96205-124">Il <xref:System.Windows.Controls.ControlTemplate> utilizza uno o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="96205-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="96205-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="96205-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96205-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96205-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="96205-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="96205-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="96205-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="96205-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="96205-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="96205-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="96205-130">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="96205-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
