---
title: 'Procedura: Applicare un disegno a un modello tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 14470d0adeb948ea46a0720b5713c20fb7d8e6d8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855877"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="349bc-102">Procedura: Applicare un disegno a un modello tridimensionale</span><span class="sxs-lookup"><span data-stu-id="349bc-102">How to: Apply a Drawing to a 3-D Model</span></span>

<span data-ttu-id="349bc-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.Media3D.Material> come applicato a un modello 3D.</span><span class="sxs-lookup"><span data-stu-id="349bc-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>

<span data-ttu-id="349bc-104">Il codice seguente definisce un <xref:System.Windows.Media.DrawingGroup> oggetto come contenuto di un <xref:System.Windows.Media.DrawingBrush>oggetto.</span><span class="sxs-lookup"><span data-stu-id="349bc-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="349bc-105">Viene impostato come la <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> proprietà dell'oggetto <xref:System.Windows.Media.Media3D.DiffuseMaterial> applicato a un piano 3D. <xref:System.Windows.Media.DrawingBrush></span><span class="sxs-lookup"><span data-stu-id="349bc-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="349bc-106">Spesso è consigliabile definire oggetti e valori complessi come il disegno seguente come risorse che possono essere riutilizzate e semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="349bc-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="349bc-107">Per ulteriori informazioni, vedere [risorse XAML](../advanced/xaml-resources.md) .</span><span class="sxs-lookup"><span data-stu-id="349bc-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="349bc-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="349bc-108">Example</span></span>

<span data-ttu-id="349bc-109">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="349bc-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="349bc-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="349bc-110">See also</span></span>

- [<span data-ttu-id="349bc-111">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="349bc-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="349bc-112">Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="349bc-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="349bc-113">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="349bc-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="349bc-114">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="349bc-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
