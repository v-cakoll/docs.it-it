---
title: 'Procedura: Animare la posizione di un oggetto utilizzando PointAnimation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 04dbcfdb64525e6231ecf33c8ac5ecf2a2d2cb7e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357931"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="433c2-102">Procedura: Animare la posizione di un oggetto utilizzando PointAnimation</span><span class="sxs-lookup"><span data-stu-id="433c2-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="433c2-103">Questo esempio illustra come usare il <xref:System.Windows.Media.Animation.PointAnimation> classe per animare un oggetto lungo un <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="433c2-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="433c2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="433c2-104">Example</span></span>  
 <span data-ttu-id="433c2-105">L'esempio seguente sposta un'ellisse un <xref:System.Windows.Shapes.Path> da un punto dello schermo a un altro.</span><span class="sxs-lookup"><span data-stu-id="433c2-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="433c2-106">Nell'esempio viene animata la posizione di un <xref:System.Windows.Media.EllipseGeometry> usando <xref:System.Windows.Media.Animation.PointAnimation> per aggiungere un'animazione la <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="433c2-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="433c2-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="433c2-107">See also</span></span>
- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [<span data-ttu-id="433c2-108">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="433c2-108">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="433c2-109">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="433c2-109">Graphics and Multimedia</span></span>](index.md)
- [<span data-ttu-id="433c2-110">Procedure relative alla grafica</span><span class="sxs-lookup"><span data-stu-id="433c2-110">Graphics How-to Topics</span></span>](graphics-how-to-topics.md)
- [<span data-ttu-id="433c2-111">Animazione e temporizzazione procedure</span><span class="sxs-lookup"><span data-stu-id="433c2-111">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
