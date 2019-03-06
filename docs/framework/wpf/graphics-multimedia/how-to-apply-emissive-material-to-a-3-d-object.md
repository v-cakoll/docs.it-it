---
title: 'Procedura: Applicare EmissiveMaterial a un oggetto 3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: 7f4158d59334c2f80775541ea1b0f944e048b081
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362500"
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a><span data-ttu-id="b1549-102">Procedura: Applicare EmissiveMaterial a un oggetto 3D</span><span class="sxs-lookup"><span data-stu-id="b1549-102">How to: Apply Emissive Material to a 3-D Object</span></span>
<span data-ttu-id="b1549-103">Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Media.Media3D.EmissiveMaterial> aggiungere colori a un oggetto Material uguale al colore del pennello di EmissiveMaterial esistente.</span><span class="sxs-lookup"><span data-stu-id="b1549-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="b1549-104">Il codice seguente illustra <xref:System.Windows.Media.Media3D.DiffuseMaterial> e <xref:System.Windows.Media.Media3D.EmissiveMaterial> applicato in combinazione per aggiungere blu all'aspetto dell'oggetto DiffuseMaterial.</span><span class="sxs-lookup"><span data-stu-id="b1549-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="b1549-105">Nel codice procedurale:</span><span class="sxs-lookup"><span data-stu-id="b1549-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="b1549-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1549-106">Example</span></span>  
 <span data-ttu-id="b1549-107">Il codice seguente illustra l'intero esempio in XAML.</span><span class="sxs-lookup"><span data-stu-id="b1549-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="b1549-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1549-108">Example</span></span>  
 <span data-ttu-id="b1549-109">Di seguito è riportato l'intero esempio nel codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="b1549-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b1549-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1549-110">See also</span></span>
- [<span data-ttu-id="b1549-111">Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="b1549-111">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="b1549-112">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="b1549-112">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="b1549-113">Animare le proprietà Material in una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="b1549-113">Animate Material Properties in a 3-D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="b1549-114">Applicare un oggetto Material alle parti anteriore e posteriore di un oggetto tridimensionale</span><span class="sxs-lookup"><span data-stu-id="b1549-114">Apply Material to the Front and Back of a 3-D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
