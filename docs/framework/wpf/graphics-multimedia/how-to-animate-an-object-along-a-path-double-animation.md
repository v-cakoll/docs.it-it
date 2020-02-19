---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Double)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452857"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="f8ea3-102">Procedura: animare un oggetto lungo un percorso (animazione Double)</span><span class="sxs-lookup"><span data-stu-id="f8ea3-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="f8ea3-103">Questo esempio illustra come usare la classe <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> per spostare un oggetto lungo un tracciato definito da un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="f8ea3-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8ea3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8ea3-104">Example</span></span>  
 <span data-ttu-id="f8ea3-105">Nell'esempio seguente vengono usati due oggetti <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> per spostare un rettangolo lungo un tracciato geometrico:</span><span class="sxs-lookup"><span data-stu-id="f8ea3-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
- <span data-ttu-id="f8ea3-106">Il primo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima la <xref:System.Windows.Media.TranslateTransform.X%2A> del <xref:System.Windows.Media.TranslateTransform> applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="f8ea3-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="f8ea3-107">In questo modo il rettangolo si sposta orizzontalmente lungo il tracciato.</span><span class="sxs-lookup"><span data-stu-id="f8ea3-107">It makes the rectangle move horizontally along the path.</span></span>  
  
- <span data-ttu-id="f8ea3-108">Il secondo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> aggiunge un'animazione al <xref:System.Windows.Media.TranslateTransform.Y%2A> del <xref:System.Windows.Media.TranslateTransform> applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="f8ea3-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="f8ea3-109">In questo modo il rettangolo si sposta verticalmente lungo il tracciato.</span><span class="sxs-lookup"><span data-stu-id="f8ea3-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="f8ea3-110">Per l'esempio completo, vedere [esempio di animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="f8ea3-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="f8ea3-111">Un altro modo per spostare un oggetto usando un percorso geometrico consiste nell'usare un oggetto <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>.</span><span class="sxs-lookup"><span data-stu-id="f8ea3-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="f8ea3-112">Per un esempio, vedere [animare un oggetto lungo un tracciato (animazione Matrix)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="f8ea3-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ea3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8ea3-113">See also</span></span>

- [<span data-ttu-id="f8ea3-114">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="f8ea3-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f8ea3-115">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="f8ea3-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
