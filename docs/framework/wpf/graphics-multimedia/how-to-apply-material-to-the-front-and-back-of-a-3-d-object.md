---
title: 'Procedura: Applicare un oggetto Material alle parti anteriore e posteriore di un oggetto tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 16f30e3a880d7dcc943a9583ba0f04c4bd682827
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652033"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="ad625-102">Procedura: Applicare un oggetto Material alle parti anteriore e posteriore di un oggetto tridimensionale</span><span class="sxs-lookup"><span data-stu-id="ad625-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="ad625-103">Nell'esempio seguente viene illustrato come applicare un <xref:System.Windows.Media.Media3D.Material> nella parte anteriore e posteriore di un oggetto 3D dell'oggetto e animare l'oggetto in modo da visualizzare entrambi i lati dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ad625-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="ad625-104">Il <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà di un <xref:System.Windows.Media.Media3D.GeometryModel3D> viene usato per applicare una linea rossa <xref:System.Windows.Media.Brush> per il lato anteriore di oggetto e il <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> proprietà del <xref:System.Windows.Media.Media3D.GeometryModel3D> viene usato per applicare un blu <xref:System.Windows.Media.Brush> per il lato posteriore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ad625-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="ad625-105">Il codice seguente viene illustrata l'applicazione dei materiali all'oggetto:</span><span class="sxs-lookup"><span data-stu-id="ad625-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="ad625-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad625-106">Example</span></span>  
 <span data-ttu-id="ad625-107">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="ad625-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ad625-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad625-108">See also</span></span>
- [<span data-ttu-id="ad625-109">Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="ad625-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="ad625-110">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="ad625-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="ad625-111">Animare le proprietà Material in una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="ad625-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="ad625-112">Applicare materiale con componente emissiva a un oggetto tridimensionale</span><span class="sxs-lookup"><span data-stu-id="ad625-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
