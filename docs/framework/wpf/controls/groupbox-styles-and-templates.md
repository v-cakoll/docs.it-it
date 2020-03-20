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
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187484"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="02d60-102">Stili e modelli di GroupBox</span><span class="sxs-lookup"><span data-stu-id="02d60-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="02d60-103">In questo argomento vengono descritti <xref:System.Windows.Controls.GroupBox> gli stili e i modelli per il controllo.</span><span class="sxs-lookup"><span data-stu-id="02d60-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="02d60-104">È possibile modificare <xref:System.Windows.Controls.ControlTemplate> l'impostazione predefinita per conferire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="02d60-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="02d60-105">Per ulteriori informazioni, vedere [Creare un modello per un controllo.](../../../desktop-wpf/themes/how-to-create-apply-template.md)</span><span class="sxs-lookup"><span data-stu-id="02d60-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a><span data-ttu-id="02d60-106">Parti di GroupBox</span><span class="sxs-lookup"><span data-stu-id="02d60-106">GroupBox Parts</span></span>  
 <span data-ttu-id="02d60-107">Il <xref:System.Windows.Controls.GroupBox> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="02d60-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a><span data-ttu-id="02d60-108">Stati di GroupBox</span><span class="sxs-lookup"><span data-stu-id="02d60-108">GroupBox States</span></span>  
 <span data-ttu-id="02d60-109">Nella tabella seguente sono elencati gli stati di visualizzazione per il <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="02d60-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="02d60-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="02d60-110">VisualState Name</span></span>|<span data-ttu-id="02d60-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="02d60-111">VisualStateGroup Name</span></span>|<span data-ttu-id="02d60-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02d60-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="02d60-113">Valido</span><span class="sxs-lookup"><span data-stu-id="02d60-113">Valid</span></span>|<span data-ttu-id="02d60-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02d60-114">ValidationStates</span></span>|<span data-ttu-id="02d60-115">Il controllo <xref:System.Windows.Controls.Validation> utilizza la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> classe e `false`la proprietà associata è .</span><span class="sxs-lookup"><span data-stu-id="02d60-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="02d60-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="02d60-116">InvalidFocused</span></span>|<span data-ttu-id="02d60-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02d60-117">ValidationStates</span></span>|<span data-ttu-id="02d60-118">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata ha `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="02d60-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="02d60-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="02d60-119">InvalidUnfocused</span></span>|<span data-ttu-id="02d60-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02d60-120">ValidationStates</span></span>|<span data-ttu-id="02d60-121">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata ha `true` il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="02d60-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="02d60-122">Esempio di controllo GroupBoxGroupBox ControlTemplate Example</span><span class="sxs-lookup"><span data-stu-id="02d60-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="02d60-123">Nell'esempio seguente viene <xref:System.Windows.Controls.ControlTemplate> illustrato <xref:System.Windows.Controls.GroupBox> come definire un per il controllo.</span><span class="sxs-lookup"><span data-stu-id="02d60-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="02d60-124">Utilizza <xref:System.Windows.Controls.ControlTemplate> una o più delle risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="02d60-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="02d60-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="02d60-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d60-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02d60-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="02d60-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="02d60-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="02d60-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="02d60-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="02d60-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="02d60-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="02d60-130">Creare un modello per un controlloCreate a template for a control</span><span class="sxs-lookup"><span data-stu-id="02d60-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
