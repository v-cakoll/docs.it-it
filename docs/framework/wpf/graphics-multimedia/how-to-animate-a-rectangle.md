---
title: "Procedura: Aggiungere un'animazione a un rettangolo"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], rectangles
- rectangles [WPF], animating
ms.assetid: 572ffb95-790d-4ace-adbf-b2ea8a90e75b
ms.openlocfilehash: 7f7cf24f7883553329de3761ff0670e8e3a09463
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151008"
---
# <a name="how-to-animate-a-rectangle"></a><span data-ttu-id="f4736-102">Procedura: Aggiungere un'animazione a un rettangolo</span><span class="sxs-lookup"><span data-stu-id="f4736-102">How to: Animate a Rectangle</span></span>
<span data-ttu-id="f4736-103">Questo esempio illustra come animare le modifiche apportate alle dimensioni e alla posizione di un rettangolo.</span><span class="sxs-lookup"><span data-stu-id="f4736-103">This example shows how to animate changes to the size and position of a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4736-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4736-104">Example</span></span>  
 <span data-ttu-id="f4736-105">L'esempio seguente usa un'istanza del <xref:System.Windows.Media.Animation.RectAnimation> classe per animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un <xref:System.Windows.Media.RectangleGeometry>, che anima le modifiche alle dimensioni e posizione del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="f4736-105">The following example uses an instance of the <xref:System.Windows.Media.Animation.RectAnimation> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>, which animates changes to the size and position of the rectangle.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f4736-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4736-106">See also</span></span>

- <xref:System.Windows.Media.Animation.RectAnimation>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.RectangleGeometry>
- [<span data-ttu-id="f4736-107">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="f4736-107">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f4736-108">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="f4736-108">Graphics and Multimedia</span></span>](index.md)
- [<span data-ttu-id="f4736-109">Procedure relative alle funzionalità grafiche</span><span class="sxs-lookup"><span data-stu-id="f4736-109">Graphics How-to Topics</span></span>](graphics-how-to-topics.md)
- [<span data-ttu-id="f4736-110">Procedure relative all'animazione e al sistema di temporizzazione</span><span class="sxs-lookup"><span data-stu-id="f4736-110">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
