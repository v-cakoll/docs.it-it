---
title: 'Procedura: Disegnare una sequenza di B&#233;spline di Bézier'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 1de2f44be189cb2ff874a748ae6093c945120178
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711791"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>Procedura: Disegnare una sequenza di B&#233;spline di Bézier
È possibile usare il <xref:System.Drawing.Graphics.DrawBeziers%2A> metodo di <xref:System.Drawing.Graphics> connesso di classe per creare una sequenza di spline di Bézier.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente disegna una curva che è costituito da due spline di Bézier collegate. L'endpoint di spline di Bézier il primo è il punto di inizio della seconda spline di Bézier.  
  
 La figura seguente mostra la spline collegate insieme a sette punti.  
  
 ![Bezier Spline](./media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Spline di Bézier in GDI+](bezier-splines-in-gdi.md)
- [Costruzione e creazione di curve](constructing-and-drawing-curves.md)
