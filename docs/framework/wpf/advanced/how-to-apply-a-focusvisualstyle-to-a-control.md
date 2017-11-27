---
title: 'Procedura: applicare un oggetto FocusVisualStyle a un controllo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f614e244293d08cd836edaf82496ca9e7b51423e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="a049f-102">Procedura: applicare un oggetto FocusVisualStyle a un controllo</span><span class="sxs-lookup"><span data-stu-id="a049f-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="a049f-103">In questo esempio viene illustrato come creare uno stile di visualizzazione dello stato attivo in risorse e applicare lo stile a un controllo, utilizzando il <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="a049f-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a049f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a049f-104">Example</span></span>  
 <span data-ttu-id="a049f-105">Nell'esempio seguente viene definito uno stile che crea la composizione del controllo aggiuntivo che si applica solo quando il controllo è attivo nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a049f-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="a049f-106">Questa operazione viene eseguita mediante la definizione di uno stile con un <xref:System.Windows.Controls.ControlTemplate>, quindi creare riferimenti a tale stile come una risorsa durante l'impostazione di <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="a049f-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="a049f-107">Un rettangolo esterno simili a un bordo viene inserito all'esterno dell'area rettangolare.</span><span class="sxs-lookup"><span data-stu-id="a049f-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="a049f-108">A meno che non viene modificato in caso contrario, il ridimensionamento dello stile utilizza il <xref:System.Windows.FrameworkElement.ActualHeight%2A> e <xref:System.Windows.FrameworkElement.ActualWidth%2A> del controllo rettangolare in cui viene applicato lo stile di visualizzazione dello stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a049f-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="a049f-109">In questo esempio imposta i valori negativi per le <xref:System.Windows.FrameworkElement.Margin%2A> per rendere il bordo leggermente di fuori del controllo con stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a049f-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="a049f-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> è additivo per qualsiasi stile di modello di controllo che deriva da uno stile esplicito o uno stile del tema; lo stile primario per un controllo può comunque essere creato utilizzando un <xref:System.Windows.Controls.ControlTemplate> e l'impostazione dello stile il <xref:System.Windows.FrameworkElement.Style%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="a049f-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="a049f-111">Lo stato attivo per gli stili di visualizzazione deve essere usate in modo coerente un tema o un'interfaccia utente, anziché utilizzare una diversa per ogni elemento con stato attivabile.</span><span class="sxs-lookup"><span data-stu-id="a049f-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="a049f-112">Per informazioni dettagliate, vedere [stile per lo stato attivo nei controlli e FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="a049f-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a049f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a049f-113">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [<span data-ttu-id="a049f-114">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="a049f-114">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a049f-115">Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="a049f-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)
