---
title: Stili e modelli di Window
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 01233c5d0179e1a6f9bed651cd1f18058bfac168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283604"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="3a133-102">Stili e modelli di Window</span><span class="sxs-lookup"><span data-stu-id="3a133-102">Window Styles and Templates</span></span>
<span data-ttu-id="3a133-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="3a133-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="3a133-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="3a133-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3a133-105">Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="3a133-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="3a133-106">Parti della finestra</span><span class="sxs-lookup"><span data-stu-id="3a133-106">Window Parts</span></span>  
 <span data-ttu-id="3a133-107">Il controllo <xref:System.Windows.Window> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="3a133-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="3a133-108">Stati della finestra</span><span class="sxs-lookup"><span data-stu-id="3a133-108">Window States</span></span>  
 <span data-ttu-id="3a133-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="3a133-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="3a133-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="3a133-110">VisualState Name</span></span>|<span data-ttu-id="3a133-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="3a133-111">VisualStateGroup Name</span></span>|<span data-ttu-id="3a133-112">description</span><span class="sxs-lookup"><span data-stu-id="3a133-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3a133-113">Valido</span><span class="sxs-lookup"><span data-stu-id="3a133-113">Valid</span></span>|<span data-ttu-id="3a133-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3a133-114">ValidationStates</span></span>|<span data-ttu-id="3a133-115">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="3a133-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3a133-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3a133-116">InvalidFocused</span></span>|<span data-ttu-id="3a133-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3a133-117">ValidationStates</span></span>|<span data-ttu-id="3a133-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="3a133-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3a133-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3a133-119">InvalidUnfocused</span></span>|<span data-ttu-id="3a133-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3a133-120">ValidationStates</span></span>|<span data-ttu-id="3a133-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="3a133-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="3a133-122">Esempio di ControlTemplate finestra</span><span class="sxs-lookup"><span data-stu-id="3a133-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="3a133-123">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="3a133-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="3a133-124">Il <xref:System.Windows.Controls.ControlTemplate> utilizza una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="3a133-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3a133-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="3a133-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a133-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a133-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3a133-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="3a133-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3a133-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="3a133-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3a133-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="3a133-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="3a133-130">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="3a133-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
