---
title: Percorsi di oggetti Graphics in GDI+
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
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 022a591a1d646b154c2bd59a2f2ab21b78b9dbda
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="graphics-paths-in-gdi"></a>Percorsi di oggetti Graphics in GDI+
I percorsi sono costituiti dalla combinazione di linee, rettangoli e curve semplici. Ricorda di [Cenni preliminari sulla grafica vettoriale](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) i seguenti blocchi predefiniti si sono rivelati a essere più utili per il disegno di immagini:  
  
-   Linee  
  
-   Rettangoli  
  
-   Puntini di sospensione  
  
-   Archi  
  
-   Poligoni  
  
-   Spline cardinali  
  
-   Spline di Bézier  
  
 In GDI+, i <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto consente di raccogliere una sequenza di tali blocchi predefiniti in una singola unità. L'intera sequenza di linee, rettangoli, poligoni e curve può quindi essere disegnata con una chiamata al <xref:System.Drawing.Graphics.DrawPath%2A> metodo la <xref:System.Drawing.Graphics> classe. Nella figura seguente viene illustrato un percorso creato dalla combinazione di una riga, un arco, una spline di Bézier e una spline di tipo cardinal.  
  
 ![Percorso](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>Utilizzo di un percorso  
 Il <xref:System.Drawing.Drawing2D.GraphicsPath> classe fornisce i metodi seguenti per la creazione di una sequenza di elementi da tracciare: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (per spline cardinali), e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>. Ognuno di questi metodi è in overload; ovvero, ogni metodo supporta diversi elenchi di parametri diversi. Ad esempio, una variazione del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve quattro valori integer e un'altra variazione del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve due <xref:System.Drawing.Point> oggetti.  
  
 I metodi per l'aggiunta di linee, rettangoli e spline di Bézier da un percorso sono associati più metodi che aggiungono diversi elementi nel percorso in una singola chiamata: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>. Inoltre, il <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> metodi sono metodi complementare, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, che consentono di aggiungere una curva o chiusa a torta al percorso.  
  
 Per disegnare un tracciato, è necessario un <xref:System.Drawing.Graphics> oggetto, un <xref:System.Drawing.Pen> , oggetto e un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawPath%2A> (metodo) e <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio spessore e colore della linea utilizzata per eseguire il rendering di percorso. Il <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia la sequenza di linee e curve che costituiscono il percorso. Il <xref:System.Drawing.Pen> oggetto e <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto vengono passati come argomenti per il <xref:System.Drawing.Graphics.DrawPath%2A> metodo. Nell'esempio seguente disegna un percorso che include una riga, di un'ellisse e di una spline di Bézier:  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 Nella figura seguente mostra il percorso.  
  
 ![Percorso](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 Oltre ad aggiungere righe, rettangoli e curve a un percorso, è possibile aggiungere i percorsi in un percorso. Ciò consente di combinare i percorsi esistenti per creare percorsi lunghi e complessi.  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 Esistono altri due elementi è possibile aggiungere a un percorso: stringhe e i grafici a torta. Un grafico a torta è una parte all'interno di un'ellisse. L'esempio seguente crea un percorso da un arco, una spline di tipo cardinal, una stringa e un grafico a torta:  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 Nella figura seguente mostra il percorso. Si noti che un percorso non è necessario essere connessi; l'arco, spline di tipo cardinal, stringa e a torta sono separati.  
  
 ![Percorsi](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Costruzione e creazione di percorsi](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
