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
ms.openlocfilehash: 8581b5f8d774a91d17dcfe93f801d87394f28c0b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735208"
---
# <a name="open-and-closed-curves-in-gdi"></a>Curve aperte e chiuse in GDI+
La figura seguente mostra due curve: quello aperto e una chiusa.  
  
 ![Curve aperte e chiuse](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")  
  
## <a name="managed-interface-for-curves"></a>Interfaccia gestita per le curve  
 Curve chiuse hanno una parte interna e possono quindi essere riempite con un pennello. Il <xref:System.Drawing.Graphics> classe [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce i metodi seguenti per il riempimento curve e forme chiuse: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, e <xref:System.Drawing.Graphics.FillRegion%2A>. Ogni volta che si chiama uno di questi metodi, è necessario passare uno dei tipi di pennello specifico (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, o <xref:System.Drawing.Drawing2D.PathGradientBrush>) come argomento.  
  
 Il <xref:System.Drawing.Graphics.FillPie%2A> metodo è complementare al <xref:System.Drawing.Graphics.DrawArc%2A> (metodo). Proprio come le <xref:System.Drawing.Graphics.DrawArc%2A> metodo disegna una parte del contorno di un'ellisse, di <xref:System.Drawing.Graphics.FillPie%2A> metodo inserisce una parte all'interno di un'ellisse. Nell'esempio seguente disegna un arco e riempie la parte corrispondente della parte interna dell'ellisse:  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 La figura seguente mostra il grafico a torta colorata e l'arco.  
  
 ![Curve aperte e chiuse](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")  
  
 Il <xref:System.Drawing.Graphics.FillClosedCurve%2A> metodo è complementare al <xref:System.Drawing.Graphics.DrawClosedCurve%2A> (metodo). Entrambi i metodi di chiudere automaticamente la curva tramite la connessione al punto finale per il punto di partenza. L'esempio seguente disegna una curva che passa attraverso (0, 0), (60, 20) e (40, 50). Quindi, la curva è chiuso automaticamente tramite la connessione (40, 50) al punto di partenza (0, 0), e la parte interna viene riempita con colori a tinta unita.  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 Il <xref:System.Drawing.Graphics.FillPath%2A> metodo riempie l'area interna di pezzi di un percorso separati. Se una parte di un percorso non forma una curva chiusa o una forma, il <xref:System.Drawing.Graphics.FillPath%2A> metodo chiude automaticamente tale parte del percorso prima di compilarlo. Nell'esempio seguente disegna e riempie un percorso che è costituito da un arco, una spline di tipo cardinal, una stringa e un grafico a torta:  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 La figura seguente mostra il percorso con e senza il riempimento a tinta unita. Si noti che il testo nella stringa è descritta, ma non è compilato, per il <xref:System.Drawing.Graphics.DrawPath%2A> (metodo). Si tratta di <xref:System.Drawing.Graphics.FillPath%2A> metodo riempire i caratteri nella stringa.  
  
 ![Stringa in un percorso](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [Costruzione e creazione di percorsi](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
