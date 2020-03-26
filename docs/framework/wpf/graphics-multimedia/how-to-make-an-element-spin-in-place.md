---
title: 'Procedura: far ruotare sul posto un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112076"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="a6f0c-102">Procedura: far ruotare sul posto un elemento</span><span class="sxs-lookup"><span data-stu-id="a6f0c-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="a6f0c-103">In questo esempio viene illustrato come <xref:System.Windows.Media.RotateTransform> fare <xref:System.Windows.Media.Animation.DoubleAnimation>in modo che un elemento si scandigli utilizzando a e un oggetto .</span><span class="sxs-lookup"><span data-stu-id="a6f0c-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="a6f0c-104">Nell'esempio seguente <xref:System.Windows.Media.RotateTransform> viene <xref:System.Windows.UIElement.RenderTransform%2A> applicato l'oggetto alla proprietà dell'elemento .</span><span class="sxs-lookup"><span data-stu-id="a6f0c-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="a6f0c-105">Nell'esempio <xref:System.Windows.Media.Animation.DoubleAnimation> viene utilizzato <xref:System.Windows.Media.RotateTransform.Angle%2A> un <xref:System.Windows.Media.RotateTransform>per animare l'oggetto dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="a6f0c-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="a6f0c-106">Per fare in modo che l'elemento si giri sul posto, l'esempio imposta la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà dell'elemento sul punto (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="a6f0c-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6f0c-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6f0c-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="a6f0c-108">Per l'esempio completo, che include altri esempi di trasformazione, vedere Esempio di [trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="a6f0c-108">For the complete sample, which includes more transformation examples, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f0c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6f0c-109">See also</span></span>

- [<span data-ttu-id="a6f0c-110">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="a6f0c-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a6f0c-111">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="a6f0c-111">Transforms Overview</span></span>](transforms-overview.md)
