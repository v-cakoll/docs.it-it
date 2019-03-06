---
title: 'Procedura: Creare una geometria combinata'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364788"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="e480e-102">Procedura: Creare una geometria combinata</span><span class="sxs-lookup"><span data-stu-id="e480e-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="e480e-103">In questo esempio viene illustrato come combinare le geometrie.</span><span class="sxs-lookup"><span data-stu-id="e480e-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="e480e-104">Per combinare due geometrie, usare un <xref:System.Windows.Media.CombinedGeometry> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e480e-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="e480e-105">Impostare relativi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> con le due geometrie per combinare e impostare il <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> proprietà, che determina come le geometrie vengono combinate insieme, alla `Union`, `Intersect`, `Exclude`, o `Xor`.</span><span class="sxs-lookup"><span data-stu-id="e480e-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="e480e-106">Per creare una geometria composta da due o più oggetti Geometry, usare un <xref:System.Windows.Media.GeometryGroup>.</span><span class="sxs-lookup"><span data-stu-id="e480e-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e480e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="e480e-107">Example</span></span>  
 <span data-ttu-id="e480e-108">Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di geometria `Exclude`.</span><span class="sxs-lookup"><span data-stu-id="e480e-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="e480e-109">Entrambe <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e il <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con scostamento dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="e480e-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="e480e-110">![Modalità di combinazione di risultati di Exclude](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="e480e-110">![Results of the Exclude combine mode](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="e480e-111">Esclusione di geometria combinata</span><span class="sxs-lookup"><span data-stu-id="e480e-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="e480e-112">Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Intersect`.</span><span class="sxs-lookup"><span data-stu-id="e480e-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="e480e-113">Entrambe <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e il <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con scostamento dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="e480e-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="e480e-114">![Modalità di combinazione di risultati di intersezione](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="e480e-114">![Results of the Intersect combine mode](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="e480e-115">Si intersecano geometria combinata</span><span class="sxs-lookup"><span data-stu-id="e480e-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="e480e-116">Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Union`.</span><span class="sxs-lookup"><span data-stu-id="e480e-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="e480e-117">Entrambe <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e il <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con scostamento dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="e480e-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="e480e-118">![Risultati della modalità di combinazione unione](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="e480e-118">![Results of the Union combine mode](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="e480e-119">Unione di geometria combinata</span><span class="sxs-lookup"><span data-stu-id="e480e-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="e480e-120">Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Xor`.</span><span class="sxs-lookup"><span data-stu-id="e480e-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="e480e-121">Entrambe <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e il <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con scostamento dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="e480e-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="e480e-122">![Risultati della modalità di combinazione Xor](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="e480e-122">![Results of the Xor combine mode](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="e480e-123">Xor geometria combinata</span><span class="sxs-lookup"><span data-stu-id="e480e-123">Combined Geometry Xor</span></span>
