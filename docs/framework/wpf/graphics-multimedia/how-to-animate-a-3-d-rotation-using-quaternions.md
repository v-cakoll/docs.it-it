---
title: 'Procedura: animare una rotazione 3D utilizzando i quaternioniHow to: Animate a 3D Rotation Using Quaternions'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112245"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a><span data-ttu-id="7fa77-102">Procedura: animare una rotazione 3D utilizzando i quaternioniHow to: Animate a 3D Rotation Using Quaternions</span><span class="sxs-lookup"><span data-stu-id="7fa77-102">How to: Animate a 3D Rotation Using Quaternions</span></span>
<span data-ttu-id="7fa77-103">In questo esempio viene illustrato come animare una rotazione di un oggetto 3D utilizzando i quaternioni.</span><span class="sxs-lookup"><span data-stu-id="7fa77-103">This example shows how to animate a rotation of a 3D object using quaternions.</span></span>  
  
 <span data-ttu-id="7fa77-104">Nel codice riportato di seguito viene illustrato un <xref:System.Windows.Media.Media3D.QuaternionRotation3D> valore utilizzato come valore per la <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> proprietà di un <xref:System.Windows.Media.Media3D.RotateTransform3D>oggetto .</span><span class="sxs-lookup"><span data-stu-id="7fa77-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="7fa77-105">Questo <xref:System.Windows.Media.Media3D.QuaternionRotation3D> viene animato con un <xref:System.Windows.Media.Animation.QuaternionAnimation> all'interno di un <xref:System.Windows.Media.Animation.Storyboard> utilizzando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7fa77-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="7fa77-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fa77-106">Example</span></span>  
 <span data-ttu-id="7fa77-107">Il codice seguente mostra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="7fa77-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="7fa77-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fa77-108">See also</span></span>

- [<span data-ttu-id="7fa77-109">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="7fa77-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="7fa77-110">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="7fa77-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="7fa77-111">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="7fa77-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="7fa77-112">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="7fa77-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="7fa77-113">Animare una rotazione 3D usando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="7fa77-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="7fa77-114">Animare una rotazione 3D usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="7fa77-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
