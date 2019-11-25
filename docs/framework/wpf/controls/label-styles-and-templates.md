---
title: Stili e modelli di Label
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: 35fcd9c15bf44d15a08c16d58847698c5ec6e574
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283497"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="fee6b-102">Stili e modelli di Label</span><span class="sxs-lookup"><span data-stu-id="fee6b-102">Label Styles and Templates</span></span>
<span data-ttu-id="fee6b-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="fee6b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="fee6b-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="fee6b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fee6b-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="fee6b-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="fee6b-106">Parti etichetta</span><span class="sxs-lookup"><span data-stu-id="fee6b-106">Label Parts</span></span>  
 <span data-ttu-id="fee6b-107">Il controllo <xref:System.Windows.Controls.Label> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="fee6b-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="fee6b-108">Stati etichetta</span><span class="sxs-lookup"><span data-stu-id="fee6b-108">Label States</span></span>  
 <span data-ttu-id="fee6b-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="fee6b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="fee6b-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="fee6b-110">VisualState Name</span></span>|<span data-ttu-id="fee6b-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="fee6b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="fee6b-112">description</span><span class="sxs-lookup"><span data-stu-id="fee6b-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fee6b-113">Valido</span><span class="sxs-lookup"><span data-stu-id="fee6b-113">Valid</span></span>|<span data-ttu-id="fee6b-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fee6b-114">ValidationStates</span></span>|<span data-ttu-id="fee6b-115">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="fee6b-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fee6b-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fee6b-116">InvalidFocused</span></span>|<span data-ttu-id="fee6b-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fee6b-117">ValidationStates</span></span>|<span data-ttu-id="fee6b-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="fee6b-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fee6b-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fee6b-119">InvalidUnfocused</span></span>|<span data-ttu-id="fee6b-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fee6b-120">ValidationStates</span></span>|<span data-ttu-id="fee6b-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="fee6b-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="fee6b-122">Esempio di ControlTemplate label</span><span class="sxs-lookup"><span data-stu-id="fee6b-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="fee6b-123">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="fee6b-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="fee6b-124">Il <xref:System.Windows.Controls.ControlTemplate> utilizza una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="fee6b-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fee6b-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="fee6b-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee6b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fee6b-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fee6b-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="fee6b-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fee6b-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="fee6b-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fee6b-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="fee6b-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="fee6b-130">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="fee6b-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
