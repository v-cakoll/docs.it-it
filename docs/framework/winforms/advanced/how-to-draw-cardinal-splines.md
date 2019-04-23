---
title: 'Procedura: Disegnare cardinal spline'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 2f03177bf97936a2ca9558972d4d82fa3e07463c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204952"
---
# <a name="how-to-draw-cardinal-splines"></a>Procedura: Disegnare cardinal spline
Spline di tipo cardinal è una curva che passa attraverso un set specificato di punti. Per disegnare spline di tipo cardinal, creare un <xref:System.Drawing.Graphics> , quindi passare l'indirizzo di una matrice di punti di <xref:System.Drawing.Graphics.DrawCurve%2A> (metodo).  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Creazione di una Spline cardinali a forma di campana  
  
-   Nell'esempio seguente disegna una spline di tipo cardinal a forma di campana che passa attraverso cinque punti designati. La figura seguente mostra la curva e cinque punti.  
  
     ![Diagramma che mostra una spline di tipo cardinal a campana.](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>Disegnare una curva Spline cardinale chiusa  
  
-   Usare la <xref:System.Drawing.Graphics.DrawClosedCurve%2A> metodo del <xref:System.Drawing.Graphics> classe per disegnare una curva spline cardinale chiusa. In una spline di tipo cardinal chiusa, la curva continua fino all'ultimo punto della matrice e si connette con il primo punto della matrice. L'esempio seguente disegna una spline di tipo cardinal chiusa che attraversa sei punti designati. La figura seguente mostra la spline di tipo chiusa insieme a sei punti:  
  
 ![Diagramma che mostra una spline di tipo cardinal chiusa.](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>Modifica della curvatura di una Spline di tipo Cardinal  
  
-   Modificare la modalità di una spline di tipo cardinal devia passando un argomento di tensione per la <xref:System.Drawing.Graphics.DrawCurve%2A> (metodo). L'esempio seguente disegna una spline di tipo cardinal tre che passano attraverso lo stesso set di punti. La figura seguente illustra le tre curve insieme ai relativi valori di tensione. Si noti che quando la tensione è 0, i punti connessi da linee rette.  
  
 ![Diagramma che mostra tre spline cardinale.](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Negli esempi precedenti sono progettati per l'uso con Windows Form, e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche

- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Costruzione e creazione di curve](constructing-and-drawing-curves.md)
