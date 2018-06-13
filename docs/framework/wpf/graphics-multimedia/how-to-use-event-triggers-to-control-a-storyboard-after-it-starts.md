---
title: 'Procedura: utilizzare i trigger di evento per controllare uno storyboard dopo il relativo avvio'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: c864668026c4f8bb58a4d6c4c36f96fb07445a9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561294"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="8838d-102">Procedura: utilizzare i trigger di evento per controllare uno storyboard dopo il relativo avvio</span><span class="sxs-lookup"><span data-stu-id="8838d-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="8838d-103">In questo esempio viene illustrato come controllare un <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="8838d-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="8838d-104">Per avviare un <xref:System.Windows.Media.Animation.Storyboard> utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilizzare <xref:System.Windows.Media.Animation.BeginStoryboard>, che distribuisce le animazioni agli oggetti e proprietà animate e quindi avvia lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="8838d-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="8838d-105">Se si fornisce <xref:System.Windows.Media.Animation.BeginStoryboard> un nome, specificando il relativo <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> proprietà consentono di uno storyboard controllabile.</span><span class="sxs-lookup"><span data-stu-id="8838d-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="8838d-106">È quindi possibile controllare in modo interattivo lo storyboard dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="8838d-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="8838d-107">Utilizzare le seguenti azioni di storyboard con <xref:System.Windows.EventTrigger> oggetti per controllare uno storyboard.</span><span class="sxs-lookup"><span data-stu-id="8838d-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <span data-ttu-id="8838d-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Sospende lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="8838d-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="8838d-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Consente di riprendere uno storyboard in pausa.</span><span class="sxs-lookup"><span data-stu-id="8838d-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="8838d-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Modifica la velocità di storyboard.</span><span class="sxs-lookup"><span data-stu-id="8838d-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>  
  
-   <span data-ttu-id="8838d-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Sposta uno storyboard alla fine del periodo di riempimento, se presente.</span><span class="sxs-lookup"><span data-stu-id="8838d-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="8838d-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Interrompe lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="8838d-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>  
  
-   <span data-ttu-id="8838d-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Rimuove lo storyboard, liberando risorse.</span><span class="sxs-lookup"><span data-stu-id="8838d-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8838d-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="8838d-114">Example</span></span>  
 <span data-ttu-id="8838d-115">Nell'esempio seguente usa azioni di storyboard controllabili per controllare in modo interattivo uno storyboard.</span><span class="sxs-lookup"><span data-stu-id="8838d-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="8838d-116">**Nota:** per un esempio di controllo di uno storyboard tramite codice, vedere la sezione [metodi del controllo un Storyboard dopo che viene avviato utilizzando relativo interattivo](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="8838d-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="8838d-117">Per ulteriori esempi, vedere il [raccolta](http://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="8838d-117">For additional examples, see the [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8838d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8838d-118">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [<span data-ttu-id="8838d-119">Controllare uno storyboard in seguito al relativo avvio usando i metodi interattivi</span><span class="sxs-lookup"><span data-stu-id="8838d-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [<span data-ttu-id="8838d-120">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="8838d-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="8838d-121">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="8838d-121">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
