---
title: Stili e modelli di Frame
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: fbe49ae98e0fe281500ae37d53a3d47ff1d0b03a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700269"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="342d9-102">Stili e modelli di Frame</span><span class="sxs-lookup"><span data-stu-id="342d9-102">Frame Styles and Templates</span></span>
<span data-ttu-id="342d9-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="342d9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="342d9-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="342d9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="342d9-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="342d9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="342d9-106">Parti di frame</span><span class="sxs-lookup"><span data-stu-id="342d9-106">Frame Parts</span></span>  
 <span data-ttu-id="342d9-107">La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="342d9-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="342d9-108">Parte</span><span class="sxs-lookup"><span data-stu-id="342d9-108">Part</span></span>|<span data-ttu-id="342d9-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="342d9-109">Type</span></span>|<span data-ttu-id="342d9-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="342d9-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="342d9-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="342d9-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="342d9-112">Area del contenuto.</span><span class="sxs-lookup"><span data-stu-id="342d9-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="342d9-113">Gli stati del frame</span><span class="sxs-lookup"><span data-stu-id="342d9-113">Frame States</span></span>  
 <span data-ttu-id="342d9-114">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="342d9-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="342d9-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="342d9-115">VisualState Name</span></span>|<span data-ttu-id="342d9-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="342d9-116">VisualStateGroup Name</span></span>|<span data-ttu-id="342d9-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="342d9-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="342d9-118">Valido</span><span class="sxs-lookup"><span data-stu-id="342d9-118">Valid</span></span>|<span data-ttu-id="342d9-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="342d9-119">ValidationStates</span></span>|<span data-ttu-id="342d9-120">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="342d9-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="342d9-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="342d9-121">InvalidFocused</span></span>|<span data-ttu-id="342d9-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="342d9-122">ValidationStates</span></span>|<span data-ttu-id="342d9-123">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="342d9-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="342d9-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="342d9-124">InvalidUnfocused</span></span>|<span data-ttu-id="342d9-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="342d9-125">ValidationStates</span></span>|<span data-ttu-id="342d9-126">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="342d9-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="342d9-127">Esempio di ControlTemplate frame</span><span class="sxs-lookup"><span data-stu-id="342d9-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="342d9-128">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="342d9-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="342d9-129">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="342d9-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="342d9-130">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="342d9-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="342d9-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="342d9-131">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="342d9-132">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="342d9-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="342d9-133">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="342d9-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="342d9-134">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="342d9-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="342d9-135">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="342d9-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
