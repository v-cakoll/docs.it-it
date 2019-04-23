---
title: "Procedura: Aggiungere un'animazione alla posizione di un oggetto usando PointAnimation"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 1ef3f77e551affaa7e61d2aabf95f10c29275417
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111306"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="0923e-102">Procedura: Aggiungere un'animazione alla posizione di un oggetto usando PointAnimation</span><span class="sxs-lookup"><span data-stu-id="0923e-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="0923e-103">Questo esempio illustra come usare il <xref:System.Windows.Media.Animation.PointAnimation> classe per animare un oggetto lungo un <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="0923e-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0923e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0923e-104">Example</span></span>  
 <span data-ttu-id="0923e-105">L'esempio seguente sposta un'ellisse un <xref:System.Windows.Shapes.Path> da un punto dello schermo a un altro.</span><span class="sxs-lookup"><span data-stu-id="0923e-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="0923e-106">Nell'esempio viene animata la posizione di un <xref:System.Windows.Media.EllipseGeometry> usando <xref:System.Windows.Media.Animation.PointAnimation> per aggiungere un'animazione la <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="0923e-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0923e-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0923e-107">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [<span data-ttu-id="0923e-108">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="0923e-108">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="0923e-109">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="0923e-109">Graphics and Multimedia</span></span>](index.md)
- [<span data-ttu-id="0923e-110">Procedure relative alla grafica</span><span class="sxs-lookup"><span data-stu-id="0923e-110">Graphics How-to Topics</span></span>](graphics-how-to-topics.md)
- [<span data-ttu-id="0923e-111">Animazione e temporizzazione procedure</span><span class="sxs-lookup"><span data-stu-id="0923e-111">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
