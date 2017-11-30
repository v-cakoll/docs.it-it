---
title: 'Procedura: disegnare spline di tipo Cardinal'
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
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c47ff269cb1c367abee0be197fdc80485fb37b97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-cardinal-splines"></a>Procedura: disegnare spline di tipo Cardinal
Spline di tipo cardinal è una curva che passa attraverso un determinato set di punti. Per disegnare spline di tipo cardinal, creare un <xref:System.Drawing.Graphics> dell'oggetto e passare l'indirizzo di una matrice di punti per il <xref:System.Drawing.Graphics.DrawCurve%2A> metodo.  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Creazione di una Spline di tipo Cardinal a campana  
  
-   Nell'esempio seguente disegna una spline di tipo cardinal a campana che passa attraverso cinque punti designati. Nella figura seguente mostra la curva e cinque punti.  
  
     ![Spline di tipo Cardinal](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>Disegno di una spline di tipo Cardinal chiusa  
  
-   Utilizzare il <xref:System.Drawing.Graphics.DrawClosedCurve%2A> metodo la <xref:System.Drawing.Graphics> classe per disegnare una spline di tipo cardinal chiusa. In una spline di tipo cardinal chiusa, la curva continua fino all'ultimo punto della matrice e si connette con il primo punto nella matrice. Nell'esempio seguente disegna una spline di tipo cardinal chiusa che passa attraverso sei punti designati. Nella figura seguente mostra la spline chiusa e sei punti.  
  
 ![Spline di tipo Cardinal](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>Modifica della curvatura di una spline di tipo Cardinal  
  
-   Possibile modificare la spline di tipo cardinal passando un argomento di tensione per la <xref:System.Drawing.Graphics.DrawCurve%2A> metodo. L'esempio seguente disegna una spline di tipo cardinal tre che passano attraverso lo stesso set di punti. Nella figura seguente mostra le tre curve insieme ai relativi valori di tensione. Si noti che quando la tensione è 0, i punti vengono collegati da linee rette.  
  
 ![Spline di tipo Cardinal](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Negli esempi precedenti sono progettati per l'uso con Windows Form e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Costruzione e creazione di curve](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
