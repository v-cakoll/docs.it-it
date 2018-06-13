---
title: 'Procedura: creare una geometria combinata'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: 107e0342b822633ccb4f51f256c121cc80c297f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561121"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="a8726-102">Procedura: creare una geometria combinata</span><span class="sxs-lookup"><span data-stu-id="a8726-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="a8726-103">In questo esempio viene illustrato come combinare le geometrie.</span><span class="sxs-lookup"><span data-stu-id="a8726-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="a8726-104">Per combinare due geometrie, utilizzare un <xref:System.Windows.Media.CombinedGeometry> oggetto.</span><span class="sxs-lookup"><span data-stu-id="a8726-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="a8726-105">Impostare il relativo <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> con le due geometrie da combinare e impostare il <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> proprietà che determina come le geometrie saranno combinate insieme, per `Union`, `Intersect`, `Exclude`, o `Xor`.</span><span class="sxs-lookup"><span data-stu-id="a8726-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="a8726-106">Per creare una geometria composta da due o più geometrie, utilizzare un <xref:System.Windows.Media.GeometryGroup>.</span><span class="sxs-lookup"><span data-stu-id="a8726-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8726-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8726-107">Example</span></span>  
 <span data-ttu-id="a8726-108">Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di geometria `Exclude`.</span><span class="sxs-lookup"><span data-stu-id="a8726-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="a8726-109">Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="a8726-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="a8726-110">![Modalità di combinazione di risultati di Exclude](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="a8726-110">![Results of the Exclude combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="a8726-111">Esclusione di geometria combinata</span><span class="sxs-lookup"><span data-stu-id="a8726-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="a8726-112">Nel codice seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione `Intersect`.</span><span class="sxs-lookup"><span data-stu-id="a8726-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="a8726-113">Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="a8726-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="a8726-114">![Risultato dell'intersezione tra modalità di combinazione](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="a8726-114">![Results of the Intersect combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="a8726-115">Geometria combinata Intersect</span><span class="sxs-lookup"><span data-stu-id="a8726-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="a8726-116">Nel codice seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione `Union`.</span><span class="sxs-lookup"><span data-stu-id="a8726-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="a8726-117">Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="a8726-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="a8726-118">![Risultati della modalità di combinazione unione](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="a8726-118">![Results of the Union combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="a8726-119">Unione di geometria combinato</span><span class="sxs-lookup"><span data-stu-id="a8726-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="a8726-120">Nel codice seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione `Xor`.</span><span class="sxs-lookup"><span data-stu-id="a8726-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="a8726-121">Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="a8726-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="a8726-122">![Risultati della modalità di combinazione Xor](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="a8726-122">![Results of the Xor combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="a8726-123">Geometria combinata Xor</span><span class="sxs-lookup"><span data-stu-id="a8726-123">Combined Geometry Xor</span></span>
