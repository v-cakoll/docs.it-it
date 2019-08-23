---
title: 'Procedura: Controllare in modo interattivo un oggetto Clock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951342"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="98e29-102">Procedura: Controllare in modo interattivo un oggetto Clock</span><span class="sxs-lookup"><span data-stu-id="98e29-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="98e29-103">La <xref:System.Windows.Media.Animation.Clock> <xref:System.Windows.Media.Animation.ClockController> proprietà di un oggetto consente di avviare, sospendere, riprendere, cercare, far avanzare il clock al periodo di riempimento e di arrestare l'orologio in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="98e29-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="98e29-104">Solo il clock radice di un albero temporale può essere controllato in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="98e29-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98e29-105">Esistono altri modi per controllare in modo interattivo le animazioni che non richiedono l'uso diretto degli orologi: è anche possibile usare gli storyboard.</span><span class="sxs-lookup"><span data-stu-id="98e29-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="98e29-106">Gli storyboard sono supportati sia nel markup che nel codice.</span><span class="sxs-lookup"><span data-stu-id="98e29-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="98e29-107">Per un esempio, vedere [animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md) o [Cenni preliminari sull'animazione](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98e29-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="98e29-108">Nell'esempio seguente vengono usati diversi pulsanti per controllare in modo interattivo un clock di animazione.</span><span class="sxs-lookup"><span data-stu-id="98e29-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98e29-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="98e29-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="98e29-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98e29-110">See also</span></span>

- [<span data-ttu-id="98e29-111">Animare una proprietà utilizzando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="98e29-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="98e29-112">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="98e29-112">Animation Overview</span></span>](animation-overview.md)
