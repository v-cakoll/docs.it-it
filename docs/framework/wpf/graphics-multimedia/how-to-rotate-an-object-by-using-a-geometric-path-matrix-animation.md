---
title: 'Procedura: ruotare un oggetto utilizzando un percorso geometrico (animazione Matrix)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 6deb593ca059d49f744226be313adb6d8781b325
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561989"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="daf13-102">Procedura: ruotare un oggetto utilizzando un percorso geometrico (animazione Matrix)</span><span class="sxs-lookup"><span data-stu-id="daf13-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="daf13-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> e <xref:System.Windows.Media.MatrixTransform> per ruotare un oggetto lungo un percorso definito da un <xref:System.Windows.Media.PathGeometry> oggetto.</span><span class="sxs-lookup"><span data-stu-id="daf13-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daf13-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="daf13-104">Example</span></span>  
 <span data-ttu-id="daf13-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto da cui iniziare l'animazione di <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="daf13-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="daf13-106">Il <xref:System.Windows.Media.MatrixTransform> viene applicato a un pulsante e determina lo spostamento lungo un percorso curvo.</span><span class="sxs-lookup"><span data-stu-id="daf13-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="daf13-107">Poiché il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> è impostata su `true`, il rettangolo ruota lungo la tangente del percorso.</span><span class="sxs-lookup"><span data-stu-id="daf13-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="daf13-108">Per l'esempio completo, vedere [percorso animazione esempio](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="daf13-108">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="daf13-109">La versione del codice dell'esempio precedente utilizzato un <xref:System.Windows.Media.Animation.Storyboard> per animare la <xref:System.Windows.Media.EllipseGeometry>, anche se è stata applicata un'unica animazione.</span><span class="sxs-lookup"><span data-stu-id="daf13-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="daf13-110">Per applicare una sola animazione a una proprietà nel codice in modo più semplice consiste nell'utilizzare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="daf13-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="daf13-111">Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="daf13-111">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf13-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daf13-112">See Also</span></span>  
 [<span data-ttu-id="daf13-113">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="daf13-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="daf13-114">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="daf13-114">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [<span data-ttu-id="daf13-115">Path Animation Sample (Esempio di animazione tracciato)</span><span class="sxs-lookup"><span data-stu-id="daf13-115">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)
