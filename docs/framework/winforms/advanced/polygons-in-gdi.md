---
title: Poligoni in GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 740a454873976e407843c417a7b09e5a5218398d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="3f622-102">Poligoni in GDI+</span><span class="sxs-lookup"><span data-stu-id="3f622-102">Polygons in GDI+</span></span>
<span data-ttu-id="3f622-103">Un poligono è una forma chiusa con tre o più lati.</span><span class="sxs-lookup"><span data-stu-id="3f622-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="3f622-104">Ad esempio, un triangolo è un poligono con tre lati, un rettangolo è un poligono con quattro lati e un pentagono è un poligono con cinque lati.</span><span class="sxs-lookup"><span data-stu-id="3f622-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="3f622-105">Nell'illustrazione seguente molti poligoni.</span><span class="sxs-lookup"><span data-stu-id="3f622-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="3f622-106">![Poligoni](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="3f622-106">![Polygons](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="3f622-107">Creazione di un poligono</span><span class="sxs-lookup"><span data-stu-id="3f622-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="3f622-108">Per disegnare un poligono, è necessario un <xref:System.Drawing.Graphics> oggetto, un <xref:System.Drawing.Pen> oggetto e una matrice di <xref:System.Drawing.Point> (o <xref:System.Drawing.PointF>) gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3f622-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="3f622-109">Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="3f622-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="3f622-110">Il <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio spessore e colore della linea utilizzata per eseguire il rendering del poligono e la matrice di <xref:System.Drawing.Point> oggetti archivia i punti di essere connessi tramite linee rette.</span><span class="sxs-lookup"><span data-stu-id="3f622-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="3f622-111">Il <xref:System.Drawing.Pen> oggetto e matrice di <xref:System.Drawing.Point> gli oggetti vengono passati come argomenti il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="3f622-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="3f622-112">Nell'esempio seguente disegna un poligono tre lati.</span><span class="sxs-lookup"><span data-stu-id="3f622-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="3f622-113">Si noti che esistono solo tre punti `myPointArray`: (0, 0), (50, 30) e (30, 60).</span><span class="sxs-lookup"><span data-stu-id="3f622-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="3f622-114">Il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo chiude automaticamente il poligono tracciando una linea da (30, 60) al punto inizio (0, 0).</span><span class="sxs-lookup"><span data-stu-id="3f622-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="3f622-115">Nella figura seguente viene illustrato il poligono.</span><span class="sxs-lookup"><span data-stu-id="3f622-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="3f622-116">![Poligono](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="3f622-116">![Polygon](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f622-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f622-117">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="3f622-118">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="3f622-118">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="3f622-119">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="3f622-119">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
