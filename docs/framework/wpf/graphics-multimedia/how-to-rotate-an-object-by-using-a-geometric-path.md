---
title: 'Procedura: ruotare un oggetto utilizzando un percorso geometrico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186871"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="2e9d0-102">Procedura: ruotare un oggetto utilizzando un percorso geometrico</span><span class="sxs-lookup"><span data-stu-id="2e9d0-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="2e9d0-103">In questo esempio viene illustrato come ruotare (pivot) un <xref:System.Windows.Media.PathGeometry> oggetto lungo un percorso geometrico definito da un oggetto.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e9d0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e9d0-104">Example</span></span>  
 <span data-ttu-id="2e9d0-105">Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> vengono utilizzati tre oggetti per spostare un rettangolo lungo un percorso geometrico.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
- <span data-ttu-id="2e9d0-106">Il <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> primo aggiunge <xref:System.Windows.Media.RotateTransform> un'animazione a che viene applicata al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="2e9d0-107">L'animazione genera valori angolari.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-107">The animation generates angle values.</span></span> <span data-ttu-id="2e9d0-108">Il rettangolo ruota lungo i contorni del tracciato.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
- <span data-ttu-id="2e9d0-109">Gli altri due <xref:System.Windows.Media.TranslateTransform.X%2A> oggetti <xref:System.Windows.Media.TranslateTransform.Y%2A> animano <xref:System.Windows.Media.TranslateTransform> i valori e di un oggetto applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="2e9d0-110">Fanno in modo che il rettangolo si sposti orizzontalmente e verticalmente lungo il tracciato.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="2e9d0-111">Un altro modo per ruotare un oggetto <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> utilizzando un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> tracciato `true`geometrico consiste nell'utilizzare un oggetto e impostarne la proprietà su .</span><span class="sxs-lookup"><span data-stu-id="2e9d0-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="2e9d0-112">Per ulteriori informazioni e un esempio, vedere [Ruotare un oggetto utilizzando un percorso geometrico (animazione a matrice)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="2e9d0-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="2e9d0-113">Per l'esempio completo, vedere Esempio di [animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="2e9d0-113">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9d0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e9d0-114">See also</span></span>

- [<span data-ttu-id="2e9d0-115">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="2e9d0-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="2e9d0-116">Path Animation Sample (Esempio di animazione tracciato)</span><span class="sxs-lookup"><span data-stu-id="2e9d0-116">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="2e9d0-117">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="2e9d0-117">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
