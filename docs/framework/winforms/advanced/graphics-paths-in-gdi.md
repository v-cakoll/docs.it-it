---
title: Percorsi di oggetti Graphics in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: c9a43065210f5ef0fffcae01cc7eb88349696b6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938166"
---
# <a name="graphics-paths-in-gdi"></a>Percorsi di oggetti Graphics in GDI+
I percorsi sono costituiti dalla combinazione di linee, rettangoli e le curve semplice. Si ricorderà dal [Cenni preliminari sulla grafica vettoriale](vector-graphics-overview.md) che i blocchi predefiniti seguenti hanno dimostrato di essere particolarmente utile per il disegno di immagini:  
  
- Linee  
  
- Rettangoli  
  
- Puntini di sospensione  
  
- Archi  
  
- Poligoni  
  
- Spline cardinali  
  
- Spline di Bézier  
  
 In GDI+, le <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto consente di raccogliere una sequenza di questi blocchi predefiniti in una singola unità. L'intera sequenza di linee, rettangoli, poligoni e curve possa quindi disegnata con una chiamata ai <xref:System.Drawing.Graphics.DrawPath%2A> metodo del <xref:System.Drawing.Graphics> classe. La figura seguente mostra un percorso creato dalla combinazione di una riga, un arco, una spline di Bézier e una spline di tipo cardinal.  
  
 ![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>Utilizzando un percorso  
 Il <xref:System.Drawing.Drawing2D.GraphicsPath> classe fornisce i metodi seguenti per la creazione di una sequenza di elementi da disegnare: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (per cardinali), e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>. Ognuno di questi metodi è in overload; ogni metodo, ovvero supporta diversi elenchi di parametri diversi. Ad esempio, una variazione del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve quattro interi e un'altra variazione del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve due <xref:System.Drawing.Point> oggetti.  
  
 I metodi per l'aggiunta di linee, rettangoli e spline di Bézier in un percorso sono associati più metodi che aggiungono diversi elementi nel percorso in una singola chiamata: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>. Inoltre, il <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> metodi includono metodi complementare, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, che consentono di aggiungere una curva chiusa o un grafico a torta al percorso.  
  
 Per disegnare un tracciato, è necessario un <xref:System.Drawing.Graphics> oggetti, una <xref:System.Drawing.Pen> oggetti e un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce le <xref:System.Drawing.Graphics.DrawPath%2A> metodo e il <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la larghezza e il colore della linea utilizzata per eseguire il rendering di percorso. Il <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia la sequenza di linee e curve che costituiscono il percorso. Il <xref:System.Drawing.Pen> oggetto e il <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto vengono passati come argomenti per il <xref:System.Drawing.Graphics.DrawPath%2A> (metodo). L'esempio seguente disegna un percorso che è costituito da una riga, un'ellisse e una spline di Bézier:  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 La figura seguente mostra il percorso.  
  
 ![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 Oltre all'aggiunta di rettangoli, linee e curve a un percorso, è possibile aggiungere i percorsi in un percorso. In questo modo è possibile combinare percorsi esistenti per creare percorsi lunghi e complessi.  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 Esistono due altri elementi di cui è possibile aggiungere a un percorso: stringhe e grafici a torta. Un grafico a torta è riportata una parte all'interno di un'ellisse. L'esempio seguente crea un percorso da un arco, una spline di tipo cardinal, una stringa e un grafico a torta:  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 La figura seguente mostra il percorso. Si noti che un percorso non deve essere connessa; l'arco, di tipo Cardinal, stringa e a torta sono separati.  
  
 ![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
- [Costruzione e creazione di percorsi](constructing-and-drawing-paths.md)
