---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Matrix con accumulazione offset)'
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
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8a9fd282d3ca4603eadd0ed10436944f7e9ab593
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="1abea-102">Procedura: animare un oggetto lungo un percorso (animazione Matrix con accumulazione offset)</span><span class="sxs-lookup"><span data-stu-id="1abea-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="1abea-103">In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> classe animare un oggetto lungo un percorso e che l'animazione vengono accumulati all'offset valori durante la ripetizione.</span><span class="sxs-lookup"><span data-stu-id="1abea-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1abea-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1abea-104">Example</span></span>  
 <span data-ttu-id="1abea-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto da cui iniziare l'animazione di <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform> applicato a un pulsante.</span><span class="sxs-lookup"><span data-stu-id="1abea-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="1abea-106">Di conseguenza, un pulsante si sposta lungo un tracciato curvo.</span><span class="sxs-lookup"><span data-stu-id="1abea-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="1abea-107">Inoltre, nell'esempio viene impostato il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> proprietà `true`, che comporta l'offset della matrice animata si accumulano durante la ripetizione dell'animazione.</span><span class="sxs-lookup"><span data-stu-id="1abea-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="1abea-108">Poiché lo scostamento si accumula, il pulsante viene spostato ulteriormente sullo schermo quando l'animazione si ripete, piuttosto che tornare nella posizione iniziale.</span><span class="sxs-lookup"><span data-stu-id="1abea-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="1abea-109">Si noti che, sebbene il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> fa sì che i valori di offset per accumulato nelle ripetizioni, ma non accumulare i valori di rotazione.</span><span class="sxs-lookup"><span data-stu-id="1abea-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="1abea-110">Per accumulare i valori di rotazione, impostare l'animazione <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> e <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="1abea-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="1abea-111">Per l'esempio completo, vedere [percorso animazione esempio](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="1abea-111">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="1abea-112">Per un esempio che illustra come aggiungere un'animazione a un <xref:System.Windows.Media.Matrix> lungo un percorso senza accumulazione offset, vedere [animare lungo un percorso di un oggetto (animazione Matrix)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="1abea-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1abea-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1abea-113">See Also</span></span>  
 [<span data-ttu-id="1abea-114">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="1abea-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="1abea-115">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="1abea-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
