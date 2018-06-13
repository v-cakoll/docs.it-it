---
title: 'Procedura: animare la posizione di un oggetto utilizzando PointAnimation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 326b71c10ad608e2481673e1c4a8cbc9ecbdc0dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559178"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="e7584-102">Procedura: animare la posizione di un oggetto utilizzando PointAnimation</span><span class="sxs-lookup"><span data-stu-id="e7584-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="e7584-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.PointAnimation> classe per animare un oggetto lungo un <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="e7584-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7584-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7584-104">Example</span></span>  
 <span data-ttu-id="e7584-105">Nell'esempio seguente si sposta un'ellisse lungo un <xref:System.Windows.Shapes.Path> da un punto dello schermo a un altro.</span><span class="sxs-lookup"><span data-stu-id="e7584-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="e7584-106">L'esempio aggiunge un'animazione la posizione di un <xref:System.Windows.Media.EllipseGeometry> utilizzando <xref:System.Windows.Media.Animation.PointAnimation> animare il <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e7584-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e7584-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7584-107">See Also</span></span>  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [<span data-ttu-id="e7584-108">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="e7584-108">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="e7584-109">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="e7584-109">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [<span data-ttu-id="e7584-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="e7584-110">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [<span data-ttu-id="e7584-111">Animazione e temporizzazione</span><span class="sxs-lookup"><span data-stu-id="e7584-111">Animation and Timing</span></span>](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="e7584-112">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="e7584-112">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
