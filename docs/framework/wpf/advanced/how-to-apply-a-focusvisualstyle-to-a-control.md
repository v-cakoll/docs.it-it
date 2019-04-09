---
title: 'Procedura: Applicare un oggetto FocusVisualStyle a un controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: 53d4984946143c15c4a2b71095529fb5ee7de4b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133549"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="96bc6-102">Procedura: Applicare un oggetto FocusVisualStyle a un controllo</span><span class="sxs-lookup"><span data-stu-id="96bc6-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="96bc6-103">In questo esempio illustra come creare uno stile di visualizzazione dello stato attivo in risorse e applicare lo stile a un controllo, usando il <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="96bc6-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96bc6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="96bc6-104">Example</span></span>  
 <span data-ttu-id="96bc6-105">L'esempio seguente definisce uno stile che consente di creare la composizione di controlli aggiuntivi che si applica solo quando il controllo è attivo nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96bc6-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="96bc6-106">Questa operazione viene eseguita mediante la definizione di uno stile con un <xref:System.Windows.Controls.ControlTemplate>, quindi fare riferimento a tale stile come risorsa quando si impostano le <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="96bc6-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="96bc6-107">Un rettangolo esterno che assomiglia a un bordo viene posizionato all'esterno dell'area rettangolare.</span><span class="sxs-lookup"><span data-stu-id="96bc6-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="96bc6-108">A meno che non viene modificato in caso contrario, il ridimensionamento dello stile utilizza il <xref:System.Windows.FrameworkElement.ActualHeight%2A> e <xref:System.Windows.FrameworkElement.ActualWidth%2A> del controllo rettangolare in cui viene applicato lo stile di visualizzazione dello stato attivo.</span><span class="sxs-lookup"><span data-stu-id="96bc6-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="96bc6-109">In questo esempio imposta i valori negativi per le <xref:System.Windows.FrameworkElement.Margin%2A> per rendere il bordo apparire leggermente di fuori del controllo con lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="96bc6-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="96bc6-110">Oggetto <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> è additivo per qualsiasi stile di modello di controllo che deriva da uno stile esplicito o uno stile del tema; lo stile di un controllo primario può comunque creato utilizzando una <xref:System.Windows.Controls.ControlTemplate> e impostando lo stile sul <xref:System.Windows.FrameworkElement.Style%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="96bc6-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="96bc6-111">Lo stato attivo gli stili di visualizzazione deve essere usate in modo coerente un tema o un'interfaccia utente, invece di usare una diversa per ogni elemento attivabile.</span><span class="sxs-lookup"><span data-stu-id="96bc6-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="96bc6-112">Per informazioni dettagliate, vedere [applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="96bc6-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96bc6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96bc6-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="96bc6-114">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="96bc6-114">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="96bc6-115">Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="96bc6-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
