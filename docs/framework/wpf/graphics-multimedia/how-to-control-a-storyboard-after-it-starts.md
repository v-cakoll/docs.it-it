---
title: "Procedura: Controllare uno Storyboard dopo l'avvio"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 107391386dfbb718f9436d9a039b08439fbc3279
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762137"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="77d9b-102">Procedura: Controllare uno Storyboard dopo l'avvio</span><span class="sxs-lookup"><span data-stu-id="77d9b-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="77d9b-103">Questo esempio illustra come usare il codice al controllo un <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="77d9b-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="77d9b-104">Per controllare uno storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usare <xref:System.Windows.Trigger> e <xref:System.Windows.TriggerAction> oggetti; per un esempio, vedere [usare i trigger di evento per controllare un Storyboard dopo il relativo avvio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="77d9b-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="77d9b-105">Per avviare uno storyboard, usare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo, che distribuisce le animazioni dello storyboard per le proprietà che vengono animati, avvia lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="77d9b-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="77d9b-106">Per rendere uno storyboard controllabile, si utilizza il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo e specificare **true** come secondo parametro.</span><span class="sxs-lookup"><span data-stu-id="77d9b-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="77d9b-107">È quindi possibile usare metodi interattivi dello storyboard per sospendere, riprendere, seek, arrestare, velocizzare, o rallentare lo storyboard o spostarlo al periodo di riempimento.</span><span class="sxs-lookup"><span data-stu-id="77d9b-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="77d9b-108">Di seguito è riportato un elenco di metodi interattiva dello storyboard:</span><span class="sxs-lookup"><span data-stu-id="77d9b-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
- <span data-ttu-id="77d9b-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Sospende lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="77d9b-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>  
  
- <span data-ttu-id="77d9b-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Riprende uno storyboard sospeso.</span><span class="sxs-lookup"><span data-stu-id="77d9b-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>  
  
- <span data-ttu-id="77d9b-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Imposta velocità interattiva dello storyboard.</span><span class="sxs-lookup"><span data-stu-id="77d9b-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>  
  
- <span data-ttu-id="77d9b-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Cerca lo storyboard nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="77d9b-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>  
  
- <span data-ttu-id="77d9b-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Cerca lo storyboard nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="77d9b-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="77d9b-114">A differenza di <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> (metodo), questa operazione viene elaborata prima il tick successivo.</span><span class="sxs-lookup"><span data-stu-id="77d9b-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
- <span data-ttu-id="77d9b-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Sposta in avanti di uno storyboard a un periodo di riempimento, se presente.</span><span class="sxs-lookup"><span data-stu-id="77d9b-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>  
  
- <span data-ttu-id="77d9b-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Interrompe lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="77d9b-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="77d9b-117">Nell'esempio seguente vengono utilizzati vari metodi di storyboard per controllare uno storyboard in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="77d9b-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="77d9b-118">**Nota:** Per vedere un esempio di controllo dell'utilizzo di trigger con uno storyboard [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [usare i trigger di evento per controllare un Storyboard dopo il relativo avvio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="77d9b-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="77d9b-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="77d9b-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="77d9b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77d9b-120">See also</span></span>

- [<span data-ttu-id="77d9b-121">Usare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio</span><span class="sxs-lookup"><span data-stu-id="77d9b-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
