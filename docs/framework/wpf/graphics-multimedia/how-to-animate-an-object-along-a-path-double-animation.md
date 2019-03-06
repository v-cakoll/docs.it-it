---
title: 'Procedura: Animare un oggetto lungo un percorso (animazione Double)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 1838b2492e7ea8a33139fdb5682362998d84a98d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363401"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="8aea6-102">Procedura: Animare un oggetto lungo un percorso (animazione Double)</span><span class="sxs-lookup"><span data-stu-id="8aea6-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="8aea6-103">Questo esempio illustra come usare il <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> classe per spostare un oggetto lungo un tracciato definito da un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="8aea6-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aea6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8aea6-104">Example</span></span>  
 <span data-ttu-id="8aea6-105">L'esempio seguente usa due <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> oggetti per spostare un rettangolo lungo un tracciato geometrico:</span><span class="sxs-lookup"><span data-stu-id="8aea6-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
-   <span data-ttu-id="8aea6-106">Il primo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima la <xref:System.Windows.Media.TranslateTransform.X%2A> del <xref:System.Windows.Media.TranslateTransform> applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="8aea6-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="8aea6-107">In questo modo il rettangolo si sposta orizzontalmente lungo il tracciato.</span><span class="sxs-lookup"><span data-stu-id="8aea6-107">It makes the rectangle move horizontally along the path.</span></span>  
  
-   <span data-ttu-id="8aea6-108">La seconda <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima la <xref:System.Windows.Media.TranslateTransform.Y%2A> del <xref:System.Windows.Media.TranslateTransform> applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="8aea6-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="8aea6-109">In questo modo il rettangolo si sposta verticalmente lungo il tracciato.</span><span class="sxs-lookup"><span data-stu-id="8aea6-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="8aea6-110">Per l'esempio completo, vedere [esempio di animazione tracciato](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="8aea6-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="8aea6-111">Un altro modo per spostare un oggetto con un tracciato geometrico consiste nell'usare un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto.</span><span class="sxs-lookup"><span data-stu-id="8aea6-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="8aea6-112">Per un esempio, vedere [animare un oggetto lungo un tracciato (animazione Matrix)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="8aea6-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aea6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aea6-113">See also</span></span>
- [<span data-ttu-id="8aea6-114">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="8aea6-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="8aea6-115">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="8aea6-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
