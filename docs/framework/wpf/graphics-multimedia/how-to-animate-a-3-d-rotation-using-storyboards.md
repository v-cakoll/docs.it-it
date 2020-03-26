---
title: 'Procedura: animare una rotazione 3D tramite storyboardHow to: Animate a 3D Rotation Using Storyboards'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112214"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a><span data-ttu-id="e9377-102">Procedura: animare una rotazione 3D tramite storyboardHow to: Animate a 3D Rotation Using Storyboards</span><span class="sxs-lookup"><span data-stu-id="e9377-102">How to: Animate a 3D Rotation Using Storyboards</span></span>
<span data-ttu-id="e9377-103">L'esempio seguente mostra come far ruotare un oggetto 3D mentre <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> "oscilla" animando le proprietà e <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> di un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e9377-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="e9377-104">Questo <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto specifica la trasformazione di rotazione dell'oggetto 3D e pertanto l'animazione delle relative proprietà crea l'effetto di rotazione desiderato.</span><span class="sxs-lookup"><span data-stu-id="e9377-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="e9377-105">All'interno <xref:System.Windows.Media.Animation.DoubleAnimation> di Storyboard, <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> viene <xref:System.Windows.Media.Animation.Vector3DAnimation> utilizzato per animare la proprietà while viene utilizzato per animare la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e9377-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9377-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9377-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e9377-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9377-107">See also</span></span>

- [<span data-ttu-id="e9377-108">Animare una rotazione 3D usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="e9377-108">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="e9377-109">Animare una rotazione 3D usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="e9377-109">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="e9377-110">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="e9377-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="e9377-111">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="e9377-111">Storyboards Overview</span></span>](storyboards-overview.md)
