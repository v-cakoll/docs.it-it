---
title: 'Procedura: animare la posizione o il colore di un cursore sfumatura'
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
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452844"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="ef420-102">Procedura: animare la posizione o il colore di un cursore sfumatura</span><span class="sxs-lookup"><span data-stu-id="ef420-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="ef420-103">Questo esempio illustra come animare il <xref:System.Windows.Media.GradientStop.Color%2A> e <xref:System.Windows.Media.GradientStop.Offset%2A> di oggetti di <xref:System.Windows.Media.GradientStop>.</span><span class="sxs-lookup"><span data-stu-id="ef420-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef420-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef420-104">Example</span></span>  
 <span data-ttu-id="ef420-105">Nell'esempio seguente vengono animati tre arresti sfumatura all'interno di una <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="ef420-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="ef420-106">Nell'esempio vengono usate tre animazioni, ciascuna delle quali anima un diverso cursore sfumatura:</span><span class="sxs-lookup"><span data-stu-id="ef420-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
- <span data-ttu-id="ef420-107">La prima animazione, una <xref:System.Windows.Media.Animation.DoubleAnimation>, aggiunge un'animazione al <xref:System.Windows.Media.GradientStop.Offset%2A> del primo cursore sfumatura da 0,0 a 1,0 e quindi nuovamente a 0,0.</span><span class="sxs-lookup"><span data-stu-id="ef420-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="ef420-108">Di conseguenza, il primo colore della sfumatura si sposta dal lato sinistro al lato destro del rettangolo e quindi di nuovo al lato sinistro.</span><span class="sxs-lookup"><span data-stu-id="ef420-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
- <span data-ttu-id="ef420-109">La seconda animazione, una <xref:System.Windows.Media.Animation.ColorAnimation>, aggiunge un'animazione al <xref:System.Windows.Media.GradientStop.Color%2A> del secondo cursore sfumatura da <xref:System.Windows.Media.Colors.Purple%2A> a <xref:System.Windows.Media.Colors.Yellow%2A> e quindi di nuovo a <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef420-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="ef420-110">Di conseguenza, il colore intermedio della sfumatura passa da viola a giallo a quello viola e viceversa.</span><span class="sxs-lookup"><span data-stu-id="ef420-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
- <span data-ttu-id="ef420-111">La terza animazione, un'altra <xref:System.Windows.Media.Animation.ColorAnimation>, anima l'opacità del terzo <xref:System.Windows.Media.GradientStop.Color%2A> del cursore sfumatura di-1 e quindi di nuovo.</span><span class="sxs-lookup"><span data-stu-id="ef420-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="ef420-112">Di conseguenza, il terzo colore nella sfumatura scompare, quindi diventa di nuovo opaco.</span><span class="sxs-lookup"><span data-stu-id="ef420-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="ef420-113">Sebbene in questo esempio venga utilizzato un <xref:System.Windows.Media.LinearGradientBrush>, il processo è lo stesso per l'animazione di oggetti <xref:System.Windows.Media.GradientStop> all'interno di un <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="ef420-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="ef420-114">Per altri esempi, vedere l' [esempio di pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="ef420-114">For additional examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef420-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef420-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="ef420-116">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="ef420-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="ef420-117">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="ef420-117">Storyboards Overview</span></span>](storyboards-overview.md)
