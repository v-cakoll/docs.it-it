---
title: Stili e modelli di GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 5ef8e4b44bc2b6072fa730f33c10191b64954f7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911261"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="43023-102">Stili e modelli di GroupBox</span><span class="sxs-lookup"><span data-stu-id="43023-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="43023-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="43023-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="43023-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="43023-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="43023-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="43023-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="43023-106">Parti controllo GroupBox</span><span class="sxs-lookup"><span data-stu-id="43023-106">GroupBox Parts</span></span>  
 <span data-ttu-id="43023-107">Il <xref:System.Windows.Controls.GroupBox> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="43023-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="43023-108">Stati di GroupBox</span><span class="sxs-lookup"><span data-stu-id="43023-108">GroupBox States</span></span>  
 <span data-ttu-id="43023-109">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="43023-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="43023-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="43023-110">VisualState Name</span></span>|<span data-ttu-id="43023-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="43023-111">VisualStateGroup Name</span></span>|<span data-ttu-id="43023-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43023-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="43023-113">Valido</span><span class="sxs-lookup"><span data-stu-id="43023-113">Valid</span></span>|<span data-ttu-id="43023-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="43023-114">ValidationStates</span></span>|<span data-ttu-id="43023-115">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="43023-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="43023-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="43023-116">InvalidFocused</span></span>|<span data-ttu-id="43023-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="43023-117">ValidationStates</span></span>|<span data-ttu-id="43023-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="43023-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="43023-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="43023-119">InvalidUnfocused</span></span>|<span data-ttu-id="43023-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="43023-120">ValidationStates</span></span>|<span data-ttu-id="43023-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="43023-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="43023-122">Esempio di ControlTemplate GroupBox</span><span class="sxs-lookup"><span data-stu-id="43023-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="43023-123">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="43023-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="43023-124">Il <xref:System.Windows.Controls.ControlTemplate> utilizza uno o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="43023-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="43023-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="43023-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43023-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43023-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="43023-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="43023-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="43023-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="43023-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="43023-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="43023-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="43023-130">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="43023-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
