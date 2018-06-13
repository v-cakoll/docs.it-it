---
title: 'Procedura: applicare più trasformazioni a un modello tridimensionale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: 591f12d2e4d51df0d8474f894946b24910f8df86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558691"
---
# <a name="how-to-apply-multiple-transformations-to-a-3-d-model"></a><span data-ttu-id="7bd6b-102">Procedura: applicare più trasformazioni a un modello tridimensionale</span><span class="sxs-lookup"><span data-stu-id="7bd6b-102">How to: Apply Multiple Transformations to a 3-D Model</span></span>
<span data-ttu-id="7bd6b-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Media3D.RotateTransform3D> e <xref:System.Windows.Media.Media3D.ScaleTransform3D> per ruotare e modificare la scala di un modello 3D.</span><span class="sxs-lookup"><span data-stu-id="7bd6b-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3-D model.</span></span> <span data-ttu-id="7bd6b-104">Il codice riportato di seguito viene illustrato come applicare tali trasformazioni per il <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> proprietà di un <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span><span class="sxs-lookup"><span data-stu-id="7bd6b-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="7bd6b-105">In codice:</span><span class="sxs-lookup"><span data-stu-id="7bd6b-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="7bd6b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bd6b-106">Example</span></span>  
 <span data-ttu-id="7bd6b-107">Il codice seguente viene illustrato l'esempio completo in XAML.</span><span class="sxs-lookup"><span data-stu-id="7bd6b-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="7bd6b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bd6b-108">Example</span></span>  
 <span data-ttu-id="7bd6b-109">Di seguito è riportato l'esempio completo nel codice.</span><span class="sxs-lookup"><span data-stu-id="7bd6b-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="7bd6b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bd6b-110">See Also</span></span>  
 [<span data-ttu-id="7bd6b-111">Ridimensionare un modello tridimensionale</span><span class="sxs-lookup"><span data-stu-id="7bd6b-111">Transform the Scale of a 3-D Model</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-transform-the-scale-of-a-3-d-model.md)
