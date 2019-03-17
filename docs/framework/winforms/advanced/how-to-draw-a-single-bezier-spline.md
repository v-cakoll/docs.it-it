---
title: 'Procedura: Disegnare una singola B&#233;Spline di Bézier'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 0731595dc25b1afb4b3dbcc7eedbfb92ef32d267
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2019
ms.locfileid: "58126279"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Procedura: Disegnare una singola B&#233;Spline di Bézier
Viene definita una spline di Bézier da quattro punti: un punto di partenza, due punti di controllo e un endpoint.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente disegna una spline di Bézier con endpoint (200, 100) e il punto di inizio (10, 100). I punti di controllo sono (100, 10) e (150, 150).  
  
 La figura seguente mostra la spline di Bézier risulta con il punto iniziale, i punti di controllo ed endpoint. L'illustrazione mostra anche struttura convessa della spline, che è un poligono costituito dalla connessione di quattro punti con linee rette.  
  
 ![Illustrazione di una Spline di Bézier.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [Spline di Bézier in GDI+](bezier-splines-in-gdi.md)
- [Procedura: Disegnare una sequenza di spline di Bézier](how-to-draw-a-sequence-of-bezier-splines.md)
