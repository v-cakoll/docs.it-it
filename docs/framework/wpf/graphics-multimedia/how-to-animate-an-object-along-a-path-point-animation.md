---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Point)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: 639e28d9b809d6fb5eed3a002bca1ffc40913896
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558781"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="e48d0-102">Procedura: animare un oggetto lungo un percorso (animazione Point)</span><span class="sxs-lookup"><span data-stu-id="e48d0-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="e48d0-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> oggetto da animare un <xref:System.Windows.Point> lungo un percorso curvo.</span><span class="sxs-lookup"><span data-stu-id="e48d0-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e48d0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e48d0-104">Example</span></span>  
 <span data-ttu-id="e48d0-105">Nell'esempio seguente viene spostato un <xref:System.Windows.Media.EllipseGeometry> lungo un percorso definito da un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="e48d0-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="e48d0-106">La geometria dell'ellisse <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà, che accetta un <xref:System.Windows.Point> valore, specifica la posizione; per spostare la geometria di puntini di sospensione, si animare la <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e48d0-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="e48d0-107">Nell'esempio viene utilizzato un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> per animare la <xref:System.Windows.Media.EllipseGeometry> dell'oggetto <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e48d0-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="e48d0-108">Per l'esempio completo, vedere [percorso animazione esempio](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="e48d0-108">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="e48d0-109">La versione del codice dell'esempio precedente utilizzato un <xref:System.Windows.Media.Animation.Storyboard> per animare la <xref:System.Windows.Media.EllipseGeometry>, anche se è stata applicata un'unica animazione.</span><span class="sxs-lookup"><span data-stu-id="e48d0-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="e48d0-110">Oggetto <xref:System.Windows.Media.Animation.Storyboard> è spesso il modo più semplice per applicare più animazioni, poiché è possono controllare queste animazioni dallo stesso <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="e48d0-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="e48d0-111">Tuttavia, un modo più semplice per applicare una sola animazione a una proprietà quando si utilizza codice è utilizzare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e48d0-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="e48d0-112">Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="e48d0-112">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e48d0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e48d0-113">See Also</span></span>  
 [<span data-ttu-id="e48d0-114">Path Animation Sample (Esempio di animazione tracciato)</span><span class="sxs-lookup"><span data-stu-id="e48d0-114">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="e48d0-115">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="e48d0-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="e48d0-116">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="e48d0-116">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
