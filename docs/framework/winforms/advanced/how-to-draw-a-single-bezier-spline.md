---
title: "Procedura: disegno di un singolo B &#233; Spline di Bézier"
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
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ebdba9e01824cc764a6ab759da049add180ba83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Procedura: disegno di un singolo B &#233; Spline di Bézier
Una spline di Bézier è definita da quattro punti: un punto di inizio, due punti di controllo e un endpoint.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente disegna una spline di Bézier con endpoint (200, 100) e il punto di inizio (10, 100). I punti di controllo sono (100, 10) e (150, 150).  
  
 Nella figura seguente mostra la spline di Bézier risulta con il punto iniziale, punti di controllo e l'endpoint. L'illustrazione mostra anche convessa della spline, un poligono formato collegando i quattro punti con linee rette.  
  
 ![Spline di Bézier](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [Spline di Bézier in GDI+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [Procedura: Disegnare una sequenza di spline di Bézier](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
