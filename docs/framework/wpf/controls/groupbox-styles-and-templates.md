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
ms.openlocfilehash: 0835c106ffbda86bca8e01bc61adebfc1ab0c2cb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459647"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="4f6d1-102">Stili e modelli di GroupBox</span><span class="sxs-lookup"><span data-stu-id="4f6d1-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="4f6d1-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="4f6d1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="4f6d1-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="4f6d1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4f6d1-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="4f6d1-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="4f6d1-106">Parti GroupBox</span><span class="sxs-lookup"><span data-stu-id="4f6d1-106">GroupBox Parts</span></span>  
 <span data-ttu-id="4f6d1-107">Il controllo <xref:System.Windows.Controls.GroupBox> non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="4f6d1-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="4f6d1-108">Stati di GroupBox</span><span class="sxs-lookup"><span data-stu-id="4f6d1-108">GroupBox States</span></span>  
 <span data-ttu-id="4f6d1-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="4f6d1-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="4f6d1-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="4f6d1-110">VisualState Name</span></span>|<span data-ttu-id="4f6d1-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="4f6d1-111">VisualStateGroup Name</span></span>|<span data-ttu-id="4f6d1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f6d1-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4f6d1-113">Valido</span><span class="sxs-lookup"><span data-stu-id="4f6d1-113">Valid</span></span>|<span data-ttu-id="4f6d1-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4f6d1-114">ValidationStates</span></span>|<span data-ttu-id="4f6d1-115">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="4f6d1-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4f6d1-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4f6d1-116">InvalidFocused</span></span>|<span data-ttu-id="4f6d1-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4f6d1-117">ValidationStates</span></span>|<span data-ttu-id="4f6d1-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="4f6d1-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4f6d1-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4f6d1-119">InvalidUnfocused</span></span>|<span data-ttu-id="4f6d1-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4f6d1-120">ValidationStates</span></span>|<span data-ttu-id="4f6d1-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="4f6d1-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="4f6d1-122">Esempio di ControlTemplate di GroupBox</span><span class="sxs-lookup"><span data-stu-id="4f6d1-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="4f6d1-123">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="4f6d1-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="4f6d1-124">Il <xref:System.Windows.Controls.ControlTemplate> utilizza una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="4f6d1-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4f6d1-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="4f6d1-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f6d1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f6d1-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4f6d1-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="4f6d1-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4f6d1-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="4f6d1-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4f6d1-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="4f6d1-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="4f6d1-130">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="4f6d1-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
