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
ms.openlocfilehash: 3a35f6dda05cfe65811de16d76b288c8fbd618a7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43874917"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="46088-102">Procedura: ruotare un oggetto utilizzando un percorso geometrico (animazione Matrix)</span><span class="sxs-lookup"><span data-stu-id="46088-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="46088-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> e una <xref:System.Windows.Media.MatrixTransform> per ruotare un oggetto lungo un tracciato geometrico definito da un <xref:System.Windows.Media.PathGeometry> oggetto.</span><span class="sxs-lookup"><span data-stu-id="46088-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46088-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="46088-104">Example</span></span>  
 <span data-ttu-id="46088-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto da animare il <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="46088-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="46088-106">Il <xref:System.Windows.Media.MatrixTransform> viene applicato a un pulsante e ne determina lo spostamento lungo un tracciato curvo.</span><span class="sxs-lookup"><span data-stu-id="46088-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="46088-107">Poiché il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> è impostata su `true`, il rettangolo ruota lungo la tangente del percorso.</span><span class="sxs-lookup"><span data-stu-id="46088-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="46088-108">Per l'esempio completo, vedere [esempio di animazione tracciato](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="46088-108">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="46088-109">La versione del codice dell'esempio precedente utilizzato un <xref:System.Windows.Media.Animation.Storyboard> animare il <xref:System.Windows.Media.EllipseGeometry>, anche se è stata applicata l'animazione solo una.</span><span class="sxs-lookup"><span data-stu-id="46088-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="46088-110">Un modo più semplice per applicare una singola animazione a una proprietà nel codice consiste nell'usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="46088-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="46088-111">Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="46088-111">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46088-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46088-112">See Also</span></span>  
 [<span data-ttu-id="46088-113">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="46088-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="46088-114">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="46088-114">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [<span data-ttu-id="46088-115">Path Animation Sample (Esempio di animazione tracciato)</span><span class="sxs-lookup"><span data-stu-id="46088-115">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
