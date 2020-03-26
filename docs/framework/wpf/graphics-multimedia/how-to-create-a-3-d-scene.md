---
title: 'Procedura: creare una scena 3DHow to: Create a 3D Scene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112102"
---
# <a name="how-to-create-a-3d-scene"></a><span data-ttu-id="70b6b-102">Procedura: creare una scena 3DHow to: Create a 3D Scene</span><span class="sxs-lookup"><span data-stu-id="70b6b-102">How to: Create a 3D Scene</span></span>
<span data-ttu-id="70b6b-103">Questo esempio mostra come creare un oggetto 3D simile a un foglio di carta piatto che è stato ruotato.</span><span class="sxs-lookup"><span data-stu-id="70b6b-103">This example shows how to create a 3D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="70b6b-104">Insieme <xref:System.Windows.Controls.Viewport3D> ai seguenti componenti vengono utilizzati per creare questa semplice scena 3D:</span><span class="sxs-lookup"><span data-stu-id="70b6b-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3D scene:</span></span>  
  
- <span data-ttu-id="70b6b-105">Una videocamera viene <xref:System.Windows.Media.Media3D.PerspectiveCamera>creata utilizzando un file .</span><span class="sxs-lookup"><span data-stu-id="70b6b-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="70b6b-106">La fotocamera specifica quale parte della scena 3D è visibile.</span><span class="sxs-lookup"><span data-stu-id="70b6b-106">The camera specifies what part of the 3D scene is viewable.</span></span>  
  
- <span data-ttu-id="70b6b-107">Viene creata una mesh per specificare la forma dell'oggetto 3D (foglio di carta) utilizzando la <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="70b6b-107">A mesh is created to specify the shape of 3D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="70b6b-108">Un materiale viene specificato per essere visualizzato sulla superficie dell'oggetto (sfumatura lineare in questo esempio) utilizzando la <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="70b6b-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="70b6b-109">Viene creata una luce per <xref:System.Windows.Media.Media3D.DirectionalLight>brillare sull'oggetto utilizzando .</span><span class="sxs-lookup"><span data-stu-id="70b6b-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70b6b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="70b6b-110">Example</span></span>  
 <span data-ttu-id="70b6b-111">Il codice seguente mostra come creare una scena 3D in XAML.</span><span class="sxs-lookup"><span data-stu-id="70b6b-111">The code below shows how to create a 3D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="70b6b-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="70b6b-112">Example</span></span>  
 <span data-ttu-id="70b6b-113">Il codice seguente mostra come creare la stessa scena 3D nel codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="70b6b-113">The code below shows how to create the same 3D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="70b6b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70b6b-114">See also</span></span>

- [<span data-ttu-id="70b6b-115">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="70b6b-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
