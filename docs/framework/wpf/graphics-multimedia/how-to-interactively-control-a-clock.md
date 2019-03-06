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
ms.openlocfilehash: 6d3dbc8c39e63b46871b0cc88fbe8d5d51b63463
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361655"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="e0af6-102">Procedura: Controllare in modo interattivo un oggetto Clock</span><span class="sxs-lookup"><span data-stu-id="e0af6-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="e0af6-103">Oggetto <xref:System.Windows.Media.Animation.Clock> dell'oggetto <xref:System.Windows.Media.Animation.ClockController> proprietà consente in modo interattivo avviare, sospendere, riprendere, seek, spostare l'orologio per periodo di riempimento e arrestare l'orologio.</span><span class="sxs-lookup"><span data-stu-id="e0af6-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="e0af6-104">È possibile controllare in modo interattivo solo il clock radice di un albero di temporizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0af6-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0af6-105">Esistono altri modi per in modo interattivo le animazioni di controllo che non richiedono di lavorare direttamente con gli orologi: è anche possibile usare gli storyboard.</span><span class="sxs-lookup"><span data-stu-id="e0af6-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="e0af6-106">Gli storyboard sono supportati nel markup e nel codice.</span><span class="sxs-lookup"><span data-stu-id="e0af6-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="e0af6-107">Per un esempio, vedere [animare una proprietà utilizzando uno Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) o nella [Cenni preliminari sull'animazione](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e0af6-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="e0af6-108">Nell'esempio seguente, diversi pulsanti consentono di controllare in modo interattivo un orologio dell'animazione.</span><span class="sxs-lookup"><span data-stu-id="e0af6-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0af6-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e0af6-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="e0af6-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0af6-110">See also</span></span>
- [<span data-ttu-id="e0af6-111">Animare una proprietà utilizzando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="e0af6-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="e0af6-112">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="e0af6-112">Animation Overview</span></span>](animation-overview.md)
