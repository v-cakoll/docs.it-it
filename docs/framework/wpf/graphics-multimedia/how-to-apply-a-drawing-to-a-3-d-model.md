---
title: 'Procedura: applicare un disegno a un modello 3DHow to: Apply a Drawing to a 3D Model'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 5b10630ab674fa9489cdf7ad53516a680f19da08
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112180"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a><span data-ttu-id="63eba-102">Procedura: applicare un disegno a un modello 3DHow to: Apply a Drawing to a 3D Model</span><span class="sxs-lookup"><span data-stu-id="63eba-102">How to: Apply a Drawing to a 3D Model</span></span>

<span data-ttu-id="63eba-103">In questo esempio viene <xref:System.Windows.Media.DrawingBrush> illustrato <xref:System.Windows.Media.Media3D.Material> come utilizzare un come applicato a un modello 3D.</span><span class="sxs-lookup"><span data-stu-id="63eba-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>

<span data-ttu-id="63eba-104">Il codice seguente <xref:System.Windows.Media.DrawingGroup> definisce un <xref:System.Windows.Media.DrawingBrush>come contenuto di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="63eba-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="63eba-105">L'oggetto <xref:System.Windows.Media.DrawingBrush> viene <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> impostato <xref:System.Windows.Media.Media3D.DiffuseMaterial> come proprietà dell'oggetto applicato a un piano 3D.</span><span class="sxs-lookup"><span data-stu-id="63eba-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="63eba-106">È spesso opportuno definire oggetti complessi e valori come il disegno seguente come risorse che possono essere riutilizzate e semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="63eba-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="63eba-107">Per altre informazioni, vedere [Risorse XAML.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)</span><span class="sxs-lookup"><span data-stu-id="63eba-107">See [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="63eba-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="63eba-108">Example</span></span>

<span data-ttu-id="63eba-109">Il codice seguente mostra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="63eba-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="63eba-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63eba-110">See also</span></span>

- [<span data-ttu-id="63eba-111">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="63eba-111">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="63eba-112">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="63eba-112">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="63eba-113">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="63eba-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="63eba-114">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="63eba-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
