---
title: 'Procedura: Creare una scena tridimensionale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 23e01934eac0d9e1ea9fb5fbbbc5d8c9d8aabbc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494380"
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="4ef0d-102">Procedura: Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="4ef0d-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="4ef0d-103">In questo esempio viene illustrato come creare un oggetto 3D che è simile a un foglio di carta cui è stata ruotata.</span><span class="sxs-lookup"><span data-stu-id="4ef0d-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="4ef0d-104">Oggetto <xref:System.Windows.Controls.Viewport3D> insieme ai componenti seguenti vengono usati per creare questa scena 3D semplice:</span><span class="sxs-lookup"><span data-stu-id="4ef0d-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="4ef0d-105">Viene creata una fotocamera utilizzando un <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="4ef0d-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="4ef0d-106">La fotocamera specifica quale parte della scena 3D è visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="4ef0d-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="4ef0d-107">Viene creata una mesh per specificare la forma dell'oggetto 3D (foglio di carta) utilizzando il <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="4ef0d-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="4ef0d-108">Viene specificato un materiale da visualizzare sulla superficie dell'oggetto (in questo esempio, una sfumatura lineare) utilizzando il <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="4ef0d-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="4ef0d-109">Viene creata una luce per gli sviluppatori nell'oggetto utilizzando <xref:System.Windows.Media.Media3D.DirectionalLight>.</span><span class="sxs-lookup"><span data-stu-id="4ef0d-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ef0d-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ef0d-110">Example</span></span>  
 <span data-ttu-id="4ef0d-111">Il codice seguente illustra come creare una scena 3D in XAML.</span><span class="sxs-lookup"><span data-stu-id="4ef0d-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="4ef0d-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ef0d-112">Example</span></span>  
 <span data-ttu-id="4ef0d-113">Il codice seguente illustra come creare la stessa scena 3D in codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="4ef0d-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="4ef0d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ef0d-114">See also</span></span>
- [<span data-ttu-id="4ef0d-115">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="4ef0d-115">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
