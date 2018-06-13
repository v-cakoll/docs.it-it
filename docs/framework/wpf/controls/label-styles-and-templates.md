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
ms.openlocfilehash: 9d2f5e4d886d8fc46ecb14dd4f1bda67debdae97
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457644"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="e8250-102">Stili e modelli di Label</span><span class="sxs-lookup"><span data-stu-id="e8250-102">Label Styles and Templates</span></span>
<span data-ttu-id="e8250-103">In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.Label> controllo.</span><span class="sxs-lookup"><span data-stu-id="e8250-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="e8250-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="e8250-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e8250-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="e8250-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="e8250-106">Parti di etichetta</span><span class="sxs-lookup"><span data-stu-id="e8250-106">Label Parts</span></span>  
 <span data-ttu-id="e8250-107">Il <xref:System.Windows.Controls.Label> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="e8250-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="e8250-108">Stati di etichetta</span><span class="sxs-lookup"><span data-stu-id="e8250-108">Label States</span></span>  
 <span data-ttu-id="e8250-109">Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Label> controllo.</span><span class="sxs-lookup"><span data-stu-id="e8250-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="e8250-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="e8250-110">VisualState Name</span></span>|<span data-ttu-id="e8250-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e8250-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e8250-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8250-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e8250-113">Valido</span><span class="sxs-lookup"><span data-stu-id="e8250-113">Valid</span></span>|<span data-ttu-id="e8250-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8250-114">ValidationStates</span></span>|<span data-ttu-id="e8250-115">Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="e8250-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e8250-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e8250-116">InvalidFocused</span></span>|<span data-ttu-id="e8250-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8250-117">ValidationStates</span></span>|<span data-ttu-id="e8250-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="e8250-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e8250-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e8250-119">InvalidUnfocused</span></span>|<span data-ttu-id="e8250-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8250-120">ValidationStates</span></span>|<span data-ttu-id="e8250-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="e8250-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="e8250-122">Esempio di ControlTemplate etichetta</span><span class="sxs-lookup"><span data-stu-id="e8250-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="e8250-123">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Label> controllo.</span><span class="sxs-lookup"><span data-stu-id="e8250-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="e8250-124">Il <xref:System.Windows.Controls.ControlTemplate> utilizza uno o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="e8250-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e8250-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e8250-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8250-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8250-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="e8250-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="e8250-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="e8250-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="e8250-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="e8250-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="e8250-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="e8250-130">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e8250-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
