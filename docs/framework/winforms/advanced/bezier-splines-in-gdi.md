---
title: B&#233;Bézier Bézier in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: 2e247ec2bcd57c2fb2f5c32f61d38a2e7a267ff1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="b233zier-splines-in-gdi"></a>B&#233;Bézier Bézier in GDI+
Una spline di Bézier è una curva specificata da quattro punti: due punti finali (p1 e p2) e due punti di controllo (c1 e c2). La curva inizia p1 e p2 termina. La curva non passano attraverso i punti di controllo, ma i punti di controllo di agire come grado attirare l'attenzione, estrarre la curva in determinate direzioni e che influenzano il modo di che curvatura. Nella figura seguente mostra una curva di Bézier insieme ai relativi punti di controllo e di endpoint.  
  
 ![Spline di Bézier](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 La curva inizia in p1 e si sposta verso il punto di controllo c1. La tangente della curva in p1 è la riga disegnata da p1 a c1. La tangente al punto finale p2 è la riga che unisce c2 e p2.  
  
## <a name="drawing-bzier-splines"></a>Disegnare spline di Bézier  
 Per tracciare una spline di Bézier, sono necessari un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Pen>. L'istanza del <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawBezier%2A> (metodo) e <xref:System.Drawing.Pen> archivia gli attributi, ad esempio spessore e colore della linea utilizzata per eseguire il rendering della curva. Il <xref:System.Drawing.Pen> viene passato come uno degli argomenti per il <xref:System.Drawing.Graphics.DrawBezier%2A> metodo. Gli argomenti rimanenti passati di <xref:System.Drawing.Graphics.DrawBezier%2A> metodo sono gli endpoint e i punti di controllo. Nell'esempio seguente disegna una spline di Bézier con punto iniziale (0, 0), controllare i punti (40, 20) e (80, 150) e punto finale (100, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 Nella figura seguente mostra la curva, i punti di controllo e due tangenti.  
  
 ![Spline di Bézier](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 Spline di Bézier sono stati originariamente sviluppate da Pierre Bézier per progettazione nel settore automobilistico. Essi sono poiché rivelati utili in molti tipi di progettazione assistita da computer e vengono inoltre utilizzate per definire le strutture di tipi di carattere. Spline di Bézier possono cedere l'esecuzione di un'ampia gamma di forme, alcune delle quali sono mostrate nella figura seguente.  
  
 ![Percorsi](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Costruzione e creazione di curve](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Procedura: Creare un oggetto Pen](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
