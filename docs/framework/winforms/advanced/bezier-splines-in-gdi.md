---
title: B&#233;Bézier spline in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779278"
---
# <a name="b233zier-splines-in-gdi"></a>B&#233;Bézier spline in GDI+
Una spline di Bézier è una curva specificata da quattro punti: due punti finali (p1 e p2) e due punti di controllo (c1 e c2). La curva di p1 in cui inizia e termina in corrispondenza di p2. La curva non passa attraverso i punti di controllo, ma i punti di controllo usate come magneti, eseguire il pull della curva in determinate le direzioni e che influenzano il modo che curvatura. La figura seguente mostra una curva di Bézier insieme ai relativi punti finali e i punti di controllo.  
  
 ![Spline di Bézier](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 La curva inizia da p1 e procede verso il punto di controllo c1. La tangente della curva in p1 è la riga disegnata da p1 a c1. La tangente a p2 endpoint è la riga disegnata dal c2 a p2.  
  
## <a name="drawing-bzier-splines"></a>Disegnare spline di Bézier  
 Per disegnare una spline di Bézier, è necessario un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Pen>. L'istanza del <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawBezier%2A> metodo e il <xref:System.Drawing.Pen> archivia gli attributi, ad esempio la larghezza e il colore della linea utilizzata per eseguire il rendering della curva. Il <xref:System.Drawing.Pen> viene passato come uno degli argomenti per il <xref:System.Drawing.Graphics.DrawBezier%2A> (metodo). I restanti argomenti passati al <xref:System.Drawing.Graphics.DrawBezier%2A> metodo sono gli endpoint e i punti di controllo. L'esempio seguente disegna una spline di Bézier con punto iniziale (0, 0), controllare i punti (40, 20) e (80, 150) e il punto (100, 10) finale:  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 La figura seguente mostra la curva, i punti di controllo e due righe tangente.  
  
 ![Spline di Bézier](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 Spline di Bézier sono stati originariamente sviluppate da Pierre Bézier per la progettazione del settore automobilistico. Essi sono poiché rivelati utili in molti tipi di progettazione assistita da computer e vengono inoltre usate per definire i contorni dei caratteri. Spline di Bézier possono ottenere una vasta gamma di forme, alcune delle quali sono illustrate nella figura seguente.  
  
 ![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Costruzione e creazione di curve](constructing-and-drawing-curves.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
- [Procedura: Creare un oggetto Pen](how-to-create-a-pen.md)
