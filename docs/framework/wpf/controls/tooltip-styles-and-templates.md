---
title: Stili e modelli di ToolTip
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
ms.openlocfilehash: 24def466509c12eb69307de139e83dd5a1ed5ce4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790676"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="d2882-102">Stili e modelli di ToolTip</span><span class="sxs-lookup"><span data-stu-id="d2882-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="d2882-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.ToolTip> controllo.</span><span class="sxs-lookup"><span data-stu-id="d2882-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="d2882-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="d2882-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d2882-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d2882-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="d2882-106">Parti della descrizione comando</span><span class="sxs-lookup"><span data-stu-id="d2882-106">ToolTip Parts</span></span>  
 <span data-ttu-id="d2882-107">Il <xref:System.Windows.Controls.ToolTip> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="d2882-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="d2882-108">Stati del controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="d2882-108">ToolTip States</span></span>  
 <span data-ttu-id="d2882-109">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.ToolTip> controllo.</span><span class="sxs-lookup"><span data-stu-id="d2882-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="d2882-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="d2882-110">VisualState Name</span></span>|<span data-ttu-id="d2882-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d2882-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d2882-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2882-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d2882-113">Chiuso</span><span class="sxs-lookup"><span data-stu-id="d2882-113">Closed</span></span>|<span data-ttu-id="d2882-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="d2882-114">OpenStates</span></span>|<span data-ttu-id="d2882-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="d2882-115">The default state.</span></span>|  
|<span data-ttu-id="d2882-116">Apri</span><span class="sxs-lookup"><span data-stu-id="d2882-116">Open</span></span>|<span data-ttu-id="d2882-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="d2882-117">OpenStates</span></span>|<span data-ttu-id="d2882-118">Il <xref:System.Windows.Controls.ToolTip> è visibile.</span><span class="sxs-lookup"><span data-stu-id="d2882-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="d2882-119">Valido</span><span class="sxs-lookup"><span data-stu-id="d2882-119">Valid</span></span>|<span data-ttu-id="d2882-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d2882-120">ValidationStates</span></span>|<span data-ttu-id="d2882-121">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="d2882-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d2882-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d2882-122">InvalidFocused</span></span>|<span data-ttu-id="d2882-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d2882-123">ValidationStates</span></span>|<span data-ttu-id="d2882-124">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="d2882-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d2882-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d2882-125">InvalidUnfocused</span></span>|<span data-ttu-id="d2882-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d2882-126">ValidationStates</span></span>|<span data-ttu-id="d2882-127">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="d2882-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="d2882-128">Esempio di ControlTemplate della descrizione comando</span><span class="sxs-lookup"><span data-stu-id="d2882-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="d2882-129">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ToolTip> controllo.</span><span class="sxs-lookup"><span data-stu-id="d2882-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="d2882-130">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="d2882-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d2882-131">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d2882-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2882-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2882-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d2882-133">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="d2882-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d2882-134">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="d2882-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d2882-135">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="d2882-135">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="d2882-136">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d2882-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
