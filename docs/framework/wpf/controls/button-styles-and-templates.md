---
title: Stili e modelli di Button
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d783b3141463ca2c74ddd649848ea49e154415b6
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="01524-102">Stili e modelli di Button</span><span class="sxs-lookup"><span data-stu-id="01524-102">Button Styles and Templates</span></span>
<span data-ttu-id="01524-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="01524-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="01524-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="01524-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="01524-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="01524-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="01524-106">Parti del controllo Button</span><span class="sxs-lookup"><span data-stu-id="01524-106">Button Parts</span></span>  
 <span data-ttu-id="01524-107">Il <xref:System.Windows.Controls.Button> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="01524-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="01524-108">Stati dei pulsanti</span><span class="sxs-lookup"><span data-stu-id="01524-108">Button States</span></span>  
 <span data-ttu-id="01524-109">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="01524-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="01524-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="01524-110">VisualState Name</span></span>|<span data-ttu-id="01524-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="01524-111">VisualStateGroup Name</span></span>|<span data-ttu-id="01524-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01524-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="01524-113">Normale</span><span class="sxs-lookup"><span data-stu-id="01524-113">Normal</span></span>|<span data-ttu-id="01524-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="01524-114">CommonStates</span></span>|<span data-ttu-id="01524-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="01524-115">The default state.</span></span>|  
|<span data-ttu-id="01524-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="01524-116">MouseOver</span></span>|<span data-ttu-id="01524-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="01524-117">CommonStates</span></span>|<span data-ttu-id="01524-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="01524-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="01524-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="01524-119">Pressed</span></span>|<span data-ttu-id="01524-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="01524-120">CommonStates</span></span>|<span data-ttu-id="01524-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="01524-121">The control is pressed.</span></span>|  
|<span data-ttu-id="01524-122">Disabilitato</span><span class="sxs-lookup"><span data-stu-id="01524-122">Disabled</span></span>|<span data-ttu-id="01524-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="01524-123">CommonStates</span></span>|<span data-ttu-id="01524-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="01524-124">The control is disabled.</span></span>|  
|<span data-ttu-id="01524-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="01524-125">Focused</span></span>|<span data-ttu-id="01524-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="01524-126">FocusStates</span></span>|<span data-ttu-id="01524-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="01524-127">The control has focus.</span></span>|  
|<span data-ttu-id="01524-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="01524-128">Unfocused</span></span>|<span data-ttu-id="01524-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="01524-129">FocusStates</span></span>|<span data-ttu-id="01524-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="01524-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="01524-131">Valido</span><span class="sxs-lookup"><span data-stu-id="01524-131">Valid</span></span>|<span data-ttu-id="01524-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="01524-132">ValidationStates</span></span>|<span data-ttu-id="01524-133">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="01524-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="01524-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="01524-134">InvalidFocused</span></span>|<span data-ttu-id="01524-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="01524-135">ValidationStates</span></span>|<span data-ttu-id="01524-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="01524-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="01524-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="01524-137">InvalidUnfocused</span></span>|<span data-ttu-id="01524-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="01524-138">ValidationStates</span></span>|<span data-ttu-id="01524-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="01524-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="01524-140">Esempio di ControlTemplate del controllo Button</span><span class="sxs-lookup"><span data-stu-id="01524-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="01524-141">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="01524-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="01524-142">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="01524-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="01524-143">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="01524-143">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01524-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01524-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="01524-145">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="01524-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="01524-146">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="01524-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="01524-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="01524-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="01524-148">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="01524-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
