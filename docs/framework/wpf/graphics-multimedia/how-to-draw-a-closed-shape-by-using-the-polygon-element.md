---
title: "Procedura: disegnare una forma chiusa utilizzando l'elemento poligono"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 324a5623ee658789b8600a43a89ce26cab7cd6cd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452974"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="9c2ab-102">Procedura: disegnare una forma chiusa utilizzando l'elemento poligono</span><span class="sxs-lookup"><span data-stu-id="9c2ab-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="9c2ab-103">In questo esempio viene illustrato come disegnare una forma chiusa utilizzando l'elemento <xref:System.Windows.Shapes.Polygon>.</span><span class="sxs-lookup"><span data-stu-id="9c2ab-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="9c2ab-104">Per disegnare una forma chiusa, creare un elemento <xref:System.Windows.Shapes.Polygon> e utilizzare la relativa proprietà <xref:System.Windows.Shapes.Polygon.Points%2A> per specificare i vertici di una forma.</span><span class="sxs-lookup"><span data-stu-id="9c2ab-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="9c2ab-105">Viene disegnata automaticamente una linea che connette il primo e l'ultimo punto.</span><span class="sxs-lookup"><span data-stu-id="9c2ab-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="9c2ab-106">Infine, specificare un <xref:System.Windows.Shapes.Shape.Fill%2A>, un <xref:System.Windows.Shapes.Shape.Stroke%2A>o entrambi.</span><span class="sxs-lookup"><span data-stu-id="9c2ab-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c2ab-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="9c2ab-107">Example</span></span>  
 <span data-ttu-id="9c2ab-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]la sintassi valida per i punti è un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="9c2ab-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="9c2ab-109">Sebbene nell'esempio venga utilizzato un <xref:System.Windows.Controls.Canvas> per contenere i poligoni, è possibile utilizzare gli elementi Polygon (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="9c2ab-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="9c2ab-110">Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="9c2ab-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>
