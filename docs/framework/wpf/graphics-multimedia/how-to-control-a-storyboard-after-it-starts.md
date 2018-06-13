---
title: 'Procedura: controllare uno storyboard in seguito al relativo avvio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 2407de5029007748de691a3020078b1241b02fd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561462"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="b531b-102">Procedura: controllare uno storyboard in seguito al relativo avvio</span><span class="sxs-lookup"><span data-stu-id="b531b-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="b531b-103">In questo esempio viene illustrato come utilizzare codice per controllare un <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="b531b-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="b531b-104">Per controllare uno storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilizzare <xref:System.Windows.Trigger> e <xref:System.Windows.TriggerAction> oggetti; ad esempio, vedere [utilizzare trigger di evento per controllare un Storyboard dopo l'avvio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="b531b-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="b531b-105">Per avviare uno storyboard, utilizzare il relativo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo, che distribuisce le animazioni dello storyboard per la proprietà animate e avvia lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="b531b-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="b531b-106">Per rendere controllabile uno storyboard, si utilizza il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> (metodo) e specificare **true** come secondo parametro.</span><span class="sxs-lookup"><span data-stu-id="b531b-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="b531b-107">È quindi possibile utilizzare metodi interattivi dello storyboard per sospendere, riprendere, cercare, arrestare, accelerare o rallentare lo storyboard o spostarlo al periodo di riempimento.</span><span class="sxs-lookup"><span data-stu-id="b531b-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="b531b-108">Di seguito è riportato un elenco di metodi interattivi dello storyboard:</span><span class="sxs-lookup"><span data-stu-id="b531b-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
-   <span data-ttu-id="b531b-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Sospende lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="b531b-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="b531b-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Consente di riprendere uno storyboard in pausa.</span><span class="sxs-lookup"><span data-stu-id="b531b-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="b531b-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Imposta velocità interattiva dello storyboard.</span><span class="sxs-lookup"><span data-stu-id="b531b-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>  
  
-   <span data-ttu-id="b531b-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Cerca lo storyboard nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="b531b-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>  
  
-   <span data-ttu-id="b531b-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Cerca lo storyboard nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="b531b-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="b531b-114">A differenza di <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> (metodo), questa operazione viene elaborata prima del tick successivo.</span><span class="sxs-lookup"><span data-stu-id="b531b-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
-   <span data-ttu-id="b531b-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Sposta uno storyboard a un periodo di riempimento, se presente.</span><span class="sxs-lookup"><span data-stu-id="b531b-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="b531b-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Interrompe lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="b531b-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="b531b-117">Nell'esempio seguente, vengono utilizzati vari metodi di storyboard per controllare in modo interattivo uno storyboard.</span><span class="sxs-lookup"><span data-stu-id="b531b-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="b531b-118">**Nota:** per vedere un esempio di controllo dell'utilizzo di trigger con uno storyboard [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [utilizzare i trigger di evento per controllare un Storyboard dopo l'avvio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="b531b-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b531b-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="b531b-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b531b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b531b-120">See Also</span></span>  
 [<span data-ttu-id="b531b-121">Usare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio</span><span class="sxs-lookup"><span data-stu-id="b531b-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
