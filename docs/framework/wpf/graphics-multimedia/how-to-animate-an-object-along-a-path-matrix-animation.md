---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Matrix)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 7dfc233fe60e1cea293edc44a2bba79dc6962f7c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452909"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="e5528-102">Procedura: animare un oggetto lungo un percorso (animazione Matrix)</span><span class="sxs-lookup"><span data-stu-id="e5528-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="e5528-103">Questo esempio illustra come usare la classe <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> per animare un oggetto lungo un tracciato definito da un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="e5528-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5528-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5528-104">Example</span></span>  
 <span data-ttu-id="e5528-105">L'esempio seguente aggiunge un'animazione a un oggetto lungo un tracciato effettuando le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5528-105">The following example animates an object along a path by doing the following:</span></span>  
  
- <span data-ttu-id="e5528-106">Applica un <xref:System.Windows.Media.MatrixTransform> all'oggetto per spostarlo.</span><span class="sxs-lookup"><span data-stu-id="e5528-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
- <span data-ttu-id="e5528-107">Definisce il percorso utilizzando un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="e5528-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
- <span data-ttu-id="e5528-108">Crea una <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> e la usa per aggiungere un'animazione alla proprietà <xref:System.Windows.Media.Matrix> dell'<xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="e5528-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="e5528-109">Il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> accetta il <xref:System.Windows.Media.PathGeometry> e lo usa per generare valori di <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="e5528-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="e5528-110">Per l'esempio completo, vedere [esempio di animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="e5528-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span> <span data-ttu-id="e5528-111">Per altre informazioni sui percorsi geometrici, vedere [Cenni preliminari sulla geometria](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e5528-111">For more information about geometric paths, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5528-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5528-112">See also</span></span>

- [<span data-ttu-id="e5528-113">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="e5528-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="e5528-114">Path Animation Sample (Esempio di animazione tracciato)</span><span class="sxs-lookup"><span data-stu-id="e5528-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="e5528-115">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="e5528-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
