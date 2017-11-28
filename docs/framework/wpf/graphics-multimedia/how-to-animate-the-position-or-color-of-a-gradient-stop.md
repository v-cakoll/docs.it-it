---
title: 'Procedura: animare la posizione o il colore di un cursore sfumatura'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 968d285d8a3345da9810f0ba4797bf8b2e33d36e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="6b634-102">Procedura: animare la posizione o il colore di un cursore sfumatura</span><span class="sxs-lookup"><span data-stu-id="6b634-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="6b634-103">In questo esempio viene illustrato come animare la <xref:System.Windows.Media.GradientStop.Color%2A> e <xref:System.Windows.Media.GradientStop.Offset%2A> di <xref:System.Windows.Media.GradientStop> oggetti.</span><span class="sxs-lookup"><span data-stu-id="6b634-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b634-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b634-104">Example</span></span>  
 <span data-ttu-id="6b634-105">Nell'esempio seguente aggiunge un'animazione tre cursori sfumatura all'interno di un <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="6b634-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="6b634-106">L'esempio utilizza tre animazioni, ognuno dei quali aggiunge un'animazione a un cursore sfumatura diversi:</span><span class="sxs-lookup"><span data-stu-id="6b634-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
-   <span data-ttu-id="6b634-107">La prima animazione, un <xref:System.Windows.Media.Animation.DoubleAnimation>, aggiunge un'animazione il primo del cursore sfumatura <xref:System.Windows.Media.GradientStop.Offset%2A> da 0,0 a 1,0 e quindi nuovamente su 0,0.</span><span class="sxs-lookup"><span data-stu-id="6b634-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="6b634-108">Di conseguenza, il primo sfumatura si sposta da sinistra a destra del rettangolo di colore e quindi tornare a sinistra.</span><span class="sxs-lookup"><span data-stu-id="6b634-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
-   <span data-ttu-id="6b634-109">La seconda animazione, un <xref:System.Windows.Media.Animation.ColorAnimation>, aggiunge un'animazione il secondo del cursore sfumatura <xref:System.Windows.Media.GradientStop.Color%2A> da <xref:System.Windows.Media.Colors.Purple%2A> a <xref:System.Windows.Media.Colors.Yellow%2A> e quindi nuovamente <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b634-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="6b634-110">Di conseguenza, il colore intermedio della sfumatura cambia da viola giallo e tornare al viola.</span><span class="sxs-lookup"><span data-stu-id="6b634-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
-   <span data-ttu-id="6b634-111">La terza animazione, un altro <xref:System.Windows.Media.Animation.ColorAnimation>, aggiunge un'animazione l'opacità del terzo sfumatura <xref:System.Windows.Media.GradientStop.Color%2A> per -1 e quindi eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="6b634-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="6b634-112">Di conseguenza, il terzo colore della sfumatura di dissolvenza e quindi diventa opaco.</span><span class="sxs-lookup"><span data-stu-id="6b634-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="6b634-113">Sebbene questo esempio viene utilizzato un <xref:System.Windows.Media.LinearGradientBrush>, il processo è lo stesso per l'animazione <xref:System.Windows.Media.GradientStop> oggetti all'interno di un <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="6b634-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="6b634-114">Per ulteriori esempi, vedere il [esempio](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="6b634-114">For additional examples, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b634-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b634-115">See Also</span></span>  
 <xref:System.Windows.Media.GradientStop>  
 [<span data-ttu-id="6b634-116">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="6b634-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="6b634-117">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="6b634-117">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
