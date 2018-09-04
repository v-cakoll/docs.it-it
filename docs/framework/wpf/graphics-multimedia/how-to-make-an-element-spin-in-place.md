---
title: 'Procedura: far ruotare sul posto un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 56385d7c31465e25f19486ea5cdaa8876cdb30ff
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43534412"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="95739-102">Procedura: far ruotare sul posto un elemento</span><span class="sxs-lookup"><span data-stu-id="95739-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="95739-103">Questo esempio viene illustrato come far ruotare utilizzando un elemento una <xref:System.Windows.Media.RotateTransform> e un <xref:System.Windows.Media.Animation.DoubleAnimation>.</span><span class="sxs-lookup"><span data-stu-id="95739-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="95739-104">L'esempio seguente applica il <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="95739-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="95739-105">L'esempio Usa una <xref:System.Windows.Media.Animation.DoubleAnimation> animare il <xref:System.Windows.Media.RotateTransform.Angle%2A> del <xref:System.Windows.Media.RotateTransform>.</span><span class="sxs-lookup"><span data-stu-id="95739-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="95739-106">Per rendere l'elemento ruotare sul posto, nell'esempio viene impostato il <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà dell'elemento per il punto (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="95739-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="95739-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="95739-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="95739-108">Per l'esempio completo, che include altri esempi di trasformazione, vedere [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="95739-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95739-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95739-109">See Also</span></span>  
 [<span data-ttu-id="95739-110">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="95739-110">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="95739-111">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="95739-111">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
