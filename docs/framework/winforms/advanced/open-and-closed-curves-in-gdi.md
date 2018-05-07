---
title: Curve aperte e chiuse in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 47f420184ac384ab11054d1cc3e767ab7f618234
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="open-and-closed-curves-in-gdi"></a>Curve aperte e chiuse in GDI+
La figura seguente mostra due curve: una aperta e una chiusa.  
  
 ![Curve aperte e chiuse](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")  
  
## <a name="managed-interface-for-curves"></a>Interfaccia gestita per curve  
 Curve chiuse sono una parte interna e possono pertanto essere riempite con un pennello. Il <xref:System.Drawing.Graphics> classe [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce i metodi seguenti per il riempimento di forme e curve chiuse: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, e <xref:System.Drawing.Graphics.FillRegion%2A>. Quando si chiama uno di questi metodi, è necessario passare uno dei tipi di pennello specifico (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, o <xref:System.Drawing.Drawing2D.PathGradientBrush>) come argomento.  
  
 Il <xref:System.Drawing.Graphics.FillPie%2A> metodo è correlato al <xref:System.Drawing.Graphics.DrawArc%2A> metodo. Come il <xref:System.Drawing.Graphics.DrawArc%2A> metodo disegna una parte della struttura di un'ellisse, il <xref:System.Drawing.Graphics.FillPie%2A> metodo compila una parte all'interno di un'ellisse. Nell'esempio seguente disegna un arco e riempie la parte corrispondente all'interno dell'ellisse:  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 Nella figura seguente mostra l'arco e torta piena.  
  
 ![Curve aperte e chiuse](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")  
  
 Il <xref:System.Drawing.Graphics.FillClosedCurve%2A> metodo è correlato al <xref:System.Drawing.Graphics.DrawClosedCurve%2A> metodo. Entrambi i metodi di chiudono automaticamente la curva tramite la connessione al punto finale al punto di partenza. Nell'esempio seguente viene tracciata una curva passante (0, 0), (60, 20) e (40, 50). Quindi, la curva viene chiuso automaticamente tramite la connessione (40, 50) al punto di partenza (0, 0), e l'interno viene riempito con un colore a tinta unita.  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 Il <xref:System.Drawing.Graphics.FillPath%2A> metodo riempie l'area interna di pezzi di percorso separati. Se una parte di un percorso non costituisce una curva chiusa o una forma, il <xref:System.Drawing.Graphics.FillPath%2A> metodo chiude automaticamente tale parte del percorso prima dell'inserimento. Nell'esempio seguente disegna e riempie un percorso costituito da un arco, una spline di tipo cardinal, una stringa e un grafico a torta:  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 Nella figura seguente mostra il percorso con e senza riempimento a tinta unita. Nota che il testo nella stringa di è descritta, ma non è compilato, per il <xref:System.Drawing.Graphics.DrawPath%2A> metodo. È il <xref:System.Drawing.Graphics.FillPath%2A> metodo riempire i caratteri nella stringa.  
  
 ![Stringa in un percorso](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Costruzione e creazione di percorsi](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
