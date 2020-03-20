---
title: 'Procedura: utilizzare i trigger di evento per controllare uno storyboard dopo il relativo avvio'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186708"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="e5cb1-102">Procedura: utilizzare i trigger di evento per controllare uno storyboard dopo il relativo avvio</span><span class="sxs-lookup"><span data-stu-id="e5cb1-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>

<span data-ttu-id="e5cb1-103">In questo esempio viene <xref:System.Windows.Media.Animation.Storyboard> illustrato come controllare un dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="e5cb1-104">Per iniziare <xref:System.Windows.Media.Animation.Storyboard> un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]utilizzando <xref:System.Windows.Media.Animation.BeginStoryboard>, utilizzare , che distribuisce le animazioni agli oggetti e alle proprietà che animano e quindi avvia lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="e5cb1-105">Se si <xref:System.Windows.Media.Animation.BeginStoryboard> assegna un nome <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> specificandone la proprietà, la si rende uno storyboard controllabile.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="e5cb1-106">È quindi possibile controllare in modo interattivo lo storyboard dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-106">You can then interactively control the storyboard after it starts.</span></span>

<span data-ttu-id="e5cb1-107">Usare le seguenti azioni <xref:System.Windows.EventTrigger> dello storyboard insieme agli oggetti per controllare uno storyboard.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>

- <span data-ttu-id="e5cb1-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: mette in pausa lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>

- <span data-ttu-id="e5cb1-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: riprende uno storyboard in pausa.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="e5cb1-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: modifica la velocità dello storyboard.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>

- <span data-ttu-id="e5cb1-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: sposta uno storyboard alla fine del periodo di riempimento, se ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>

- <span data-ttu-id="e5cb1-112"><xref:System.Windows.Media.Animation.StopStoryboard>: interrompe lo storyboard.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>

- <span data-ttu-id="e5cb1-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: rimuove lo storyboard, liberando risorse.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>

## <a name="example"></a><span data-ttu-id="e5cb1-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5cb1-114">Example</span></span>

<span data-ttu-id="e5cb1-115">Nell'esempio seguente vengono utilizzate azioni di storyboard controllabili per controllare in modo interattivo uno storyboard.</span><span class="sxs-lookup"><span data-stu-id="e5cb1-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="e5cb1-116">Per visualizzare un esempio di controllo di uno storyboard tramite codice, vedere [Controllo di uno storyboard dopo l'avvio dell'utilizzo](how-to-control-a-storyboard-after-it-starts.md)dei relativi metodi interattivi .</span><span class="sxs-lookup"><span data-stu-id="e5cb1-116">To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

<span data-ttu-id="e5cb1-117">Per ulteriori esempi, vedere raccolta di esempi di [animazione](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="e5cb1-117">For additional examples, see the [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

## <a name="see-also"></a><span data-ttu-id="e5cb1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5cb1-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="e5cb1-119">Controllare uno storyboard in seguito al relativo avvio usando i metodi interattivi</span><span class="sxs-lookup"><span data-stu-id="e5cb1-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="e5cb1-120">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="e5cb1-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="e5cb1-121">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="e5cb1-121">Storyboards Overview</span></span>](storyboards-overview.md)
