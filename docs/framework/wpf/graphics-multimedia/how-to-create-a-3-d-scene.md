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
ms.openlocfilehash: 8e176cb437055787da86d56770dd71323134fa33
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126230"
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="b1ac9-102">Procedura: Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="b1ac9-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="b1ac9-103">In questo esempio viene illustrato come creare un oggetto 3D che è simile a un foglio di carta cui è stata ruotata.</span><span class="sxs-lookup"><span data-stu-id="b1ac9-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="b1ac9-104">Oggetto <xref:System.Windows.Controls.Viewport3D> insieme ai componenti seguenti vengono usati per creare questa scena 3D semplice:</span><span class="sxs-lookup"><span data-stu-id="b1ac9-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="b1ac9-105">Viene creata una fotocamera utilizzando un <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="b1ac9-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="b1ac9-106">La fotocamera specifica quale parte della scena 3D è visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="b1ac9-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="b1ac9-107">Viene creata una mesh per specificare la forma dell'oggetto 3D (foglio di carta) utilizzando il <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="b1ac9-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="b1ac9-108">Viene specificato un materiale da visualizzare sulla superficie dell'oggetto (in questo esempio, una sfumatura lineare) utilizzando il <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="b1ac9-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="b1ac9-109">Viene creata una luce per gli sviluppatori nell'oggetto utilizzando <xref:System.Windows.Media.Media3D.DirectionalLight>.</span><span class="sxs-lookup"><span data-stu-id="b1ac9-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1ac9-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1ac9-110">Example</span></span>  
 <span data-ttu-id="b1ac9-111">Il codice seguente illustra come creare una scena 3D in XAML.</span><span class="sxs-lookup"><span data-stu-id="b1ac9-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="b1ac9-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1ac9-112">Example</span></span>  
 <span data-ttu-id="b1ac9-113">Il codice seguente illustra come creare la stessa scena 3D in codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="b1ac9-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b1ac9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1ac9-114">See also</span></span>

- [<span data-ttu-id="b1ac9-115">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="b1ac9-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
