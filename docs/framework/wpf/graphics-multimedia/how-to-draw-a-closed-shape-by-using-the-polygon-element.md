---
title: 'Procedura: disegnare una forma chiusa utilizzando l''elemento poligono'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cf842c22238105510b13407d55c8c9773f84a70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="25516-102">Procedura: disegnare una forma chiusa utilizzando l'elemento poligono</span><span class="sxs-lookup"><span data-stu-id="25516-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="25516-103">In questo esempio viene illustrato come disegnare una forma chiusa utilizzando il <xref:System.Windows.Shapes.Polygon> elemento.</span><span class="sxs-lookup"><span data-stu-id="25516-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="25516-104">Per disegnare una forma chiusa, creare un <xref:System.Windows.Shapes.Polygon> elemento e utilizzare il relativo <xref:System.Windows.Shapes.Polygon.Points%2A> proprietà per specificare i vertici di una forma.</span><span class="sxs-lookup"><span data-stu-id="25516-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="25516-105">Viene automaticamente disegnare una linea che connette il primo e ultimo punto.</span><span class="sxs-lookup"><span data-stu-id="25516-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="25516-106">Infine, specificare un <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, o entrambi.</span><span class="sxs-lookup"><span data-stu-id="25516-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25516-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="25516-107">Example</span></span>  
 <span data-ttu-id="25516-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], la sintassi valida per i punti di è un elenco delimitato da virgole di coppie di coordinate x e y separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="25516-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="25516-109">Sebbene nell'esempio viene utilizzato un <xref:System.Windows.Controls.Canvas> per contenere i poligoni, è possibile utilizzare elementi poligono (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="25516-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="25516-110">In questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi forma](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="25516-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
