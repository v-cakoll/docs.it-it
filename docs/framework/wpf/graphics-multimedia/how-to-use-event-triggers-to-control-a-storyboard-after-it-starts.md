---
title: 'Procedura: Utilizzare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: e4cfaf2352c3cca2b67a8e6a5d4c933399583e5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663648"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="9aea8-102">Procedura: Utilizzare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio</span><span class="sxs-lookup"><span data-stu-id="9aea8-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="9aea8-103">In questo esempio viene illustrato come controllare un <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="9aea8-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="9aea8-104">Per avviare un <xref:System.Windows.Media.Animation.Storyboard> usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usare <xref:System.Windows.Media.Animation.BeginStoryboard>, che distribuisce le animazioni agli oggetti e proprietà animate e quindi avvia lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="9aea8-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="9aea8-105">Qualora il Licenziatario fornisca <xref:System.Windows.Media.Animation.BeginStoryboard> specificando un nome relativo <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> proprietà, si renderla uno storyboard controllabile.</span><span class="sxs-lookup"><span data-stu-id="9aea8-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="9aea8-106">È quindi possibile controllare in modo interattivo lo storyboard dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="9aea8-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="9aea8-107">Usare le seguenti azioni di storyboard con <xref:System.Windows.EventTrigger> oggetti per controllare uno storyboard.</span><span class="sxs-lookup"><span data-stu-id="9aea8-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <span data-ttu-id="9aea8-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Sospende lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="9aea8-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="9aea8-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Riprende uno storyboard sospeso.</span><span class="sxs-lookup"><span data-stu-id="9aea8-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="9aea8-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Modifica la velocità dello storyboard.</span><span class="sxs-lookup"><span data-stu-id="9aea8-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>  
  
-   <span data-ttu-id="9aea8-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Sposta uno storyboard alla fine del periodo di riempimento, se presente.</span><span class="sxs-lookup"><span data-stu-id="9aea8-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="9aea8-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Interrompe lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="9aea8-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>  
  
-   <span data-ttu-id="9aea8-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Rimuove lo storyboard, liberando così risorse.</span><span class="sxs-lookup"><span data-stu-id="9aea8-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9aea8-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="9aea8-114">Example</span></span>  
 <span data-ttu-id="9aea8-115">Nell'esempio seguente usa azioni dello storyboard controllabili per controllare uno storyboard in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="9aea8-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="9aea8-116">**Nota:** Per un esempio di controllare uno storyboard tramite codice, vedere [controllare un Storyboard dopo che viene avviata usando relativi metodi interattivi](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="9aea8-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="9aea8-117">Per altri esempi, vedere la [raccolta di esempi di animazione](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="9aea8-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aea8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9aea8-118">See also</span></span>
- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="9aea8-119">Controllare uno storyboard in seguito al relativo avvio usando i metodi interattivi</span><span class="sxs-lookup"><span data-stu-id="9aea8-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="9aea8-120">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="9aea8-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="9aea8-121">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="9aea8-121">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
