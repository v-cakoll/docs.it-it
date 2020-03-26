---
title: 'Procedura: Applicare materiale emissivo a un oggetto 3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3D objects
- 3D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: bf32b41ec2410c01ad137ec0ca9311f7c2b70061
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112154"
---
# <a name="how-to-apply-emissive-material-to-a-3d-object"></a><span data-ttu-id="0c583-102">Procedura: Applicare materiale emissivo a un oggetto 3D</span><span class="sxs-lookup"><span data-stu-id="0c583-102">How to: Apply Emissive Material to a 3D Object</span></span>
<span data-ttu-id="0c583-103">Nell'esempio seguente viene <xref:System.Windows.Media.Media3D.EmissiveMaterial> illustrato come utilizzare per aggiungere un colore a un materiale esistente uguale al colore del pennello di EmissiveMaterial.</span><span class="sxs-lookup"><span data-stu-id="0c583-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="0c583-104">Il codice <xref:System.Windows.Media.Media3D.DiffuseMaterial> seguente <xref:System.Windows.Media.Media3D.EmissiveMaterial> mostra e applicato in combinazione per aggiungere blu all'aspetto di DiffuseMaterial.</span><span class="sxs-lookup"><span data-stu-id="0c583-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="0c583-105">Nel codice procedurale:</span><span class="sxs-lookup"><span data-stu-id="0c583-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="0c583-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c583-106">Example</span></span>  
 <span data-ttu-id="0c583-107">Il codice seguente mostra l'intero esempio in XAML.</span><span class="sxs-lookup"><span data-stu-id="0c583-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="0c583-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c583-108">Example</span></span>  
 <span data-ttu-id="0c583-109">Di seguito è riportato l'intero esempio nel codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="0c583-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0c583-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c583-110">See also</span></span>

- [<span data-ttu-id="0c583-111">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="0c583-111">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="0c583-112">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="0c583-112">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="0c583-113">Animare le proprietà Material in una scena 3D</span><span class="sxs-lookup"><span data-stu-id="0c583-113">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="0c583-114">Applicare un oggetto Material alle parti anteriore e posteriore di un oggetto 3D</span><span class="sxs-lookup"><span data-stu-id="0c583-114">Apply Material to the Front and Back of a 3D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
