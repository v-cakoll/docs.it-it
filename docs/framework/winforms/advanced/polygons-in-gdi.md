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
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132626"
---
# <a name="polygons-in-gdi"></a>Poligoni in GDI+
Un poligono è una forma chiusa con tre o più lati. Ad esempio, un triangolo è un poligono con tre lati, un rettangolo è un poligono con quattro lati e un pentagon è un poligono con cinque i lati. La figura seguente mostra molti poligoni.  
  
 ![I poligoni](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>Creazione di un poligono  
 Per tracciare un'istanza polygon, è necessario un <xref:System.Drawing.Graphics> oggetti, una <xref:System.Drawing.Pen> oggetto e matrice di <xref:System.Drawing.Point> (o <xref:System.Drawing.PointF>) oggetti. Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawPolygon%2A> (metodo). Il <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la larghezza e il colore della linea utilizzata per eseguire il rendering del poligono e la matrice di <xref:System.Drawing.Point> oggetti archivia i punti di essere connessi da linee rette. Il <xref:System.Drawing.Pen> oggetto e matrice di <xref:System.Drawing.Point> gli oggetti vengono passati come argomenti il <xref:System.Drawing.Graphics.DrawPolygon%2A> (metodo). L'esempio seguente disegna un poligono tre lati. Si noti che esistono solo tre punti `myPointArray`: (0, 0), (50, 30) e (30, 60). Il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo chiude automaticamente il poligono tracciando una linea dal (30, 60) nuovamente al punto di partenza (0, 0).  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 La figura seguente mostra il poligono.  
  
 ![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Creare un oggetto Pen](how-to-create-a-pen.md)
