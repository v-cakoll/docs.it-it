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
ms.workload: dotnet
ms.openlocfilehash: 6d2eaf570190f85ca084e5a5ab5d1bee1be56871
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
