---
title: "Procedura: Aggiungere un'animazione alla posizione o al colore di un cursore sfumatura"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: 4762233cace895c9d492fb426f3f6be14498ad53
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593354"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="c5837-102">Procedura: Aggiungere un'animazione alla posizione o al colore di un cursore sfumatura</span><span class="sxs-lookup"><span data-stu-id="c5837-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="c5837-103">In questo esempio illustra come animare la <xref:System.Windows.Media.GradientStop.Color%2A> e <xref:System.Windows.Media.GradientStop.Offset%2A> di <xref:System.Windows.Media.GradientStop> oggetti.</span><span class="sxs-lookup"><span data-stu-id="c5837-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5837-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5837-104">Example</span></span>  
 <span data-ttu-id="c5837-105">L'esempio seguente anima tre sfumatura all'interno di un <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="c5837-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="c5837-106">L'esempio Usa tre animazioni, ognuna delle quali anima un cursore sfumatura diversi:</span><span class="sxs-lookup"><span data-stu-id="c5837-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
- <span data-ttu-id="c5837-107">La prima animazione, un <xref:System.Windows.Media.Animation.DoubleAnimation>, aggiunge un'animazione il prima del cursore sfumatura <xref:System.Windows.Media.GradientStop.Offset%2A> da 0,0 a 1,0 e quindi nuovamente su 0,0.</span><span class="sxs-lookup"><span data-stu-id="c5837-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="c5837-108">Di conseguenza, il primo colore in sfumatura si sposta da sinistra al lato destro del rettangolo e quindi eseguire il backup sul lato sinistro.</span><span class="sxs-lookup"><span data-stu-id="c5837-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
- <span data-ttu-id="c5837-109">La seconda animazione, un <xref:System.Windows.Media.Animation.ColorAnimation>, aggiunge un'animazione di secondo del cursore sfumatura <xref:System.Windows.Media.GradientStop.Color%2A> dal <xref:System.Windows.Media.Colors.Purple%2A> al <xref:System.Windows.Media.Colors.Yellow%2A> e quindi tornare alla <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5837-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="c5837-110">Di conseguenza, il colore intermedio della sfumatura cambia da viola in giallo e nuovamente in viola.</span><span class="sxs-lookup"><span data-stu-id="c5837-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
- <span data-ttu-id="c5837-111">La terza animazione, un'altra <xref:System.Windows.Media.Animation.ColorAnimation>, consente di animare l'opacità del terzo cursore sfumatura <xref:System.Windows.Media.GradientStop.Color%2A> da -1 e poi di nuovo.</span><span class="sxs-lookup"><span data-stu-id="c5837-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="c5837-112">Di conseguenza, il terzo colore della sfumatura di dissolvenza e quindi diventa nuovamente opaco.</span><span class="sxs-lookup"><span data-stu-id="c5837-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="c5837-113">Sebbene questo esempio Usa un' <xref:System.Windows.Media.LinearGradientBrush>, il processo è lo stesso per l'animazione <xref:System.Windows.Media.GradientStop> oggetti all'interno di un <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="c5837-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="c5837-114">Per altri esempi, vedere la [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="c5837-114">For additional examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5837-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5837-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="c5837-116">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="c5837-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c5837-117">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="c5837-117">Storyboards Overview</span></span>](storyboards-overview.md)
