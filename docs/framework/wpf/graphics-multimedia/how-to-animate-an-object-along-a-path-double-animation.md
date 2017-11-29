---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Double)'
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
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a461b741675a18ac1e3544b17a9bbe9a8d18547
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="947e8-102">Procedura: animare un oggetto lungo un percorso (animazione Double)</span><span class="sxs-lookup"><span data-stu-id="947e8-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="947e8-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> classe per spostare un oggetto lungo un percorso definito da un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="947e8-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="947e8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="947e8-104">Example</span></span>  
 <span data-ttu-id="947e8-105">L'esempio seguente usa due <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> oggetti per spostare un rettangolo lungo un percorso:</span><span class="sxs-lookup"><span data-stu-id="947e8-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
-   <span data-ttu-id="947e8-106">Il primo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> aggiunge un'animazione di <xref:System.Windows.Media.TranslateTransform.X%2A> del <xref:System.Windows.Media.TranslateTransform> applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="947e8-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="947e8-107">In questo modo il rettangolo si sposta orizzontalmente lungo il tracciato.</span><span class="sxs-lookup"><span data-stu-id="947e8-107">It makes the rectangle move horizontally along the path.</span></span>  
  
-   <span data-ttu-id="947e8-108">Il secondo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> aggiunge un'animazione di <xref:System.Windows.Media.TranslateTransform.Y%2A> del <xref:System.Windows.Media.TranslateTransform> applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="947e8-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="947e8-109">In questo modo il rettangolo si sposta verticalmente lungo il tracciato.</span><span class="sxs-lookup"><span data-stu-id="947e8-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="947e8-110">Per l'esempio completo, vedere [percorso animazione esempio](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="947e8-110">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="947e8-111">È possibile spostare un oggetto utilizzando un percorso per utilizzare un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto.</span><span class="sxs-lookup"><span data-stu-id="947e8-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="947e8-112">Per un esempio, vedere [animare lungo un percorso di un oggetto (animazione Matrix)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="947e8-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="947e8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="947e8-113">See Also</span></span>  
 [<span data-ttu-id="947e8-114">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="947e8-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="947e8-115">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="947e8-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
