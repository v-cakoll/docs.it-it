---
title: Poligoni in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 3ac6b9b651e65a45612cf2bd8ff17990c5cfba0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="polygons-in-gdi"></a>Poligoni in GDI+
Un poligono è una forma chiusa con tre o più lati. Ad esempio, un triangolo è un poligono con tre lati, un rettangolo è un poligono con quattro lati e un pentagono è un poligono con cinque lati. Nell'illustrazione seguente molti poligoni.  
  
 ![Poligoni](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>Creazione di un poligono  
 Per disegnare un poligono, è necessario un <xref:System.Drawing.Graphics> oggetto, un <xref:System.Drawing.Pen> oggetto e una matrice di <xref:System.Drawing.Point> (o <xref:System.Drawing.PointF>) gli oggetti. Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo. Il <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio spessore e colore della linea utilizzata per eseguire il rendering del poligono e la matrice di <xref:System.Drawing.Point> oggetti archivia i punti di essere connessi tramite linee rette. Il <xref:System.Drawing.Pen> oggetto e matrice di <xref:System.Drawing.Point> gli oggetti vengono passati come argomenti il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo. Nell'esempio seguente disegna un poligono tre lati. Si noti che esistono solo tre punti `myPointArray`: (0, 0), (50, 30) e (30, 60). Il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo chiude automaticamente il poligono tracciando una linea da (30, 60) al punto inizio (0, 0).  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 Nella figura seguente viene illustrato il poligono.  
  
 ![Poligono](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Procedura: Creare un oggetto Pen](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
