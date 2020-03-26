---
title: 'Procedura: animare le traduzioni 3DHow to: Animate 3D Translations'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112258"
---
# <a name="how-to-animate-3d-translations"></a><span data-ttu-id="49279-102">Procedura: animare le traduzioni 3DHow to: Animate 3D Translations</span><span class="sxs-lookup"><span data-stu-id="49279-102">How to: Animate 3D Translations</span></span>
<span data-ttu-id="49279-103">In questo argomento viene illustrato come animare un set di trasformazioni di traslazione in un modello 3D.</span><span class="sxs-lookup"><span data-stu-id="49279-103">This topic demonstrates how to animate a translation transformation set on a 3D model.</span></span>  
  
 <span data-ttu-id="49279-104">Nel codice riportato di <xref:System.Windows.Media.Media3D.TranslateTransform3D> seguito <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> viene illustrata l'applicazione di un oggetto alla proprietà di un <xref:System.Windows.Media.Media3D.GeometryModel3D>oggetto .</span><span class="sxs-lookup"><span data-stu-id="49279-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="49279-105">La <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> proprietà <xref:System.Windows.Media.Media3D.TranslateTransform3D> di questo oggetto viene animata utilizzando il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="49279-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="49279-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="49279-106">Example</span></span>  
 <span data-ttu-id="49279-107">Il codice seguente mostra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="49279-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="49279-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49279-108">See also</span></span>

- [<span data-ttu-id="49279-109">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="49279-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="49279-110">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="49279-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="49279-111">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="49279-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="49279-112">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="49279-112">Transforms Overview</span></span>](transforms-overview.md)
