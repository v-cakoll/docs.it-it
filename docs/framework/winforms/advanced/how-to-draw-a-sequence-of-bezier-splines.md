---
title: "Procedura: disegnare una sequenza di B &#233; spline di Bézier"
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
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f5bdd9ae29dcbb8397d2fe645e240572aad32a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>Procedura: disegnare una sequenza di B &#233; spline di Bézier
È possibile utilizzare il <xref:System.Drawing.Graphics.DrawBeziers%2A> metodo il <xref:System.Drawing.Graphics> connessi di classe per creare una sequenza di spline di Bézier.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene tracciata una curva composta da due connessione di spline di Bézier. L'endpoint di spline di Bézier il primo è il punto iniziale della seconda spline di Bézier.  
  
 Nella figura seguente mostra la spline collegate insieme i sette punti.  
  
 ![Spline di Bézier](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Spline di Bézier in GDI+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [Costruzione e creazione di curve](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
