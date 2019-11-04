---
title: Stili e modelli di NavigationWindow
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 4aae14299b3959e7d2122991954cc62505d2a19e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460199"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="d96ce-102">Stili e modelli di NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="d96ce-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="d96ce-103">In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="d96ce-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="d96ce-104">È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="d96ce-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d96ce-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d96ce-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="d96ce-106">Parti NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="d96ce-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="d96ce-107">Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="d96ce-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="d96ce-108">Parte</span><span class="sxs-lookup"><span data-stu-id="d96ce-108">Part</span></span>|<span data-ttu-id="d96ce-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="d96ce-109">Type</span></span>|<span data-ttu-id="d96ce-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d96ce-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d96ce-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="d96ce-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="d96ce-112">Area del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d96ce-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="d96ce-113">Stati NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="d96ce-113">NavigationWindow States</span></span>  
 <span data-ttu-id="d96ce-114">Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="d96ce-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="d96ce-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="d96ce-115">VisualState Name</span></span>|<span data-ttu-id="d96ce-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d96ce-116">VisualStateGroup Name</span></span>|<span data-ttu-id="d96ce-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d96ce-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d96ce-118">Valido</span><span class="sxs-lookup"><span data-stu-id="d96ce-118">Valid</span></span>|<span data-ttu-id="d96ce-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d96ce-119">ValidationStates</span></span>|<span data-ttu-id="d96ce-120">Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="d96ce-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d96ce-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d96ce-121">InvalidFocused</span></span>|<span data-ttu-id="d96ce-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d96ce-122">ValidationStates</span></span>|<span data-ttu-id="d96ce-123">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="d96ce-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d96ce-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d96ce-124">InvalidUnfocused</span></span>|<span data-ttu-id="d96ce-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d96ce-125">ValidationStates</span></span>|<span data-ttu-id="d96ce-126">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="d96ce-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="d96ce-127">Esempio di ControlTemplate NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="d96ce-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="d96ce-128">Sebbene in questo esempio siano contenuti tutti gli elementi definiti nel <xref:System.Windows.Controls.ControlTemplate> di un <xref:System.Windows.Navigation.NavigationWindow> per impostazione predefinita, i valori specifici devono essere considerati come esempi.</span><span class="sxs-lookup"><span data-stu-id="d96ce-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="d96ce-129">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="d96ce-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d96ce-130">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d96ce-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96ce-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d96ce-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d96ce-132">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="d96ce-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d96ce-133">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="d96ce-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d96ce-134">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="d96ce-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="d96ce-135">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d96ce-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
