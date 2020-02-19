---
title: 'Procedura: far ruotare sul posto un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452792"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="3bd2c-102">Procedura: far ruotare sul posto un elemento</span><span class="sxs-lookup"><span data-stu-id="3bd2c-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="3bd2c-103">In questo esempio viene illustrato come eseguire la rotazione di un elemento utilizzando un <xref:System.Windows.Media.RotateTransform> e una <xref:System.Windows.Media.Animation.DoubleAnimation>.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="3bd2c-104">Nell'esempio seguente viene applicato il <xref:System.Windows.Media.RotateTransform> alla proprietà <xref:System.Windows.UIElement.RenderTransform%2A> dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="3bd2c-105">Nell'esempio viene utilizzato un <xref:System.Windows.Media.Animation.DoubleAnimation> per animare il <xref:System.Windows.Media.RotateTransform.Angle%2A> dell'<xref:System.Windows.Media.RotateTransform>.</span><span class="sxs-lookup"><span data-stu-id="3bd2c-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="3bd2c-106">Per far ruotare l'elemento, nell'esempio viene impostata la proprietà <xref:System.Windows.UIElement.RenderTransformOrigin%2A> dell'elemento sul punto (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="3bd2c-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bd2c-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="3bd2c-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="3bd2c-108">Per l'esempio completo, che include altri esempi di trasformazione, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="3bd2c-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd2c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bd2c-109">See also</span></span>

- [<span data-ttu-id="3bd2c-110">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="3bd2c-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="3bd2c-111">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="3bd2c-111">Transforms Overview</span></span>](transforms-overview.md)
