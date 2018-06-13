---
title: 'Procedura: far ruotare sul posto un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a37952af621c79d231b45a247c92d3576a533580
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562511"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="8b09f-102">Procedura: far ruotare sul posto un elemento</span><span class="sxs-lookup"><span data-stu-id="8b09f-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="8b09f-103">Questo esempio viene illustrato come creare un elemento di selezione tramite un <xref:System.Windows.Media.RotateTransform> e <xref:System.Windows.Media.Animation.DoubleAnimation>.</span><span class="sxs-lookup"><span data-stu-id="8b09f-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="8b09f-104">Nell'esempio seguente viene applicato il <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="8b09f-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="8b09f-105">Nell'esempio viene utilizzato un <xref:System.Windows.Media.Animation.DoubleAnimation> per animare la <xref:System.Windows.Media.RotateTransform.Angle%2A> del <xref:System.Windows.Media.RotateTransform>.</span><span class="sxs-lookup"><span data-stu-id="8b09f-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="8b09f-106">Per far ruotare sul posto l'elemento, nell'esempio viene impostato il <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà dell'elemento per il punto (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="8b09f-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b09f-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b09f-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="8b09f-108">Per un esempio completo che include più trasformazioni, vedere [esempio trasformazioni 2D](http://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="8b09f-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b09f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b09f-109">See Also</span></span>  
 [<span data-ttu-id="8b09f-110">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="8b09f-110">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="8b09f-111">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="8b09f-111">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
