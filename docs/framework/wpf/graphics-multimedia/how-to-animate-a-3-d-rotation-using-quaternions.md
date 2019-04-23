---
title: "Procedura: Aggiungere un'animazione a una rotazione tridimensionale usando quaternioni"
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: d994ac2ae67fd366f27f123d5bd15f14d5ac7abe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183222"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="f32e0-102">Procedura: Aggiungere un'animazione a una rotazione tridimensionale usando quaternioni</span><span class="sxs-lookup"><span data-stu-id="f32e0-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="f32e0-103">In questo esempio illustra come animare una rotazione di un oggetto 3D tramite quaternioni.</span><span class="sxs-lookup"><span data-stu-id="f32e0-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="f32e0-104">Il codice seguente mostra una <xref:System.Windows.Media.Media3D.QuaternionRotation3D> utilizzato come valore per il <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> proprietà di un <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="f32e0-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="f32e0-105">Ciò <xref:System.Windows.Media.Media3D.QuaternionRotation3D> viene aggiunta un'animazione con una <xref:System.Windows.Media.Animation.QuaternionAnimation> all'interno di un <xref:System.Windows.Media.Animation.Storyboard> usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f32e0-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="f32e0-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="f32e0-106">Example</span></span>  
 <span data-ttu-id="f32e0-107">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="f32e0-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f32e0-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f32e0-108">See also</span></span>

- [<span data-ttu-id="f32e0-109">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="f32e0-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f32e0-110">Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="f32e0-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="f32e0-111">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="f32e0-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="f32e0-112">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="f32e0-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="f32e0-113">Animare una rotazione tridimensionale usando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="f32e0-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="f32e0-114">Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="f32e0-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
